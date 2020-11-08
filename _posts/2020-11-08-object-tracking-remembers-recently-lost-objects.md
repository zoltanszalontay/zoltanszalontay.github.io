---
layout: post
title: "The role of Object Tracking in a Fever Detector application"
description: "We discuss how an Object Tracker can help the Fever Detector camera whe objects disappear temporarily"
date: 2020-11-08 20:00:00 +0100
author: Zoltán Szalontay
categories: Product
thumbnail: "/assets/images/post-thumbs/object-tracker-1.png"
tags: raspberry tensorflow coral cv
---
## Introduction

In this post we discuss the role of an Object Tracker algorithm and how improve a Fever Detector application.

## Object Tracker

The role of an Object Tracker is to make and maintain associations between bounding boxes found on consecutive video frames.

When one or more objects are found on a video frame, th edetector returns their bounding box. The same happens for the next frame. The problem is that we cannot tell which rectangle on the second frame contains the same object (person, face etc.) that for example the first rectangle on the first frame. We need an algorithm that finds and maintains 1-1 associations between bounding boxes found on the two frames.

One of the most simplistic Object Tracker algorithm is the Centroid Tracker. It simply associates two boxes based on their distance. It supposes that the objects do not move a lot between two frames so obviously, the closest box shows tha same object.

This algorithm has some problems, though:
* It gets confused when two objects get too close.
* It tends to loose objects when they are out of sight for a long time.

For the first problem correlation based trackers may have the solution. The second problem can be handled by fine tuning the Centroid Tracker's parameters:
* maxDisappeared: The number of frames to remember an object. Any time before that the object will still be tracked again.
* maxDistance: Bounding boxes closer than this will be regarded as the same object.

## Demo:

Check out the video that shows the Object Detector in action:
<iframe width="560" height="315" src="https://youtu.be/hqLGBOBQ7_4" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# More information

Adrian Rosebrock posted an [excellent article](https://www.pyimagesearch.com/2018/07/23/simple-object-tracking-with-opencv/) about the Centroid Tracker on his excellent Pyimagesearch.com site.