---
layout: post
title: "COVID-19 Fever Detector"
description: "We have finished the first module of our Raspberry Pi based Intelligens Edge platform"
date: 2020-08-31 20:00:00 +0100
author: Zoltán Szalontay
categories: Product
thumbnail: "/assets/images/post-thumbs/fever-detector-1.png"
tags: raspi tf coral cv
---
## Introduction

We are very happy to announce that the first module of our AIoT platform, an Intelligent Edge device that detects people, locates their forehead and measures temperature in real-time, is ready for real customer tests.

## Main topic

The primary design principle was to develop a Smart Camera IoT Edge device that runs on the cheapest possible hardware that is needed to perform various real-time Computer Vision related tasks to create business value for customers. The platform we created is modular, so e.g. Fever Detection and People Counter modules may run in parallel, on the same hardware.

The Fever Detector device uses a dual camera system. A traditional USB camera and a FLIR Lepton thermal camera. The images of the two cameras are aligned so that faces are matching, regardless the focal distance, parallax error, rotation or cropping differences.

The device can use a number of correction algorithms:
* Image alignment: After an initial calibration, the two camera images are aligned.
* Temperature correction:
  * The device normalizes measured temperatures to a fixed temperature reference object, called the Black Body.
  * Temperature normalization can work with a variable temperature reference object as well.
* Distance correction: The temperature is corrected based on the predicted distance of the ojects (faces). 

The device can measure temperatures for faces closer than 2 meters.

The software can log the number of people and their temperature. It can send push notifications or e-mail alerts, statuses or life sign messages. Screen capture of video recording is available.

## About the hardware:

![The Smart Camera prototype in its 3D printed box with the Google Coral Edge TPU](/assets/images/in-content/smart-camera-1.jpg){:.img-fluid}

* The device is based on a Raspberry Pi 4B (2GB RAM, 16GB+ SD card or SSD).
* The primary camera is a Raspberry Pi camera. It may be replaced by any USB camera.
* Thermal camera:
  * To measure people's temperature, we use a [FLIR Lepton 3.5 radiometric thermal camera](https://www.flir.com/products/lepton/?model=3.5%20Lepton&_ga=2.62341164.1062001574.1522086040-178603989.1522086040).
  * Resolution is 160x120. It is substantial for situations when less than 10-15 people are visible at the same time. 
  * Capture speed is 9 FPS.
* Computer vision models are run on a Google Coral Edge TPU.
* Optional hardware components:
  * Touch screen/monitor
  * Solar cell and battery for mobile operation

Check out the video that shows the Fever Detector Smart Camera in action:
<iframe width="560" height="315" src="https://www.youtube.com/embed/IU5YGhB-Flg" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Wrap-up

The True Positive Fever Detector Smart Camera detects multiple faces and measures their temperature in real-time.