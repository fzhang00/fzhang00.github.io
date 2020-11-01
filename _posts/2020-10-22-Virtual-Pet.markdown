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

You can use my starter project, or create yours from scratch. 

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_LvFWCo1pHMqb" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

1. Initialization

    First step of a program is always initialization. We define some variable and assign initial value to these variable. 

    ![on_start](/assets/Virtual_pet_on_start.png)

2. Count down

    As time passes, our pet gets hungry (health score goes lower over time). If it sits around too long, it would like to go exercise (move score goes lower over time). We will implement a count down to reduce the variable slowly until they are zero.

    ![count down](/assets/Virtual_pet_countdown.png)

3. Define two functions to check health score and move score

    ![check_health](/assets/Virtual_pet_check_health.png)

    ![check_move](/assets/Virtual_pet_check_move.png)

4. Check the pet's status continuously

    We've define the function to do these check. Now we just need to call these functions in loop. 

    ![check pet status](/assets/Virtual_pet_check_status.png)

5. Feed and exercise your pet

    Now what's missing here is a way to feed your pet, and exercise it. 
    
        - When we feed the pet, health score goes up. 
        - When we exercise the pet, move score goes up. 
    
     The pet owner can do these action by pressing a button for feeding, and shaking the microbit for exercise. I will leave these parts to you. There is one tip. 

    *** Keep your event handling type function short. ***

    By event handling function. I mean these ```On Shake```, ```On Button A Pressed``` blocks. These blocks are best used to change variable value, and provide a very short notice, like display a icon for 200ms, or play one tone for 1/8 beat. Making notice too long will block display from other part of your program. 

    *** Also pay attention to keep your variable no bigger than 10. *** 

    This means only increase your variable if it is less than 10. 

    ```Python
    if variable < 10:
        variable = variable + 1
    ```

6. Add your creation
    
    What else do you think a pet would behave. Add your own creation. 

7. Completion
    
    Complete the project by giving your pet a look. It's almost Halloween, so I make a pumpkin. 

    ![Virtual pet complete](/assets/virtual_pet_complete.jpg)

