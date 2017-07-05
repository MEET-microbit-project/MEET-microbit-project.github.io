# [](#python)Python

## [](#modules)Modules

In programming, often times there is a certain set of functions that will
be reused over and over again. One example are the trigonometric functions
`sin` and `cos`. It would be a big waste of time if you would have to
implement them over and over again each time you write a program that uses
them. Instead, python allows you to `import` a set of functions from
a collection of functions, called a `module`. Here is an example of the
`math` module being imported and used:

```python
import math

x = 12
y = math.sin(x)
```

Try using the math module in one of your programs from before!

Sometimes it can be annoying always writing the module name before a function.
In python there is a handy syntax of copying the function names into our
current program:

```python
from math import *

x = 12
y = sin(x)
```

## [](#random)Random
There is another useful python module for generating (pseudo-) random numbers:

```python
import random

# random number between 1 and 6
random_integer = random.randint(1, 6)

my_list = ["left", "right"]
# make a random choice out of a list
random_direction = random.choice(my_list)
```

Use this module to make a random name generator
[in this program](/editor/editor.html?n=U2FsdGVkX1%2F%2BBodHu7idSyH%2BCpyerPeOlQlyCgUuOp0%3D&c=U2FsdGVkX1%2BqWqoIUabuKXKucgOd5SpDoy4mtwUpmKYvIOSfqJGbPcm41idEfGQH&s=U2FsdGVkX19pqsvnWEATaS%2FSBMabGtbJZ8UzJhJ6J%2BcLp8O8GRjplzbVLp0jTSiINWK9gPQQecyPwnv9Mdi8TWGWBQqNWI1ga%2F4ainsa7RiyB%2F3tZO813ICGA%2BeRrKL%2BFDDvF1ldSyopaKQaUVrVRhbpdjBvls%2By7aKpV4G6MQlKtDx8STJNlGCx%2Biz%2BJVIqxrgiM0Wi74BcBvLawsX8D6Wxz3iqLazgvnrZG1WugcnvIuFIgt%2F7QKMTvfjsGb7FPxlaueFM7ydLp4RJhDtJ91CsQrVUq0%2FSiL%2BjONnVtvqDwqLHJHLGRkiq88MR4AhjkSZRrepj2A6TNR0VmqMzSEMVO8st09mAoI81T%2Bhiij6LvWeLjGu%2FP0Uv8aNP%2BXI0d96KmF64%2BumB7%2Flqn%2Bn221i5xC0j1%2BW%2F1v6OGgi0JnMqgKjvN%2FTRNzLDIxt%2F7zDQAy5NpCAl8KBgT58IDXYDuNjrAx9%2FIrspqG4qqrZpFdtJMClrxLlEkBDH5BCp5Jt%2FoJFg%2Bwu5y3FTUvtmIZ%2FOhf8EtcHNJL6Se6xJNLYxm%2BZNt7MDh4Qeh8nAymJWwsSgZHWQhjyD1x77E8Zjp1HODJTGMXyre1mudEsNK99iC2jhbEtdN9hZMdHaYFI3PzVwdlVDeBUZafGnZQ2hUFWeHCw9MXT1YoBaEzLjnByyuCIBd1AdYQLpsHNMjsK7CjT9MR6D%2BKS%2FRbXK5rcrSg2g3xfycSK%2B8uq%2FAY3FCmKpudY%3D&h=).

# [](#micro-bit)Micro:Bit

All functionality is contained in a *module* (in other words a library) with
the name `microbit`.In order to be able to use the microbit-specific functions
below, include this line at the top of your program:
```python
from microbit import *
```
In English, this means *"import everything (*`*`*) from the `microbit` library"*.

### [](#sleep)sleep
Sometimes it is useful to make the micro:bit wait, and do nothing for a while.
You can do this by specifying a time in milliseconds
(there are 1000 milliseconds in each second):
```python
# sleep for 3 seconds
sleep(3000)
```

## [](#display)Display

### [](#scroll)scroll
You can scroll longer strings of text over the display:
```python
display.scroll("Hello, World!")
```

If you want to scroll something other than a string, you must convert it:
```python
a_number = 42
display.scroll(str(a_number))
```

### [](#show)show
Show something statically on the display:
```python
display.show("!")
```

There are a lot of images available from the `microbit` module:
```python
display.show(Image.HAPPY)
```
For a list of available images see
[here](https://microbit-micropython.readthedocs.io/en/latest/tutorials/images.html#images).

You can also show a list of images in a sequence that you have put into a list:
```python
my_images = ["Hello!", 42, Image.YES]
display.show(my_images, loop=True, delay=100)
```

## [](#buttons)Buttons
There are two buttons on the micro:bit, `button_a` and `button_b`.
`button_a.get_presses()` returns the number of times button A was pressed since the the last time this function was called.
```python
while True:
    sleep(2000)
    # show the number of times button B was pressed in the last 2 seconds
    display.show(str(button_b.get_presses()))
```

## [](#input-output-pins)Input / Output Pins
The micro:bit pins are accessible through `pin0`, `pin1`, ..., `pin22`.
```python
# set pin1 to 1 (on)
pin1.write_digital(1)
# set pin0 to 0 (off)
pin0.write_digital(0)

# read digital values
pin_value = pin0.read_digital()  # 0 or 1

# write analog value from 0 (low output) up to 1023 (maximum output)
pin0.write_analog(1023)
# read analog value
pin0.read_analog()  # integer number from 0 up to 1023
```

## [](#music)Music
Music controls are in a separate module called `music`.
```python
import music

music.play(music.NYAN, pin=0, loop=false)
```
A list of available music can be found
[here](https://microbit-micropython.readthedocs.io/en/latest/tutorials/music.html#music).

## [](#accelerometer)Accelerometer
The accelerometer can be used to determine how the micro:bit
is oriented in space.
```python
# a reading of 0 mean the micro:bit is level along this axis
# 1024 is an acceleration of 1g (earth gravity)
reading_x = accelerometer.get_x()
reading_y = accelerometer.get_y()
reading_z = accelerometer.get_z()
```
For more detail and an overview of the axes see
[this article](http://microbit-challenges.readthedocs.io/en/latest/tutorials/accelerometer.html).

### [](#gestures)gestures
The micro:bit automatically detects the following gestures:

```python
"up", "down", "left", "right", "face up", "face down", "freefall", "3g", "6g", "8g", "shake"
```

```python
# returns true if the gesture is currently active
accelerometer.is_gesture("face up")
# indicates whether the gesture was active since last function call
accelerometer.was_gesture("shake")
```

Next up: [introduction to the bit:bot](bitbot-intro.md)
