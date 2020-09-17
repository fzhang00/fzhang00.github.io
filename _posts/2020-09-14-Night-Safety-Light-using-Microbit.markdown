---
layout: default
title: Night Safety Light with Microbit and MakeCode
tags: [makecode microbit]
category: projects
---

# Night Safety Light

Living in Canada year round, we all know  what's like in the winter. Sun goes down by 4-5pm. The street can be dark and slippery. Can we make a wearable device with Microbit to help us be safe in the dark? 

![Dark street](/assets/dark_street.jpg)

## Identify what features do you want? 

- Flashing LED when it's dark.
- Have an on/off button to save power
- Only turn on when walking? 
- Display sensor measurement on button pressed? 

## Features on the Microbit

- Light sensor, range 0 to 255. 0 is complete dark. 255 is super bright.
- Acceleronmeter, tell us if we are moving.
- Buttons, to navigate among features, or turn on/off LED. Typical uses: 
    - When button A is pressed
    - When button B is pressed
    - When button A+B are pressed together

## Let's know the sensors

### LEDs, Light Emitting Diode

LEDs has become very common in our household. Usually the LEDs we saw are light bulb, like this one
![LED light bulb](https://www.premierltg.com/wp-content/uploads/2015/07/LED-bulbs.jpg)

On Microbit they look like these:

![Surface Mount LEDs](https://aws.robu.in/wp-content/uploads/2019/11/Surface-Mount-LED-2-1-314x252.jpg)

Here is short video introduing LEDs by Microbit. [YouTube Microbit LEDs](https://youtu.be/jzwa-HegLk4)

- LEDs are small, effecient, bright, and don't require much power
- LEDs lights up when a one way electrical current pass through it
- When we stop the electrical current, it takes time for the light to go away
    - This time is related to strength of ambient light
    - Microbit measure the time it takes for the LEDs to go out, and use that to estimate ambient light.

Here is another YouTube video that talks about using LED as light sensor. Have a look if you want to know more. They also shows a nice demonstration.
[Sparkfun using LED as light sensor](https://youtu.be/Gv6Ijam6yFY)

### Buttons

## Design our program with flowchart

Before we start writing our code, we should first design our program. Creating a flow chart helps us to reduce bugs in our program, and also make it easier to spot them. We will do this step together in class. 

Here are the basic element of flowchart
![flow chart](/assets/flowchart_element.png)

Below is an example of a simple flow chart
![Project flow chart](/assets/night_light_flowchart.PNG)

## Build our code based on the flowchart design

I will leave it to you to complete this step. 