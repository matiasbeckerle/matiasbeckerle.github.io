---
layout: post
title: Multiplayer game with Node.js and Pixi.js
tags : [gamedev, development, multiplayer, networking, JavaScript, Node.js, Pixi.js, socket.io]
---

<p>I have been reading about networking for some time because multiplayer games are really fun. There is a few models to choose which one fits better for your game but I decided to try with server/client model.</p>
<p>I couldn't find an entire example (code) for what involves making a server/client multiplayer game but I've found a really useful information. These links really helped me to understand what was going on behind the scenes:</p>
<ul>
  <li><a href="https://developer.valvesoftware.com/wiki/Source_Multiplayer_Networking">https://developer.valvesoftware.com/wiki/Source_Multiplayer_Networking</a></li>
  <li><a href="http://www.gamasutra.com/view/feature/131781/the_internet_sucks_or_what_i_.php">http://www.gamasutra.com/view/feature/131781/the_internet_sucks_or_what_i_.php</a></li>
</ul>
<p>So I decided to try something just for learning purposes and the result is kind of good, actually. I could achieve something! Yeah, not a big deal but it was helpful to understand these things.</p>
<p>I've developed a game (?) under <em>authoritative server</em> and <em>interpolation</em> concepts. I don't know if is fair to call it a game because it isn't fun. It is more like a proof of concept. The code is entirely written in JavaScript because I wanted to learn about <a href="https://nodejs.org">Node.js</a> too.</p>
<h3>Server/Client model</h3>
<p>The <a href="https://nodejs.org">Node.js</a> server sends snapshots of the current game state to all the connected players several times per second, using a small structure to identify uniquely each instance of the game objects. Is responsible of keeping the game alive and serving the resources too.</p>
<p>The client was developed with <a href="http://www.pixijs.com">Pixi.js</a> 2D game engine. Consumes the snapshots provided by the server and handles all the game objects (populated with the game engine information) in the scene.</p>
<p>The communication between both sides is handled by <a href="http://socket.io">socket.io</a>.</p>
<h3>Code and game</h3>
<ul>
  <li>You can <a href="https://doom-lgs.herokuapp.com">play the game</a> in Heroku where is hosted by free. Try the multiplayer stuff opening two browser tabs.</li>
  <li>The code is available at <a href="https://github.com/matiasbeckerle/doom-lgs">GitHub</a>. Take a look, I hope it helps!</li>
  <li>More information <a href="https://github.com/matiasbeckerle/doom-lgs/blob/master/README.md">here</a>.</li>
</ul>
<h3>Disclaimers</h3>
<p>The assets being used are from Doom. None of them are from my property. I hope id Software doesn't take it bad. I'm trying to reach them to let them know about it. I've choosed them because are such an inspiration for me and they rock!</p>
<p>Take into account that anyone who wants to make a fast-paced multiplayer game would need to handle a LOT of things that I'm not showing here. The interpolation in this example is like a joke, seriously.</p>
<p>Please don't take anything as a rule because it could be wrong. Maybe there are better solutions. Remember, is my first time with networking and I'm kind of a newbie with game development. I've just wanted to share a code that is working.</p>
