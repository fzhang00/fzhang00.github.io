---
layout: default
title: Make a personal assistant using Microbit, part 2
tags: [makecode microbit]
category: projects
---
# A Simple Personal Assistant, Part 2

*** 

> Our Goal Today
>
> - A view on light sensor data
>
> - Improve button pressed detection
>
> - Gesture

***
## 1. Light Sensor Data

We've all experienced in our first project, that the night safety light was flashing LED indoor when we think it was pretty bright. Our microbit decide when to flash LED by comparing to a fix number. This number is called the threshold. How to set a reasonable threshold? That requires us to have some concept about how sensor measures the environment feature. 

Here is are two plots. The first one, I took a Microbit and record the lighting level in my office, and in my backyard from 7am to 8am. Have a look at these data plots: 

![light_level_plots](/assets/light_level_plots.PNG)

As a designer, we often need to collect, and analyze data from our design to build understanding, and improve our design. The night light design is a great example. 

From these data plot, we see that indoor light are not very strong. My office is very bright, but only shows light_level of 30 in our sensor reading. 

For outdoor, at light level of 30, it still feels quite dark, and the Microbit LEDs clearly stands out. Actually it was when I terminate the recording, that I feel the LEDs don't stand out. 

![backyard microbit](https://lh3.googleusercontent.com/KG-3HJWyrM6noQgyhqkkiWGU5m97X1SLq_OaLoneMoljInC1J5WhsQX5KCiRimtqbjo_qGk_2aqCjhkGvdRBLOZdj89dcFNjvNTZyYQdTgO7aVFaWtucBAAISVEmOfgPJkCLYuojQbMRVcD6-2uoux_zpZCKRyZoewVlSCdvn4Ab4RAq3BBTSM0NKh_SBHeRuGW_E0yA5Y4v83D2Gf0BgpA4p_Eg6Krf01cgGcdBeRFrTde9NFIURS66Bna-GukkvU0dyu0GSc8P9y-tK4-ZF5njSRzEhvue5mz2Huotce1bNS7YxUtSh_p9R_NEHDA1zcKS4Ja2kVupUXG649WailU9L1SnTnfqAbl9BtZ58d4dNyTw5yzrsV1I69Tvt5Qod2S0oPV6sMnCpwIDx9fzD6nXEjLRj4mY3wMt4z_5oeIntbgxCJpb-AsegEQVSqd71yPFddnMsjUoDkkzCkjhw1Mg31YQtFqrU5ucfXjvG3n2xSCYFg-Hj3yHOjM-a49hA5AhwKnga7_xVs5ivamWdVwVDm9pjeSwLX_Tjtl0ic_O1ppams-FbD_nDM7CNG7V_HRXr3j9TkvjQsfJbj6cd63_B1muopSgw_u1LP1ZqhPXRvpw9s4mxDtSGcQQA6jJ_7HGLzwqeOyBeY7K897hg5oikWj3SpEt7QdyPxF16sQk6YWjffaI65AACBLInWo=w769-h947-no?authuser=0)

Based on these observation, as a designer, I would keep my light threshold at between 50 to 100. And find an additional way to turn ON or OFF the night light feature. 


## 2. Did our button works? 

### 2. a) Button not responsive when LEDs are flashing

![How program detect button press](/assets/2020_10_01_how_button_work.png)

* Demo in slow motion

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_0tjKU2a1rYfe" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>

### 2/b) Solution: Use Event Handler

Say we have a continuous task of 

1. S1: Flashing LED
2. S2: Check if button A has been pressed
3. S3: Read temperature if button A is pressed

Our program originally follow the upper scenario. Task 1 takes most of the time in each iteration of a loop. The solution is to make our program do the bottom scenario: breaking up the task 1, and check for task 2. 

![concurrency task scheduler](/assets/concurrency.png)

How do we achieve this in our program? The technique is called event handling. To make this happen in MakeCode, we need two components: ```basic.pause()``` and event handler.  See demo program below: 

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_Kjw6dJATmcCA" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>

### 2. c) Update your code with event handler

Block programmer, please join Microbit classroom: https://microbit.org/join

![microbit classroom](/assets/microbit_block_classroom.PNG)

Python programmer, use the usually MakeCode editor, and share screen when necessary. 

*** 

> Task
>
> - Make your temperature reporting feature more responsive by using event handling
>

***

## 3. Add a simple Step Counter 

We would like to continue enriching our personal assistant design. Let's try to add a step counter feature. The step counter uses gesture to detect motion. Here is a quick demo for gesture: 

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_J4Ca43W1k0yA" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>


A step counter counts your steps. It's a good tool to count how much you have exercised. To do that, we will use the gesture **shake**

1. Make a variable called ```step```
2. Add event handler: On ```shake```, increase ```step``` by 1
3. In our ```while True:``` loop, add step number report.

***
> Home Work: 
> 
> - Complete step counter code, or create something of your own with gesture. 
> - Try out your step counter. Does it work? 
> - If you create your own idea, make a video to demonstrate. 
> - Send your work (.hex file or the shared project url), and video) to fzhang00@gmail.com
>
***