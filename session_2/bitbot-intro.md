# [](#bit-bot)Bit:Bot

## [](#bitbot-module)Bitbot Module
To make the beginning easier, we added a module `bitbot` with some basic
functionality. See the [advanced](#advanced) section
to learn how to write these out manually, using the pins.
```python
import bitbot

# set speed in percent
bitbot.set_speed(-100, -100)  # move back as fast as possible
bitbot.set_speed(0, 40)  # only right motor is on

# read brightness
brightness = bitbot.brightness()  # returns a tuple, e.g. (70.2, 70.1)
brightness_left = brightness[0]  # brightness in percent
```

## [](#buzzer)Buzzer
The buzzer is connected to pin 14.
```python
# make an annoying buzzing sound for 2 seconds
pin14.write_digital(1)
sleep(2000)
pin14.write_digital(0)  # don't forget to turn it off again
```

## [](#line-detection)Line Detection
The line detectors are connected to the same pins as the buttons.
This means you can't use the buttons while connected to the
bit:bot, but it also means line detection is very easy:
```python
# this could be part of a line-following program
if button_a.is_pressed():
    # there is a line on the left, move right
```

## [](#neopixel)Neopixel
There is a dedicated `neopixel` module. The relevant pin is pin 13 and there are
12 pixels in the Neopixel array.
```python
import neopixel

np = neopixel.Neopixel(pin13, 12)
np[3] = (255, 0, 0)  # set pin with index 3 to all red
np.show()  # show the changes that were made
```

## [](#advanced)Advanced

| motor | Direction Pin | Speed Pin |
|:------|:--------------|:----------|
| left  | `pin8`        | `pin0`    |
| right | `pin12`       | `pin1`    |

The direction pins are set to a digital value, `0` for forward, `1` for backwards.
The speed pins are set to an analog value (between 0 and 1023).

- If the motor is going forwards, higher values make it move faster.
- If the motor is set to go backwards, lower values make it move faster.

```python
# move forwards with maximal speed
pin8.write_digital(0)
pin12.write_digital(0)
pin0.write_analog(1023)
pin1.write_analog(1023)

# move backwards with maximal speed
pin8.write_digital(1)
pin12.write_digital(1)
pin0.write_analog(0)
pin1.write_analog(0)
```
