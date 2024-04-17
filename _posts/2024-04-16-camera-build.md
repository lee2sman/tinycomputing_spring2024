---
layout: post
title: Class 11 - Camera build-out
---

This week:
- camera sensors
- python libraries

## Camera

<iframe width="560" height="315" src="https://www.youtube.com/embed/GImeVqHQzsE?si=WrvV9GY49GUDapbe" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>  
Camera board setup

We have the Camera Module v2 8mb 1080p.

As of 2021 there is new camera firmware, so the currentdriver software is libcamera (instead of the old raspicam and Picamera python library).

There are a number of applications that come with this software. Of particular use for us:

* libcamera-still (still photo capture)
* libcamera-vid (video capture application)

## Setting up camera

1) 

Update the software on our Pi.

```
sudo apt update
sudo apt upgrade
```

2) Test python.

```
python --version
```

Make sure you are running version 3. If not successful, you will need to run python3.

Check to see if you have Picamera2 installed.

```
python -c "import Picamera2"
```

If not, install:

```
sudo apt install python3-picamera2
```

3) Connect camera


![insert camera]({{ site.baseurl }}/assets/img/insert-camera.gif)  
*image from Leigh Johnson, Opensource.com, CC BY SA*

Turn Pi off. Plug in cable in right orientation. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/tHjwx2AQHxU?si=tR_dxbtVbekHOc1P" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

4) TEST it works.

Try running the still photo program from picamera2.

In the command line:

```
libcamera-still -o test.jpg
```

5. Basic python script using Picamera2

```
from picamera2 import Picamera2

picam2 = Picamera2()

picam2.start_and_capture_file("test.jpg")
```

This should take a photo and save to your current directory.

* [More advanced Picamera2 examples](https://raspberrytips.com/picamera2-raspberry-pi/) - See Adjust the camera settings with Python and Create a timelapse in Python on this page
* [Many more picamera2 example scripts](https://github.com/raspberrypi/picamera2/tree/main/examples)

### Adding sound to your python script

* Add sound! You can use pygame library as well to play sounds. Make a shutter press sound for example.

Add the pygame library at the top

```
import pygame
```

In your script you can play a sound:

```
pygame.mixer.music.load("click.wav")
pygame.mixer.music.play()
```

More advanced examples can be found here: 

### Links

* [Raspberry Pi Camera Modules documentation](https://www.raspberrypi.com/documentation/accessories/camera.html#differences-compared-to-raspicam-apps)


### imagemagick, command line image manipulation

imagemagick is command line software to manipulate images. Most things you can do in a graphical image manipulation software, such as Photoshop, GIMP, etc can be done on the command line with imagemagick. You can resize, turn to black and white, dither, convert between formats (jpg to png, to gif, etc), and many more.

* Imagemagick [examples](https://imagemagick.org/script/examples.php)
* [Manipulating Images With ImageMagick Command-Line Tools](https://www.baeldung.com/linux/imagemagick-edit-images) - code examples


### Bash scripting to glue together different programs/functions

```
#!/bin/bash

#let's play a shutter sound, using mplayer
mplayer click.mp3

#take photo
libcam-still -o photo.jpg

# pause 1 seconds in bash
sleep 1

#use imagemagick to turn to black and white
convert photo.jpg -alpha off -threshold 50% output.png 
```

## Camera examples with Raspberry Pi

<video controls>
<source src="https://www.danmacnish.com/img/projects/drawthisvideo.mp4" type="video/mp4">
</video>  
[Dan Macnish - Draw This](https://www.danmacnish.com/drawthis/) - an instant camera that draws cartoons.

[Github repo](https://github.com/danmacnish/cartoonify) with the code.


<iframe width="560" height="315" src="https://www.youtube.com/embed/enTTZEgiqNg?si=Gd-rsPd4y4SK-chq" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[Duckietown](https://duckietown.com/) 


![Real-time object tracking camera with TensorFlow and Raspberry Pi]({{ site.baseurl }}/assets/img/pan-tilt.gif)  
Gif by Leigh Johnson, CC BY SA

[Real-time object tracking camera with TensorFlow and Raspberry Pi](https://opensource.com/article/20/1/object-tracking-camera-raspberry-pi) - on OpenSource.com. 



![Instant camera]({{ site.baseurl }}/assets/img/instant.png)  
Instant camera by Adafruit, [documentation](https://learn.adafruit.com/instant-camera-using-raspberry-pi-and-thermal-printer) - note: this is old and would have to be adapted!

<iframe width="560" height="315" src="https://www.youtube.com/embed/PLE8osLom30?si=I2Qp6IAXTV78Q2KX" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
Digital Toy Camera - [info](https://volzo.de/thing/digitaltoycamera/)

## Homework

1. On-going progress on your Pi group project
2. Final project proposal
3. Weekly log of work toward final project
 - each participant writes up their activity of the week (ideally, write a log every 20 minutes with your activities during that time)
 - photo documentation (which can include screenshots)
 - a writeup that ends with: what didn't work? what are your next steps? 

##### Final Project proposals

1. What is your project concept idea?
2. Who is on your team?
3. What resources will you be using?
4. What are you having trouble with or need help with?
5. What are you planning on doing next?

Your outcome will be due :

- a completed project.
- project building tutorial
- project manual (how to use it)
- weekly logs of your activity and weekly photo documentation

