---
layout: default
title: A collection of reference Projects
tags: [makecode microbit]
category: Summary
---

# Reference Projects

## Send image through radio

Use this code as example to choose an image and sent it to another Microbit. 

You can create more image using the block: Images --> create image

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_6UqE1AWAcMd9" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>

## Count down timer

When time is up, the program play sounds and display heart.

- Press A to restart the timer. 
- Press B to disable timer

To use this in your program, instead of using button, you can also reset and disable timer when certain condition occurs.

Logic: 
```
if timer variable > 0, 
  timer is running. reduce by 1 every loop
if timer variable = 0
  time is up. Sound alarm
if timer variable < 0
  timer disabled. Don't count down and don't make sound.
```
<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_7XXJm15ULM1U" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>

## A more sensitive step counter

The ```on shake``` can only detect jumping. Use this more sensitive step counter to detect walking. You can modify the 1500 here to make the step counter more or less sensitive. 

1500 is call the threshold. Acceleration strength higher than this number is considered a step. 

Note that acceleration strength is always more than 1000, because of the earth's gravity field.

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_imT2TvitCF3F" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>

## Digital Watch

This is a digital watch 

- Press A to set hours
- Press B to set minutes
- Shake to display time

There is a ```text list``` and a ```forever``` loop in the code to demonstrate how to compare time, set off alarm, and disarm alarm. 

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_iKAJFU6VoUhm" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>

## Radio Handshake

This code can be used to send radio invitation and receive response between two Microbits

- Microbit A press button B to send an invitation. 
- Microbit B press button B to accept. Then start variable is set to 1, and game starts. 
- Microbit A can also press button B to start the game itself 
- Control when your game is run using the start variable. You can place the grey ```if...else...``` in your game running block. 
    - For example: Count steps when start is 1.

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_WvkemvEv83d0" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>

## How to calculate averaged value of a set of measurement

This program demonstrate how to calculate average value of a number of measurement. 

There are two ways.

1. Use variable to hold the sum of all measurement, and another variable to count number of measurement. Then mean = total/n

2. Record all measurement in a list, then loop through the list to calculate mean.

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_2jMWV4P20Lx9" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>
