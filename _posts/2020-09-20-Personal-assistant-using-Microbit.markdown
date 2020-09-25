---
layout: default
title: Make a personal assistant using Microbit, part 1
tags: [makecode microbit]
category: projects
---
# A Simple Personal Assistant, Part 1

We've created a smart night safety light using Microbit last week. Did you know that if we add a few more features to it, it can become a smart personal assistant. Today, we will add temperature monitor and output warning when temperature is low. 

Starting Project: https://makecode.microbit.org/_3JHRct4xEiHL

Electronics we will be using today: 

- Light sensor
- [Temperature sensor](https://youtu.be/_T4N8O9xsMA)
- [Button](https://youtu.be/t_Qujjd_38o) 

*** 

> Our Goal Today
>
> - Practise using function
>
> - Add Temperature Measurement to our Gadget

***

## Let's Review

Last week, we make a night safety light, and we used ```while True``` loop to continuously monitoring light sensor level. 

![whileTrue_flowchart_to_code](/assets/whileTrue_flowchart_to_Code.PNG)

We also used ```if...else...``` to make a decision on when to flash LEDs. 

![if_flowchart_to_code](/assets/IF_flowchart_to_Code.PNG)

## Function

We noticed that the code for flashing LED can be used in whenever we want to flash LEDs. So to keep our code neat, let's put this trunk of code into a function. To define a function, click ```Advanced``` then ```Functions``` then ```Make a Function```. Then enter a function name, and add a number input.

![Make function](/assets/make_function.png)

Move your LED flashing code under this function, and call this function when you need to flash LEDs. 

***

> Our Task: 
>
> * Create LED flashing function, and use the function in your code. 

***

## Add temperature detection

As the temperature detection is a added feature, and it runs in parallel to the night light feature. Therefore we can append this feature after the light sensing block. We will activate this feature by pressing the button A. 

![flowchart_add_temperature_detection](/assets/2020_09_20_add_temperature_detection.PNG)

***

> Our Task: 
>
> * Add temperature detection and low temperature warning to your code. 

***

## Challenge (Optional)

We have two button on the microbit, and we has use them to activate at least 3 features:

- When button A is pressed: we used this to measure temperature
- When button B is pressed: 
- When button A+B is pressed: 

Can you add light level reading and compass heading reading display with button B and A+B pressed? 

***

> Our Task: 
>
> * When button B is pressed: show light level.
> * When button A+B is pressed: show compass reading.  

***

## Assignment after class

Now our microbit can display temperature reading. Collect a set of outdoor temperature data throughout the day and record them into a table like this. You do need to leave the Microbit outside for a while (~10 minutes) to read a stable temperature reading. 

![temperature measurement table](/assets/2020_09_20_temperature_measurement_table.PNG)