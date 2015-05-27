---
layout: post
title: Multiplayer game part 2
tags : [development, tutorial, multiplayer, networking, Node.js, Pixi.js, socket.io]
---

<div class="message">
	This post belongs to a series entitled "Multiplayer game". Please read the <a href="/2015/05/24/multiplayer-game-part-1">Part 1: Introduction</a>.
</div>

## Server

First of all, the main server script serves all the client-side resources and listen for connections using [socket.io](http://socket.io/) as the communication layer.

{% highlight js %}
http.listen(port, function () {
    console.log("Listening on *:" + port);
});

// Provide resources
app.use(express.static(__dirname + "/public"));
app.get("/", function (req, res) {
    res.sendFile(__dirname + "/index.html");
});

io.sockets.on("connection", function (socket) {
    // Add a new client
    addClient(socket);

    // Someone kills an enemy
    socket.on("enemyHit", function (enemyId) {
        gameManager.onEnemyHit(enemyId);
    });
    
    // Someone goes offline
    socket.on("disconnect", function () {
        removeClient(socket);
    });
});
{% endhighlight %}

Sends snapshots of the current game state to all the connected players several times per second, using a small structure to identify uniquely each instance of the game objects.

{% highlight js %}
// Start the game and send frequent updates to the clients
gameManager.start();
gameManager.onUpdate = function (snapshot) {
    io.emit("update", snapshot);
};
{% endhighlight %}

I have created a GameManager class that handles the whole game. When the server is deployed it starts an iteration with two different intervals:

- A very fast interval (100ms) that sends the snapshots to the players.
- A not-so-fast interval (3s) that verifies the current game and instantiate new enemies if necessary.

{% highlight js %}
/**
 * Starts a game iteration keeping two different ticks:
 *  - Snapshot will notify our players about the current game state.
 *  - Game will keep alive our game creating enemies, etc.
 */
var start = function () {
	tickSnapshot = setInterval(updateSnapshot, 100);
	tickGame = setInterval(updateGame, 3000);
};
	
/**
 * Sends a snapshot of the current game state to our players.
 */
function updateSnapshot() {
	GameManager.onUpdate(snapshot);
	snapshot.dirty = false;
}

/**
 * Keeps alive our game creating enemies, etc.
 */
function updateGame() {
	if (Object.keys(snapshot.enemies).length < spawnPositions.length){
		spawnEnemy();
	}
}
{% endhighlight %}

The snapshot has to be really small because contains the information to be communicated with the players. It has to be fast. In this game the snapshot only contains:

- Dirty check.
- Players quantity.
- Spawned enemies (only ID and position).

The trick behind the dirty check lies in the server knowing when there is a change needed to be reflected in all the other clients (players). You will see the clients only updating their game when there is a significant change (*dirty = true*).

The previous code snippets contains significant parts of the game but to understand the whole idea you would need to check the [repository](https://github.com/matiasbeckerle/doom-lgs).