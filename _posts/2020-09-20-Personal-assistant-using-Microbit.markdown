---
layout: default
title: Make a personal assistant using Microbit, part 1
tags: [makecode microbit]
category: projects
---
# A Simple Personal Assistant, Part 1

We've created a smart night safety light using Microbit last week. Did you know that if we add a few more features to it, it can become a smart personal assistant. Today, we will add temperature monitor and output warning when temperature is low. 

Electronics we will be using today: 

- Light sensor
- Temperature sensor
- Button

*** 

> Our Goal Today
>
> - Improve Night Light by adding Shake Detection
>
> - Add Temperature Measurement to our Gadget

***

## Let's Review

Last week, we make a night safety light, and we used ```while True``` loop to continuously monitoring light sensor level. 

![whileTrue_flowchart_to_code](/assets/whileTrue_flowchart_to_Code.PNG)

We also used ```if...else...``` to make a decision on when to flash LEDs. 

![if_flowchart_to_code](/assets/IF_flowchart_to_Code.PNG)

## Add Feature

### Improve the night light feature

Did you noticed your night light is flashing all night even when you are not on the road? That's a waste of battery, isn't it? Let's make the night light feature even more context awared by adding one more condition:

LEDs will flash only when _light level is low_ **and** _we are walking (Microbit is shaked)._

![flowchart_shake_condition](/assets/2020_09_20_add_shake.PNG)

In Block, you can construct the condition with these block. You need to construct your own conditional statement. 

![add_shake_blocks](/assets/2020_09_20_add_shake_blocks.PNG)

In Python code, the condition can be written as: (update the code to your own variable names)

```python
light_level < 50 and input.is_gesture(Gesture.SHAKE)
```

***

> Our Task: 
>
> * Update your night light design to include the shake detection

***

### Add temperature detection

As the temperature detection is a added feature, and it runs in parallel to the night light feature. Therefore we can append this feature after the light sensing block. We will activate this feature by pressing the button A. 

![flowchart_add_temperature_detection](/assets/2020_09_20_add_temperature_detection.PNG)

***

> Our Task: 
>
> * Add temperature detection and low temperature warning to your code. 

***

### Challenge (Optional)

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

Now our microbit can display temperature reading. Collect a set of temperature data throughout the day and record them into a table like this:

![temperature measurement table](/assets/2020_09_20_temperature_measurement_table.PNG)