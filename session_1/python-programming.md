# [](#the-if-statement)The If Statement

Any interesting program will have to make decisions. An autonomous car
for example should only drive **if** there is no pedestrian in front.
A weather app should display different images depending whether it rains,
it's sunny or it snows.
In python, these decisions are made using an if statement:

```python
a = 4
b = 2
if a > b:
    biggest = a
else:
    biggest = b
```

There can also be more than two cases:

```python
age = 19  # in a real program this would be user input
if age < 10:
    message = "Where are your parents?"
elif age < 21:
    message = "You can't enter this casino."  # do you see why we use " here?
else:
    message = "You can enter!"
```

In python, `elif` is short for "else if".
The if statement takes a truth value `True` or `False` and executes
the following lines if the value is `True`. Which lines belong to the if
statement is determined by the indentation.

```python
message = 'True is False'
if True:  # this if statement has no use
    message = 'True is True'

# at this point the message will always be 'True is True'
```

```python
# You can also save truth values. The type of these variables is called bool.
>>> age = 41
>>> is_adult = age > 18
>>> is_adult
True

>>> if is_adult:
        message = 'You are adult'
>>> message
'You are adult'
```

In
[this program](/editor/editor.html?n=U2FsdGVkX1%2FE9e8Ygapbt4tO9Kklt89tB%2BzDD6kyvyU%3D&c=U2FsdGVkX1%2B8IuLRAoGJS2cX%2FsCRtMZeluUmn7xjCnKqAO8IampjcrGI8rmB4f%2FH&s=U2FsdGVkX1%2F3ZxQ0hF4z2qWE2LXtWNzLGEDG8DAOArGwrd9%2B78pwBpijODLrXQM6%2Bpmv0Vs18Oq966FKo21MwCJpbNBUv2uMpVFdxRfHerwFKKZ%2B6hLt6MCsZnlMF%2Fylts1L6Vjg7bDny%2F8U7m6rmxMmV0FQcG%2BaJNtaB6Vw6rO2r62T985b8JJ8ncpsgeRxaz%2B11Tw683zFUwqiZlvPUK53Gbxms5oEnlXqh8vnSZM4TCd3o71qXzORAIIW5EwM6FDSqwGozyJx8ZcMluC9AWJTxRj1rcUfackTy9AAmwh%2FvCYgGGIm8L9za1M8l9uNKk1rrXN0WJaYFHp%2FYxODlBBn5YK%2BNaxL3wZrGKAkxCYFjSt%2FrQfmhywCWf5usOxQ65RLHLWyPetY1W2cjudFCcVKCq6tJpjXjXWbPJuku%2BW6G4q5PrfQ8dRj%2BuFfhTnMwC5ik5BZVNmXi04giHN%2FqU9VJc3gxrnbJbgjdIfR9o5dzte9RA3QG6Up%2FPmscwlbKhF7qeVINWGaYYHk0Jk5q3Q4mpNwLEfjcCEKhN1Fi0XcUayzMY4qCoG8clVlWkyYHupwNcs%2FTdI0p0rBtxbr%2F%2Bgi%2Ft0FHzgA6pTAtvSyp0RNZjSE0Fy5h%2FgheBdddJ1EYdFLL0fZr30%2FOGS3i70uH%2BzWEqHFhZgWlHRopaQ8qMsXVaZq12OknnzlZWn0LfbeZ683XRip9u2thjDl52jGGlzW5K%2FJd%2BoZmjXumtME98M%3D&h=),
your task is to create a message given the number of times button A was pressed.
Can you make the message different depending on whether the button was pressed?

If there are multiple or more complicated expressions, you can compute
new bool values using the keywords `not`, `and`, `or`:

```python
>>> not True
False
>>> not False
True

>>> adult = True
>>> rich = False
>>> adult and rich
False
>>> not rich
True
>>> adult or rich
True
```

Is there any way you can rewrite your micro:bit program from before using
these keywords? The path to mastering programming is trying things out!
Don't worry about making mistakes because that is how you will learn!

# [](#loops)Loops

In almost every program it is important to repeat a task. The way to do this is
with loops. In python there are two kinds of loops:
- the `while` loop for doing something while a condition is true
- the `for` loop to do something for each item in e.g. a list

## [](#the-while-loop)The While Loop

Here is a basic example constructing a list of numbers from 0 up to 9

```python
numbers = []

i = 0
while i < 10:
    numbers.append(i)
```

In the previous programs for the micro:bit you might have seen this expression:

```python
while True:
    # some other code
```

This is called an infinite loop. It is never going to stop repeating the
content because the condition is always satisfied (i.e. true).

Test your understanding with
[this micro:bit program](/editor/editor.html?n=U2FsdGVkX191CgpVuBApN2xHOTuic%2F46w8AnG7I5YN4%3D&c=U2FsdGVkX19y88p%2F5hRmg%2Fz%2Bu6XpGym9whIh5nNcCEn1gtKTs4s%2Bp2ZCxhmD7dq7&s=U2FsdGVkX18E1dmnzy9QPN8IwleJDfXbGAreidQh7L8y72uaF7ICKgfXabxBe9LlEmIFMfrFm9DEZPKQzlhlWodnEE2HyBd%2Bi4Xa3GxplUzLKp378BcOZZ0eu8KM5cj1CKgerukXUc2SyYfcrOaXBMK8MTP6FEoGUKKcBnzE%2Fsx0O1OISJBvxeLnIbhfuD2gy9Rc7WgsXYpa9cdLEYr5neFMBVjjJmLvybMBe8yCwH0IPGoLk5yCZHHQYzdrw%2F58lbo7z3JBRUj%2B8FLHzbhPU5qzMF7gPL64CWXiISWwAu%2F7LYD06Y5SAP1WsiYRzAr3I06GWitefd892IS5G7lxZsBLqJuOs3nQaLECkGZzllpAthcJKZhk20RSG9kXUKyJtKVk4qCMRTKSMUNIr%2FAKwFh8f%2Fio49BEzoZV9Edo%2BVgjbsPIa5S9G7JEW7xMRboSGPKWJ8gmZP2ZMjFCqA0x%2FRAInBEKbN%2BeOm8Ib%2FuDShsizH0dbcFjYMiLZ%2Fptz3tgQr%2FjmDFoqoQXiK%2FS3H76NUd9IMmAWXa0trX08LwThmkSvoRjYNWCEKPvpP0VAc%2BwF0hRdO3e9SnJj4WEWZ7PiNH8%2BmsqVldTFOGrRgIsFad%2B552diEWtbYPVhBwoaxyuaxqGt6lcspBXPihMNP38SsOMw3Q4WDc8oNYAtfKBCXpj8UoJbeUmQ6ZioNoJ5SncXsJqonMEeYaYki1AN%2FRHCb2KngZ6a3GAJSNqP9i%2B8mYn%2BXkhRO7%2FjcRREpwQ6NEfMxTcSch87XOdr%2FWg0XqdoeFzpDMWbxlSAvmgmu4BxtOodOaitGEuujAECKj6dRmlR8s9ucM0TzvkWIJIAzn9QVjk6VZriXPCgLr2ztc0NmZAniFjL6a%2Bt%2B2wen9ufUo0GdzeGLm1swPDTbL0Auh%2F26wdZjTJpoUo1k6%2B61hyLR5i6O8AkmGAJdnsQL7uwhEjQh2F0%2FqnTEGZniiSxo%2BLMaTPB0l2FQKpRRu6IPJOtOc%3D&h=).

You can use the while loop to go through the indices of a list:

```python
# let us sum up all the numbers in a list
numbers = [1, 12, 42]
total_sum = 0

index = 0
while index < len(numbers):
    total_sum = total_sum + numbers[index]
    index = index + 1  # can also be written as index += 1
```

Most of the time, going through a list will be easier using a for loop, however.

## [](#the-for-loop)The For Loop

The for loop is used to go through all the items in something that is iterable,
like a list. Using it, we can rewrite the last snippet much more efficiently:

```python
numbers = [1, 12, 42]
total_sum = 0

for number in numbers:
    total_sum += number  # the same as total_sum = total_sum + number
```

It is easy to go through a range of numbers using `range`:
- `range(10)` represents the numbers 0, 1, 2, ..., 9
- `range(3, 6)` represents 3, 4, 5
- `range(6, 3, -1)` represents 6, 5, 4

Let's try to sum all the numbers from 1 to 99!

```python
sum99 = 0

for i in range(100):
    sum99 += i
```

Try implementing
[this program](/editor/editor.html?n=U2FsdGVkX184kpoHOk8anEsAqKFBdox%2FONbDU6d%2Fmkg%3D&c=U2FsdGVkX19Ud9i0NgUQNNxgB3adLB5s5iFOwu6f6iYs62VCqank41A0g3ObyGFI&s=U2FsdGVkX19p9aK%2BkkqI%2BXhLbKEB8t9KR4FmRivG6U%2F2OqoLll5XYsRD%2FQowKxqXR4JSHUGOzuExSUM3ggMSpQpCc8Ay17XiNatfin3XdRfh4J8HR3mdLO1BWJu6cT%2BQPRgQZeaC17HLQTi7Po6WpwwLi0caJNMnEx6ECfE5hVSeFSgtj6SDT9bLUGzgbvPODwdHdur014bvGVkV%2Fr3awwVf2TQSXa80TFFvHcRSifelfTsUdkrALqCwe9iqVIHU6EmdDscxvbDSqezfP6tEVwo4y2bMWDHkk7zrxfZ1lShPISZTYEvr4hoofcX4s8q%2FPBQDQEzeJJVnBU%2BesWLWKgCyhwm4A3B%2BJV7mh0T2xo33A7N8787w8FXniVvAFOmpSSkQJopzFrBlEHvap9wayp0n1ezr2FMRDudH7Fuh31cvQqFG5DBcIrJCxYQ5692DdJshCv6Xqcar3V%2FgHAo%2BTuyI2x9%2Fw61iiTqbalo9sl%2F9lEwWvUNVtzioX6XvE39SRBI4ahTJQXZRoOHgl9MfAx1%2Fw7spiN4sue1sCh2RjY5iZhaaj9Ai84Qx3RIaAb3IeYmEsV6Sze3xMPpOEes0N1A%2BXTg%2BJRMYlpIJqvilQMoh1iTN0Bd24l3rRrqwfthxWoRvpldiDZMO62MQ12bPGgsVgQn8Ue6dHiKrgkozhfawfJVLTLTC%2BTk%2FXhUM0DEogm%2FWY3vjJk3IeqpftSEWme0%2BXpfOI1yPMGXg%2Fo8uQvpgkNVXd0I1coU19qQTGbgYq4d8%2BeyHVyV4TSjZOP3f541vF5bHjaiOGW51CL8UiXcwouDPIofxkJaDXWo%2FTBa605ChU3uuX%2F91WHHtNyWLdw%3D%3D&h=),
once for each of the loop types you know!
