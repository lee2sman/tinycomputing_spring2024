---
layout: post
title: Class 10 - New Digital Senses
---

This week:
- palate cleanser
- GPIO
- Artists and the Pi: New Digital Senses
- Intro to camera project

<iframe width="560" height="315" src="https://www.youtube.com/embed/XmwA0YtA60E?si=WvIxwPmS7Hmf9ESt" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>  

The 1-bit Art of Tristan Perich

## GPIO

Raspberry Pis are digital swiss army knifes of computing. They can run any Unix/Linux operating system, and [others](https://www.tomshardware.com/reviews/install-windows-10-on-raspberry-pi,5993.html) as well. 

Let's review the layout of our Pi's hardware.

![Raspberry Pi 3B+ hardware layout](https://i0.wp.com/iot4beginners.com/wp-content/uploads/2018/12/pi-anatomy.png?w=696&ssl=1)

GPIO stands for General Purpose Input Output. The GPIO pins (a collection of 40 sharp pins on your Raspberry Pi) allow you to connect external hardware such as buttons, sensors, power and more. These are hardware additions that go beyond the basic functionality of your out-of-the-box Pi.

26 pins are controllable.

![Pi GPIO pins](https://cdn.shopify.com/s/files/1/0176/3274/files/pinout_595a696c-cc3a-45ef-aef8-987b9f59ce58_large.png?v=1539186287)  

The USB ports are to the right of this above diagram.

Pins interact with the sensors and get data. Output can include buzzers, motors turning, LED blinkings, or a display.

#### A guide to the pins:

The two top left red pins supply 5v power.

The two mustard yellow pins supply 3.3v power. It is always on, so you could leave an LED plugged in to this to indicate that power is on.

The black pins are ground. For all circuits, you connect one side to positive and the other to negative or ground. 

Two white pins are ID EEPROM. These shouldn't be used by you but may be used by any commercial HAT you want to connect.

![Pin labelling](https://i0.wp.com/iot4beginners.com/wp-content/uploads/2018/12/gpiogpio.png?w=625&ssl=1)  

**Note: There are multiple ways to number PINs, depending on the manufacturer or depending on how you want to count (from the top left?). Make sure to double check what pin is really indicated. Different Pis have different pins mappings.**

What can work with the GPIO pins? Any language can access or write to the pins. It's common to use Python, but Processing and now even Javascript, can access the pins. 

IF you don't have the GPIO package installed:

```
sudo apt-get install rpi.gpio
```

#### HATs

HAT stands for *Hardware Attached on Top*. They are essentially add-on boards to the Pi to get additional physical computing capabilities. HATs conform to a [specification](https://github.com/raspberrypi/hats), which means that any board labeled a HAT is guaranteed to work in conjunction with your Raspberry Pi.

There are [dozens](https://www.adafruit.com/category/286) of HATS available, from a [large](https://www.sparkfun.com/categories/396) [number](https://magpi.raspberrypi.org/articles/best-raspberry-pi-hats) of [manufacturers](https://www.pi-top.com/products/pi-top-4).

### Resources for working with GPIO on the Pi

[NodeJS with GPIO](https://www.w3schools.com/nodejs/nodejs_raspberrypi_gpio_intro.asp) - Use Javascript to control the GPIO pins

[Official Raspberry Pi documentation](https://www.raspberrypi.org/documentation/usage/gpio/) on GPIO pins

Processing 3's [GPIO reference](https://processing.org/reference/libraries/io/GPIO.html)

[Intro tutorial](https://projects.raspberrypi.org/en/projects/introduction-to-processing) on using Processing to trigger LEDs on the Pi

[Adafruit tutorial](https://learn.adafruit.com/processing-on-the-raspberry-pi-and-pitft/hardware-io) on using Processing with Pi

Pinout [Diagrams](https://pinout.xyz/#)

Complete [Raspberry Pi tutorials](https://learn.adafruit.com/series/learn-raspberry-pi)

## Artists and the Pi: New Digital Senses 

![Social Media Without The Internet](https://tuangstudio.files.wordpress.com/2018/06/a.jpg?w=671&h=1006)  

> “Social Media without the Internet” is an interactive performance art project, created as an examination of the human sense of touch. The work is created to accompany the research project entitled “Digital Senses,” as a research innovation that examines how a new developing sense –digital sense—is applied to human sense of touch. Social Media without the Internet consists of two mediums: art object and performance. The art object is a tech wearable. Its functions are designed to be operated by hand gestures when people are socializing, i.e. handshaking, hi-fiving, shoulder-tapping, and handholding. The performance is a medium of investigation of the way social media’s interactions can be introduced into the real world. The project encourages people to socialize and invites them to have more intimate interactions with one another.
> These two aspects, the wearable and the live performance, were created to invigorate and inform each other. The interactive part of the wearable functions as a collector to amass data from interactions with participants, while the performance works to make that interaction happen. The wearable is designed as a blazer, an informal suit jacket without matching pants, that looks casual enough to be worn with other street-style clothing. In the gallery setting, there is live video of the jacket wearer and participants interacting streaming on monitors, which represents the broadcast of interaction between users on social media. However, without the Internet, the live stream operates as a “local area network” only.

 
<iframe width="560" height="315" src="https://www.youtube.com/embed/t5FuFI3mdYE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

by Tuang Thongburisute. [additional info](https://tuangstudio.com/portfolio/social-media-without-the-internet/)

### She Bon 

![She Bon](http://shebon.zoness.com/images/main.jpg)

<iframe width="560" height="315" src="https://www.youtube.com/embed/fA3M7fjr60Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

> SHE BON is a collection of wearable augments capable of sensing various forms of the wearer's bio-data as input, in order to indicate their level of arousal with electronic and mechanical devices as output!

> I view SHE BON as my personal suite of amour that enhances my ability to express aspects of my physical state that might be subtle and thus go unnoticed.

by Sarah Petkus. [info](https://hackaday.io/project/158886-she-bon)

### The Cyborg Foundation

<iframe width="560" height="315" src="https://www.youtube.com/embed/NivuCuwZ944" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/vqzek4rv0Wk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

> The Cyborg Foundation is a nonprofit organization created in 2010 by cyborg activists and artists Moon Ribas and Neil Harbisson. The foundation is a platform for the research, creation and promotion of projects related to extending and creating new senses and perceptions by applying technology to the human body.  
*--[info](https://en.wikipedia.org/wiki/Cyborg_Foundation)*

## Next project: Raspberry Pi camera projects

For our next project we will make use of the [Raspberry Pi Camera Module 2](https://www.raspberrypi.com/products/camera-module-v2/), featuring a Sony 8-megapixel sensor. It is compatible with all versions of the Raspberry Pi.

* [Official Camera documentation](https://www.raspberrypi.com/documentation/accessories/camera.html)
* Useful tutorial [Guide to Raspberry Pi Camera V2 Module](https://randomnerdtutorials.com/guide-to-raspberry-pi-camera-v2-module/) from "Random Nerd Tutorials"

Project examples/tutorials:
* [Pi + Teachable Machine (machine learning to identify objects)](https://learn.adafruit.com/teachable-machine-raspberry-pi-tensorflow-camera)
* [Timelapse camera](https://learn.adafruit.com/pi-timelapse)
* [Selfie bot with instant receipt printer](https://learn.adafruit.com/raspberry-pi-selfie-bot)
* [Low light long exposure photography camera](https://learn.adafruit.com/raspberry-pi-hq-camera-low-light-long-exposure-photography)

Not exactly related but may be of use/interest:
* [Simple Raspberry Pi robot](https://learn.adafruit.com/simple-raspberry-pi-robot)

## Homework

Form a team to work on this project.

Review the documentation for the Raspberry Pi camera. View some example projects. Brainstorm a camera project.

Acquire a Raspberry Pi camera and a USB battery pack to power your camera Pi project.

Write down an idea for a camera project. Note any references, links, inspiration, etc.

Bring to class with your parts.
