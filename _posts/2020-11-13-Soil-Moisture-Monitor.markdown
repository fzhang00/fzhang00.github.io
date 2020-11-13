---
layout: default
title: Soil Moisture Monitor
tags: [makecode microbit]
category: Project
---

# Soil Moisture Monitor

This is a multi-week project that intended to introduce the concept of IOT. This week, we will start by make a soil moisture monitor. In up coming weeks, we will explore how we can send our data to remote computer, smart phone, or even the internet through wireless communication. 

Today the technologies we will be using are:

- Analog signal measurement 
- Science concept: electrical conductivity
- Programming technique: List, Plot data
- Math tool: averaging 

This can be a multi-weeks project depending on the progress of the class. 

# GPIO pins on your Microbit

GPIO pins are called General Purpose Input/Output pins. As the name suggests, they can be used to do many things. We've seen them used for outputing sounds. Today we will use them to monitor electrical current. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/EDgdHb0R96I" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

GPIO pins can be used to receive (measure) or output digital or analog signals. 

- Digital means the signal we output or receive are either 0 or 1
    - The button or pin pressed is a digital input. It is either pressed (1) or not pressed (0)
- Analog means the signal we output or receive are variable, can have any value between 0 to 1024 (for our Microbit)
    - The sound going to the buzzer is an analog output.
    - The current we are measuring today is an analog input. 

# Electric Conductivity

Here is a little bit of science on how we can measure soil moisture. This is based on the science of electric conductivity. 

- Many things in our day to day life depends on electricity. Light, TV, computer, just to name a few.
- Electricity can only travel in some materials, such as metal. These are conductive material.
- Material that electricity cannot travel on, are non-conductive materials, such as wood, plastic. 
- What other material are conductive?

Because our household tap water are conductive. We can measure conductivity to determine how moist the soil is. 

    - More water in soil -> more conductive -> higher reading on Pin 0
    - Less water in soil -> less conductive -> less reading on Pin 0

![soil conductivity](/assets/soil_moisture_science.PNG)

We can use the principle of conductivity for lots of application. For example: door alarm, 

# Build the sensor

- Material
    - A large sheet of aluminum foil
    - flower pot with soil
    - Microbit with Battery

1. Take the large sheet of aluminum foil and fold it repeatedly, until it becomes a thick stick. 
2. Cut the stick in half so that you have two sticks. 
3. Insert one stick into the 3V pin of the Microbit
4. The other stick into the P0 pin of the Microbit
5. Poke both sticks into flower pot

# Code

## Get Analog Measurement

Pins blocks can be found in ```Advanced --> Pins```

- To read analog signal from Pin 0, and store it in variable called measurement: 
    ```python
        measurement = pins.analog_read_pin(AnalogPin.P0)
    ```
- To display the variable as a plot on the LEDs, use
    ```python
        led.plot_bar_graph(measurement, 1024)
    ```

## Save Energy

Our first product connects to 3V pin. There are current flowing through the flower pot constantly. This technique uses a lot of electricity, and drain the battery very fast. Let's make a low energy version of this design. 

- Remove the aluminum stick from 3V pin, and put it in P1 pin
- Supply energy to P1 pin only when taking measurement. Like this: 
```python
    pins.analog_write_pin(AnalogPin.P1, 1023) # supply power
    measurement = pins.analog_read_pin(AnalogPin.P0) # take measurement
    pins.analog_write_pin(AnalogPin.P1, 0) # cut power
```

## Handle noise in data
We will continue to practise using List in our code. This time, we will use List to store a few conductivity measurement, and calculate the mean value.

Mean value, can also be called averaged value. The averaged value is good for providing general information about a subject. For example,

    - The average age of a grade 3 class is 8.5 years old. 
    - The average lifespan of a large breed dog is 12 years old
    - The average lifespan of a small breed dog is 15 years old

Because data collected by sensor has noise. ie. if your measurement is normally 700, you could still occasionally get a value of 1000. That number can be called noise. One way to avoid reporting wrong measurement to user, is to take a lot of measurements, then report the average of all your measurements. 

The way to calculate average is 

1. Add up all of your measurements. For example, if we have 10 measurements, and we create a variable ```sum``` to hold the result of this step, then: 

```
sum = measurement_1 + measurement_2 + measurement_3 + ... + measurement 10
```

2. Divide the sum by number of measurement:

```
average = sum / 10
```

### Put it in Code

Putting them together:
```python
# 1. Empty your list
measurement = []
# 2. Take 10 measurement
for i in range(10):
    measurement.append(pins.analog_read_pin(AnalogPin.P0))
# 3. Calculate sum
sum = 0
for i in range(10):
    sum = sum + measurement[i]
# 4. Calculate average:
average = sum/10
```


