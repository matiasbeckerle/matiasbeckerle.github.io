---
layout: post
title: Simplest shield effect in Unity5
tags: [unity, gamedev, tutorial]
---

<p>I was needing a solution for a shield effect and none seems to fit my needs or taste so I started a simple new one. Maybe you will need more complex stuff later but this is enough to start. Something like this:</p>
<video controls>
	<source src="/public/video/simplest-shield-effect-in-unity5/shield-effect.mp4" type="video/mp4">
	Your browser does not support the video tag.
</video>
<h3>A shield GameObject</h3>
<ol>
  <li>Create a <em>sphere</em> 3D object inside your spaceship GameObject.</li>
  <li>Adjust the transform position and scale to fit your spaceship.</li>
  <li>Attach a Rigidbody.</li>
</ol>
<h3>The material</h3>
<ol>
  <li>Create a new material and add it to your new <em>shield GameObject</em>.</li>
  <li>Set <em>Shader</em> to <strong>Standard (Specular setup)</strong>.</li>
  <li>Set <em>Rendering Mode</em> to <strong>Transparent</strong>.</li>
  <li>Select your <em>Albedo</em> color. <strong>Alpha value should be 0</strong>.</li>
  <li>Set <em>Smoothness</em> to <strong>0</strong>.</li>
</ol>
<p>Before step 4 and 5 is a good idea to play with some values in order to get your desired shield style first. Mine is really subtle blue.</p>
<h3>The script</h3>
<p>Add <a href="https://gist.github.com/matiasbeckerle/3126b118c3acfae4dddf">this script</a> inside your new <em>shield GameObject</em>.</p>
<p>Basically, the magic consist in putting the maximum alpha and smoothness when a collision is detected and fade out slowly.</p>
<h3>Conclusion</h3>
<p>Probably are better ideas or solutions to achieve a shield effect but this one seems pretty light and easy. This could be a prefab with some adjustments.</p>
<p>Unity version: 5.0.1f1</p>
<p>Disclaimer: When I check my code after a while it usually sucks. Be careful.</p>
