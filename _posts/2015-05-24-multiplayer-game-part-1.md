---
layout: post
title: Multiplayer game part 1
tags : [development, tutorial, multiplayer, networking, nodejs]
---

I have been reading about networking for some time because multiplayer games are really fun. There is a few models to choose which fits better for your game. In my case I wanted to know about the client/server model. Seems to be the one for a FPS.

I couldn't find an entire example (code) for what involves making a client/server multiplayer game but I've found a really useful information. The theory of an *authoritative server* and *interpolation* stuff. These links really helped me to understand a multiplayer game:

- [https://developer.valvesoftware.com/wiki/Source_Multiplayer_Networking](https://developer.valvesoftware.com/wiki/Source_Multiplayer_Networking)
- [http://www.gamasutra.com/view/feature/131781/the_internet_sucks_or_what_i_.php](http://www.gamasutra.com/view/feature/131781/the_internet_sucks_or_what_i_.php)

So I decided to try something just for learning purposes and the result is kind of good because I could achieve something! Yeah, not a big deal but it was helpful to understand these things.

I've developed a *game* (?) using the *authoritative server* model. I don't know if is fair to call it a game because it isn't fun. It is more like a proof of concept. The code is entirely written in JavaScript because I wanted to learn about Node.js too. These are the ingredients:

- A [Node.js](https://nodejs.org/) server.
- A client using [Pixi.js](http://www.pixijs.com/) game engine.
- [socket.io](http://socket.io/) for communication between both sides.
- Kick-assets from *Doom*.

I will explain a little bit in the next posts but if you want to take a look, the code is hosted on [GitHub](https://github.com/matiasbeckerle/doom-lgs).

### Disclaimers

*The assets being used are from Doom. None of them are from my property. I hope id Software doesn't take it bad. I'm trying to reach them to let them know about it. I've choosed them because are such an inspiration for me and they rock!*

*Take into account that is just the tip of the iceberg. Anyone who wants to make a fast-paced multiplayer game would need to handle a LOT of things that I'm not showing here. The interpolation in this example is like a joke, seriously.*

*Please don't take anything from here as a rule because it could be very wrong. Maybe there are better ways to do it. Remember, is my first time with networking and I'm kind of a newbie with game development. I've just wanted to share a code that is working.*