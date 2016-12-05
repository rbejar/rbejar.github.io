---
author: rbejar
comments: true
date: 2014-01-07 16:05:03+00:00
layout: post
link: http://www.rubenbejar.com/2014/01/how-to-overlay-a-3d-model-on-interactive-google-street-view-panoramas/
slug: how-to-overlay-a-3d-model-on-interactive-google-street-view-panoramas
title: How to overlay a 3D model on interactive Google Street View panoramas
wordpress_id: 401
categories:
- Programming
- Research
- Tips
tags:
- three.js
- webgl
---

I have developed a [small example](http://rbejar.github.io/3DMappingExperiments/WebGLTests/StreetViewOverlay_EINA.html) that shows how to overlay a 3D model on interactive Google Street View panoramas using [three.js](http://threejs.org/). The code is available in a [github repository](https://github.com/rbejar/StreetView3DOverlay) with an MIT license.

The example shows a 3D model (a ferris wheel) placed on a parking lot behind my current building at [EINA - Universidad de Zaragoza](http://eina.unizar.es) on a Google Street View panorama. You can change the viewpoint and zoom in and out, and the model keeps its position and rotates as the viewpoint changes. You can also change the panorama, among a fixed set of them, by clicking the spacebar to see the ferris wheel in its place from different points. The panoramas are included via the API offered by Google, but the user interaction (keys, mouse) has been developed for the example.

There are a number of parameters related to the Street View images which have been established by trial-and-error. This means that both the position and orientation of the ferris wheel is not very precise. The method itself is not very precise, as for instance the distortion in the panoramic images is not uniform. I think this will be difficult to make up for, but even in its current state, this code can be useful for different purposes.

It works better with WebGL support in the web browser, but it will automatically fall back to a simpler version if WebGL support is not detected (thanks three.js!). It has been reported to work at least in the current versions of Firefox in Windows, Linux and Mac OS X, Chrome/ium in Linux and Windows and Internet Explorer 10 in Windows.

The code is not a terrible mess, but it is not something to be terribly proud of either ;-)

Have fun!

[![Ferris Wheel on Panorama](http://www.rubenbejar.com/wp-content/uploads/2014/01/Noria1-300x278.png)](http://rbejar.github.io/3DMappingExperiments/WebGLTests/StreetViewOverlay_EINA.html)
