---
layout: post
title: "People Counter"
description: "The People Counter module of our Smart Camera device is ready"
date: 2020-10-26 20:00:00 +0100
author: Zoltán Szalontay
thumbnail: "/assets/images/post-thumbs/people-counter-1.png"
categories: Product
tags: raspberry tensorflow coral cv
---
## Introduction

We have just released the second module of our Smart Camera Intelligent IoT Edge device, a People Counter.

## People Counter

The People Counter function helps retailers, banks, insurance companies to count their customers and limit the number of people entering their offices. The Smart Camera module detects people and tracks them. It is important to note that the device does this without storing any photos of customers or recognizing them.

The entrance as a yellow boundary line can be specified on the screen. The Smart Camera counts people crossing the line and counts the number of people inside. It can issue an alert when the maximum capacity of the office is reached.

Apart from people, the system can detect and track other types of objects, such as card, bicycles etc. So it can also be used as a traffic counter that counts different types of vehicles separately.

The device uses the same hardware as the one used by our Fever Detector. The only difference is that the People Counter module does not require a thermal camera.

## Hardware

* The device is based on a Raspberry Pi 4B (2GB RAM, 16GB+ SD card or SSD).
* The primary camera is a Raspberry Pi camera. It may be replaced by any USB camera.
* Computer vision models are run on a Google Coral Edge TPU.
* Optional hardware components:
  * Touch screen/monitor
  * Solar cell and battery for mobile operation

Check out the True Positive People Counter Smart Camera in action:
<iframe
  width="560" height="315" 
  src="https://www.youtube.com/embed/MV7yFJw1BPo" 
  frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
</iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/voxTJ1efxxE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Wrap-up

The True Positive People Counter Smart Camera device is easy to deploy. It can continuously detect and track visitors and alerts when the maximum room capacity is reached.