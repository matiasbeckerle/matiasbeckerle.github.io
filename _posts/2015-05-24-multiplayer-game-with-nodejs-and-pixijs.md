---
layout: post
title: Multiplayer game with Node.js and Pixi.js
tags : [development, multiplayer, networking, Node.js, Pixi.js, socket.io]
---

I have been reading about networking for some time because multiplayer games are really fun. There is a few models to choose which one fits better for your game but I decided to try with server/client model.

I couldn't find an entire example (code) for what involves making a server/client multiplayer game but I've found a really useful information. These links really helped me to understand what was going on behind the scenes:

- [https://developer.valvesoftware.com/wiki/Source_Multiplayer_Networking](https://developer.valvesoftware.com/wiki/Source_Multiplayer_Networking)
- [http://www.gamasutra.com/view/feature/131781/the_internet_sucks_or_what_i_.php](http://www.gamasutra.com/view/feature/131781/the_internet_sucks_or_what_i_.php)

So I decided to try something just for learning purposes and the result is kind of good, actually. I could achieve something! Yeah, not a big deal but it was helpful to understand these things.

I've developed a game (?) under *authoritative server* and *interpolation* concepts. I don't know if is fair to call it a game because it isn't fun. It is more like a proof of concept. The code is entirely written in JavaScript because I wanted to learn about [Node.js](https://nodejs.org) too.

## Server/Client model

The [Node.js](https://nodejs.org) server sends snapshots of the current game state to all the connected players several times per second, using a small structure to identify uniquely each instance of the game objects. Is responsible of keeping the game alive and serving the resources too.

The client was developed with [Pixi.js](http://www.pixijs.com) 2D game engine. Consumes the snapshots provided by the server and handles all the game objects (populated with the game engine information) in the scene.

The communication between both sides is handled by [socket.io](http://socket.io).

## Code and game

- You can [play the game](https://doom-lgs.herokuapp.com) in Heroku where is hosted by free. Try the multiplayer stuff opening two browser tabs.
- The code is available at [GitHub](https://github.com/matiasbeckerle/doom-lgs). Take a look, I hope it helps!

## Disclaimers

The assets being used are from Doom. None of them are from my property. I hope id Software doesn't take it bad. I'm trying to reach them to let them know about it. I've choosed them because are such an inspiration for me and they rock!

Take into account that anyone who wants to make a fast-paced multiplayer game would need to handle a LOT of things that I'm not showing here. The interpolation in this example is like a joke, seriously.

Please don't take anything as a rule because it could be wrong. Maybe there are better solutions. Remember, is my first time with networking and I'm kind of a newbie with game development. I've just wanted to share a code that is working.