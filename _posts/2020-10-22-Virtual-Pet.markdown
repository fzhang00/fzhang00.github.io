---
layout: default
title: Virtual Pet
tags: [makecode microbit]
category: projects
---

# Virtual Pet Project

Last week, we've learn about accelerometer. This week, let's use it in a virtual pet toy creation. In this project, we will also practise:

- Logic
- Event handling
- Function definition
- Music
- Math

Let's get started. 

## Design

As for every project, we will first design what our pet will do, before implementing the code. 

1. Health. A pet need to eat. So we will have a health status for it. 
    - The health variable starts from 10, and count down.
    - Once dropped to 0, the pet dies
    - Health value is limited in 0 to 10. 
    - Pressing button A will feed the pet, and preventing it from dying. 
![pet health](/assets/Lesson5-pet-health.png)

2. Move. Any animal would like to move around. If it doesn't, it will get anxious. 
    - The move variable also starts from 10 and count down. 
    - Once drop below 3, the pet will complaint
    - Boost move by shaking the pet, or flip it up side down. 
![pet move](/assets/Lesson5-pet-move.png)

3. What other feature would you like? 
    - Maybe if it fall down, it will cry? etc. 
    - 
    - 

## Implement

- Python: Start from the starter project. Switch to Python 

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_LvFWCo1pHMqb" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

- Block: head to Microbit classroom [https://microbit.org/join](https://microbit.org/join)


