---
layout: post
title: Simplest shield effect in Unity5
tags: [unity, development, tutorial]
---

I was needing a solution for a shield effect and none seems to fit my needs or taste so I started a simple new one. Maybe you will need more complex stuff later but this is enough to start. Something like this:

<video controls>
	<source src="/public/video/simplest-shield-effect-in-unity5/shield-effect.mp4" type="video/mp4">
	Your browser does not support the video tag.
</video>

## A shield GameObject

1. Create a *sphere* 3D object inside your spaceship GameObject. 
2. Adjust the transform position and scale to fit your spaceship.
3. Attach a Rigidbody.

## The material

1. Create a new material and add it to your new *shield GameObject*.
2. Set *Shader* to **Standard (Specular setup)**.
3. Set *Rendering Mode* to **Transparent**.
4. Select your *Albedo* color. **Alpha value should be 0**.
5. Set *Smoothness* to **0**.

Before step 4 and 5 is a good idea to play with some values in order to get your desired shield style first. Mine is really subtle blue.

## The script

Add the following script inside your new *shield GameObject*:

{% gist 3126b118c3acfae4dddf %}

Basically, the magic consist in putting the maximum alpha and smoothness when a collision is detected and fade out slowly.

## Conclusion

Probably are better ideas or solutions to achieve a shield effect but this one seems pretty light and easy. This could be a prefab with some adjustments.

<p class="message">Unity version: 5.0.1f1</p>
<p class="message">Disclaimer: When I check my code after a while it usually sucks. Be careful.</p>