---
layout: default
title: The making of PERSPEkTIVA
tags: [gamedev, development, tips]
---

Before I start, you can download and play the game using the following link:

[http://matiasbeckerle.itch.io/perspektiva](http://matiasbeckerle.itch.io/perspektiva)

. . .

This year I failed too many times to conceive a video game. During mid August I decided to start again from level 1: learn the basics as expert people recommends. And they were right, so right.

If you are a beginner gamedev as me (it doesn't matter if you are already experienced with coding) you need to do this first. Trust me, because starting to make a video game is easy, finishing it is not. Finishing it is the most difficult part.

My primary objetive was to make a classic or something with fixed and small scope. Mechanics, aesthetics, sound, music, menus, polish, testing. Everything like a pro video game but without the PR work because I didn't want to sell it, just learn from it.

A breakout-like video game seemed the best fit for me. I chose to [open source it](https://github.com/matiasbeckerle/perspektiva). If it helps you, please use it.

## Numbers

[PERSPEkTIVA](http://matiasbeckerle.itch.io/perspektiva) was released only a week ago but here they are. Take into account the video game wasn't really exposed.

- 222 [itch.io](http://itch.io/) store views.
- 47 downloads.
- 2 Linux, 1/5 Mac, mayority Windows. I can't be precise because I released two different versions and I lost the first numbers.

## Timing

I finished the whole gameplay within the first two or three weeks. The remaining time was aesthetics, sound, music, effects, polish, testing and publish-related tasks. This point is interesting because I didn't expect more time doing polishing than the gameplay.

- First commit: 2015-08-17
- [1.1.0 version](http://matiasbeckerle.itch.io/perspektiva): 2015-11-02

## What went right

1. **The final result is nice.** Yeah, I'm glad of what I achieved. It is not perfect but it feels funny and enjoyable. I finished the game which it was the whole sense of making it.

2. **Round two for aesthetics.** Everyone who knows me know that I can't draw a single pixel. At the beginning the video game had another set of colors and aesthetics in general. Luckily at some point I decided to spend more time on it. The final result is prettier than before, I know is not a big deal but... was made by a programmer (doesn't look so bad, right?).

3. **The worst bug lead me to an interesting mechanic/feature**. At an early stage you couldn't go for slow motion and shoot the ball to a random location after releasing a button. The truth is that I was trying to fix the worst bug where the ball doesn't bounce as expected. Once the player enters in that mode the game turns boring. I though: "Ok what will happen if the player has the possibility of apply a random force to the ball?" Then the feature was born.

4. **Music.** I had the luck of finding an amazing artist as [Secheron Peak](http://secheronpeak.bandcamp.com/) who gave an entire album under the Attribution-NonCommercial-NoDerivs 3.0 Unported license. I strongly recommend to listen the whole [Slow Gravity](http://secheronpeak.bandcamp.com/album/slow-gravity) album. I think the music fits amazingly with the aesthetics of [PERSPEkTIVA](http://matiasbeckerle.itch.io/perspektiva).

5. **Platform support**. The video game seems running nice on Windows, Linux and Mac. All the credit goes to [Unity](https://unity3d.com/), I almost didn't make anything.

6. **Unexpected help/promotion.** I didn't exposed the video game through specialized magazines, forums, websites, youtubers or ads. But I made a few publications on social networks and dev forums. It was nice to see people retweeting or talking. Thanks to everyone of you, I really appreciate that.

## What went wrong

1. **Bugs.** There were 3 important bugs. The worst was the one I already told in the "what went right" part of the post. The second is still happening I believe. It is really weird and I can't reproduce it. I think it could give a bad impression to anyone who discovers it. The third one was about performance. I took all the considerations to make the video game really fast and to work nicely on slower machines. I even used the profiler. Everything seemed really good until I noticed an unexpected FPS drop on the ball camera in computers without graphic cards. I thought it was related with that at first. I launched the game knowing it. Then I decided to review it again and there it was! An unwanted setting in the ball camera. Lesson learned: if you know something is wrong, don't discard it quickly as it is the fault of something/someone else.

2. **Testing.** I didn't make any exhaustive testing, specially on Linux and Mac. Mostly because I develop on and use Windows. Tests were through friends. Thanks to all of you! Lesson learned: for the next project I will try to have some virtual machines at least.

3. **Announcement error**. I was preparing a post for [Indie DB](http://www.indiedb.com/) but I misunderstood the platform. Almost 300 visits saw the announcement one week before the release, without the possibility of playing the game. Lesson learned: I don't know... the UI of the platform didn't indicate properly what will happen. I guess I didn't see something important and it was my fault.

## Conclusion

Seeing this in retrospective I can say that it was a complete success! At least in what involves to complete my objectives. I learned a lot and that was the whole point.

* Art is more important of what I thought. Basically, without artists you can't make anything. I could handle [PERSPEkTIVA](http://matiasbeckerle.itch.io/perspektiva) without an artist for graphics because I used primitive figures with solid colors (no textures). But what about my next game? I'm in trouble.

* When I started adding effects everything becomes more delightful. I think it is because you start to feel the game is almost complete, so you want to play it entirely, share it.

* It is not everything about doing the game. You will need time to test it, write about it, prepare animated GIFs, get feedback, etc.

* Being a solo dev is hard. Everything demands you time and it becomes worse when you have a full-time job. Things could go wild. I spent the majority of the development time on weekends. At some point you got obsessed... it is a strange feeling. Like if you only want to spend time doing your game. That is good and bad at the same time. Good because you love the game, you trust on it. Bad because makes you an outsider and you stop taking care of other stuff. You need to balance your life.

---

[DOWNLOAD & PLAY](http://matiasbeckerle.itch.io/perspektiva)

[SOURCE CODE](https://github.com/matiasbeckerle/perspektiva)
