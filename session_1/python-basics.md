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
5.0

>>> (6 - 2) / 2  # use brackets to change the operation order
2.0
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

![variable as a box](/img/variable.svg)

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

Now it's time to try out what you've learned! Go to
[this website](/editor/editor.html?n=U2FsdGVkX18rFQnuLbYMCsvJW2TgBtMJhZqQ5Z5vP0c%3D&c=U2FsdGVkX1%2F3t%2BqQqoB6xzcrCJgIIjZgb8GJW7i3siqU1OegtLHmM5Vcy91%2BCoNh&s=U2FsdGVkX1%2F7tf1RUkGZTyAofKUNSu2qxOWVE2Bv4ThcHvRO23RBuOVrxGSU8a0wmrEd%2BhCa7X4idHMNhSXLt0UPRLsz1CmoPGp6GvvgDjLuUUvqmyJ2dO661VcGuHhTyRc%2B2skVWc8zIhSmJeSGjm3hro3QtUA2gyQfOF%2FOb3hZJVCt7NmFArYjAiEkR2uPbBxvcI5jVVGIV0mBqAa%2BU3r88MWTkBypACFFnD%2Br%2F3nsEBtMMCxmlN2HBmzDouV79aaMLeVFUzeyDdWksCyKHgmtwpbJJ84DJGbVdG%2FHxqxL1R625tiDOsrPsqEa7Qxj0BjRlQzmVLtkh1R6OC7mtrpVwOrOKmFeDeD9jMNXrA90sB6NjDJ%2B%2BGx6njyDAa0vfTOGyqdSX%2BtBjjGFIUqYgg%3D%3D&h=)
and try out different things with the `my_var` variable.
(The password for this and the following scripts is empty, just click 'Decrypt')

## [](#strings)Strings
In programming, text (a sequence of text characters) is called a string.
To tell python is a string, it has to be enclosed in either single quotation
marks (`'...'`) or double quotation marks (`"..."`). In some languages single quotation marks are reserved for characters but in python you can use them
interchangeably.
```python
>>> 'Hello, World!'
'Hello, World!'
```

Just like numbers, strings can be saved in variables, and you can even use `+`
to add strings together.

```python
>>> name = 'Joe'
>>> name
'Joe'

>>> 'Hello, ' + name + '!'
'Hello, Joe!'
```

Sometimes you want to display a variable that isn't a string. For example,
how could you make a sentence stating the age of Joe? To do this, we must
convert the integer to a string using the `str` expression:

```python
>>> name = 'Joe'
>>> age = 19
>>> name + ' is ' + str(age) + ' years old.'
'Joe is 19 years old.'
```

Why not try this out in the micro:bit program from before? Can you spot where
the number we used before was converted to a string?

# [](#lists)Lists

A list can store a variable number of items.
To create a list, enclose the comma separated values in
square brackets `[]`:

```python
>>> abc = ['a', 'b', 'c']
>>> abc
['a', 'b', 'c']
```

Just like with variables from before, it doesn't matter what types the different
items have, you can freely mix them.

```python
>>> my_favorites = [42, 'pizza']
```

Accessing the items individually is easy if you know their index. Note that the
first item in a list has the index 0!

```python
>>> my_favorites[1]
'pizza'
```

Of course you can use the list item `'pizza'` like any other string variable:

```python
>>> 'My favorite food is ' + my_favorites[1] + '.'
'My favorite food is pizza.'
```

Whenever there is a value written in the code directly, you can also
use a variable instead:

```python
>>> food_index = 1
>>> 'My favorite food is ' + my_favorites[food_index] + '.'
'My favorite food is pizza.'
```

## [](#list-operations) List Operations

If you have two lists, it is easy to put them together:

```python
>>> birds = ['pigeon', 'seagull', 'sparrow']
>>> numbers = [3, 42, 2017]
>>> birds_and_numbers = birds + numbers
>>> birds_and_numbers
['pigeon', 'seagull', 'sparrow', 3, 42, 2017]
```

Lists are mutable.
That means you can change a list by adding or removing elements.

```python
>>> my_list = [1, 2, 'pizza', 'rice']
>>> my_list.append(42)
>>> my_list
[1, 2, 'pizza', 'rice', 42]
>>> my_list.pop(2)  # pop returns the element at the given index and removes it
'pizza'
>>> my_list
[1, 2, 'rice', 42]
```

You can get the length of a list using `len`:
```python
>>> l = [1, 2, 3, 4, 'toast']
>>> len(l)
5
```

# [](#tuples)Tuples

Tuples, like lists, are a structure containing an arbitrary number of elements.
Unlike lists, tuples cannot be changed by adding or removing elements, however
(they are called immutable, strings are immutable too).
Tuples are created by simply enclosing the values in brackets:

```python
>>> coordinates = (11, 52)
>>> coordinates[1]
52
```

There is also no way of adding tuples together. Tuples are meant to contain
only pairs, triplets, etc. of values that belong together in that specific order
(just like coordinates, or a name and an age).
Here is an example of a list containing tuples:

```python
>>> students = [('John', 14), ('Alex', 16), ('Mary', 12)]
>>> students[0]
('John', 14)
```

Since for tuples the length is usually known (as opposed to lists), there
is an easy way how to extract the values:

```python
>>> name, age = students[1]
>>> name + ' is ' + str(age) + ' years old.'
'Alex is 16 years old.'
```

Congratulations! You have finished learning the basic structures in python.
Next, you are going to learn about the fundamental building blocks of
programming in python, that is, how to make your programs do useful, and
more complex things.

Next up: [python programming](python-programming)
