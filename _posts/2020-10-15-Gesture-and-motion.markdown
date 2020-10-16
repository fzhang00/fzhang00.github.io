---
layout: default
title: Gesture and Motion
tags: [makecode microbit]
category: projects
---
# Gesture and Motion

Last weekend, I sent out a video demonstrating how to use the Microbit gesture feature to control the Microbit. This week, we will dig deeper to understand what enables these gesture feature. This is achieved through a sensor called accelerometer. 

Did you ever wonder how does your phone know which way you are holding it, and rotate the photo for you? It is by using accelerometer. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/UT35ODxvmS0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Accelerometer has also been used to create context awared toys. For example, this Talkie toy sense the gesture of the stuffy, and produce giggleing sound when it is shaken,  talks "Weee" when it is up side down, etc. 

After this lesson, you will know all the secret of this toy, and you will also be amazed for such a high price tag that the manufactuer put on these sort of toys. At least, I am. LOL. 

![accelerometer built in toy](/assets/acceleronmeter_enriched_toy.png)

## Accelerometer Data

Now let's take a closer look at the Microbit's accelerometer, and learn how we can use these data to determine the gesture of our Microbit. 

First of all, the measure motion in the physical world, which is a 3D world, we need to define a 3D axes: X, Y, and Z

Our Microbit measure acceleration in these 3 axes. 

![Microbit Accelerometer axis](https://microbit-challenges.readthedocs.io/en/latest/_images/microbit_axes.png)

To have a better sense about the axes, let's shake our microbit along each of these axis, and observe the accelerometer reading. Open the project below in your MakeCode, and download the program to your Microbit.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_ce5agr0Vudsj" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

After downloading this program to your Microbit, you will see the ```Show Console Device``` button show up below the Microbit Simulator. Click that, and you will see a page like the image below. This page will show your accelerometer reading in real time. Shake your Microbit along the three axes seperatly and get a feel about accelerometer data. 

![Show accelerometer reading](/assets/show_accelerometer_reading.png)

Here is a little summary of our observation: 

* When we shake along X, we see big violent changes (from -1500 to +1500) on our X plot. Same thing goes for Y and Z. 
* But we also see some activities on the other axes. This is because our motion is not precisely only on one axis. Motion actually happens on all axis, just more or less on certain axis. 

Now let's load another project that's going to give ue the gesture indicator, and showing accelerometer reading at a slower speed:

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_7RjCyfK6J8pu" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

Now we can observed, how Microbit determine gesture from accelerometer data. 

![Determine gesture](/assets/determine_gesture.png)

We can see by sensing axis senes the earth's gravity (which reads about 1000 by the accelerometer), we can determine the orientation of the Microbit. 

However, data is full of noise. And we don't necessarily orient the Microbit perfectly. Therefore we need to set a number range to determine the orientation. Therefore, we will use the following table. 

![Determine gesture](/assets/determine_gesture2.png)

Now, a small in class exercise:

*** 

> Our Task
>
> - Modify the gesture indicator to use our own number to determine gesture
> - For example, use ```z > -1200 and z < -800``` detect screen up gesture
>

***

## Two Weeks Project

*** 

>
> - Create a Halloween theme project. Some ideas could be:
>   - Use any of the sensors we've learned so far: LEDs, light sensors, temperature, accelerometers, button
>   - DIY motion sensitive light up Halloween costume
>   - Halloween decoration
>   - Make Halloween theme Scratch game controlled by Microbit. Download Microbit program here: https://scratch.mit.edu/microbit
>   

***

Here is a light up project example: 
<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_gJ91xFa97CCP" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>


