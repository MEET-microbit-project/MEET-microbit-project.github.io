# [](#python-basics)Python Basics

## [](#numbers)Numbers

Python can be used as a basic calculator,
it supports addition `+`, substraction `-`, multiplication `*`, and division `/`,
but also more advanced operations such as module `%` and exponentials `**`.

To demonstrate how python works, we are going to show some examples.
The python code we enter will begin with `>>>` to distinguish it from the
result that, follows in the line below. Here are some examples with numbers:

```python
>>> 3 + 7
10
```

```python
>>> 3 - 7
-4
```

Of course you can also use decimal numbers:

```python
>>> 7.1 + 3
10.1
```

Often it is useful to add a note in the code so you can later remember what
you did, or to explain your code to others. To do this, you can add a comment
starting with the character `#`. Everything following this character in one line
will be ignored by python.

```python
>>> # This is the first comment (this whole line will be ignored)

>>> 1 + 1  # this is the second comment
2
```

Here are some more examples of calculations in python:

```python
>>> 1 + 2 + 3
6
```

Keep in mind the operation order you know from math!

```python
>>> 6 - 2 / 2
5
```

Division always gives a float as a result.

```python
>>> 6 / 3
2.0

>>> 8 / 5
1.6
```

To get an integer as a result, you can use the operator `//`.

```python
>>> 6 // 3
2

>> 8 // 5  # it always rounds down, discarding any decimal places
1
```

The modulo operator `%` lets you calculate the remainder in a division.

```python
>>> 10 % 6
4
>>> 14 % 6
2
```

This is sometimes useful to determine if a number is even or odd.

```python
>>> 8 % 2  # 8 is even
0
>>> 9 % 2  # 9 is odd
1
```

You can calculate exponentials using `**`:

```python
>>> 2 ** 2
4
>>> 2 ** 3
8
```

## [](#variables)Variables

You can think of a variable as a box. In python, you can put anything you like
into a box (Side note: In some languages there are different boxes for different
things like decimal numbers, integer numbers, etc. In python, however, there is
one box that fits everything which makes it very easy to write. This kind of programming language is called dynamically typed).

![variable as a box](/img/variable.png)

```python
>>> my_number = 42
>>> twenty = 10 + 10  # store your calculations
>>> my_number  # using the variables will return the stored values
42
```

Once you have put a value into a box (i.e. a variable),
you can use it in other calculations. But you can also change
the value of the variable again, even using the old value
currently stored:
```python
>>> my_number - twenty  # you can use the variables in calculations
22
>>> twenty / 2  # and you can freely mix the values and the variables
10.0
>>> twenty = twenty / 2  # change the value of the variable
>>> twenty
10.0
```

Now it's time to try out what you've learned!
Go to [this website](https://goo.gl/UkHtX3) and try out different things 
with the `my_var` variable.
