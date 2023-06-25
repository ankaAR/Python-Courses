# Notes About Python

## Built-in Data Types

### 1. Comments

There is no multi-line comment in Python. Use `#` for single line comment.

    # Multy
    # Line
    # Comment

You can use `"""` for multi-line comment, but it is not recommended because it allocates memory for string object.

    """
    Multy
    Line
    Comment
    """

### 2. Strings

A string is a sequence of characters. You can use single quotes or double quotes to represent a string.

    'Hello World'
    "Hello World"

You can use also a triple quote for multi-line string.

    """
    Hello
    World
    """

You can use `\` to escape special characters.

Having single quotes inside single quotes is one case where you need to escape the character.

    >>> Print('Hello \'World\'')
    Hello 'World'

You can do arithmetic operations on strings.

    >>> 'Hello' + 'World'
    'HelloWorld'
    >>>'Hello' * 3
    'HelloHelloHello'

#### 2.1. String Methods

You can use methods to manipulate strings.

    >>> 'Hello World'.upper()
    'HELLO WORLD'
    >>> 'Hello World'.lower()
    'hello world'

If we use find() method, it returns the index of the first occurrence of the substring. If the substring is not found, it returns -1.

    >>> 'Hello World'.find('W')
    6
    >>> 'Hello World'.find('Universe')
    -1

There are many string methods. See [String Methods](https://docs.python.org/3/library/stdtypes.html#string-methods) for more details.

### 3. Numbers

Python has three types of numbers: integers, floating point numbers, and complex numbers.

    >>> 1
    1
    >>> 1.0
    1.0
    >>> 1 + 2j
    (1+2j)

#### 3.1. Arithmetic Operators

Python comes with many built-in arithmetic operators.

    >>> 1 + 2 # Addition
    3
    >>> 1 - 2 # Subtraction
    -1
    >>> 1 * 2  # Multiplication
    2
    >>> 1 / 2 # Division
    0.5
    >>> 1 // 2 # Floor Division
    0
    >>> 1 % 2  # Modulus
    1
    >>> 2 ** 3 # Exponentiation
    8

If you wants to convert a number to a string, you can use str() function.

    >>> str(7.0)
    '7.0'

If you wants to convert back a string to a number, you can use int() or float() function.

    >>> int('7')
    7
    >>> float('7.0')
    7.0

You cannot convert a string to a complex number.

    >>> complex('7.0')
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ValueError: complex() arg is a malformed string

### 4. Boolean

Boolean is a data type that has two possible values: True or False.

    >>> True
    True
    >>> False
    False

There are some behaviors for bool() function.

    >>> bool(0)
    False
    >>> bool(1)
    True
    >>> bool(2)
    True
    >>> bool(-1)
    True
    >>> bool('')
    False
    >>> bool('Hello')
    True

None is a special constant in Python that represents the absence of a value or a null value.

    >>> None # It must be capitalized
    >>> None == None
    True

### 5. Variables

Variables are used to store values. You can assign a value to a variable using `=` operator.

    >>> x = 1
    >>> x
    1

If you want to print a variable, you can use print() function.

    >>> x = 1
    >>> print(x)
    1

You can assign multiple values to multiple variables in one line.

    >>> x, y, z = 1, 2, 3
    >>> print(x, y, z)
    1 2 3

You can assign the same value to multiple variables in one line.

    >>> x = y = z = 1
    >>> print(x, y, z)
    1 1 1

If you assign a new value to a variable, the old value will be overwritten.

    >>> x = 1
    >>> print(x)
    1
    >>> x = 2
    >>> print(x)
    2

If we have a string stored in a variable and an integer stored in another variable, we cannot concatenate them.

    >>> x = 'Hello'
    >>> y = 1
    >>> x + y
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: must be str, not int

### 6. Lists

A list is a collection of items. You can use square brackets to represent a list.

    >>> my_list = [1, 2, 3]
    >>> my_list
    [1, 2, 3]

You can access an item in a list using its index. The index starts from 0.

    >>> my_list = [1, 2, 3]
    >>> my_list[0]
    1
    >>> my_list[1]
    2

If you access an item using an index that is out of range, you will get an error.

    >>> my_list = [1, 2, 3]
    >>> my_list[3]
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    IndexError: list index out of range

One way to get the length of a list is to use len() function.

    >>> my_list = [1, 2, 3]
    >>> len(my_list)
    3

#### 6.1. List Slice

You can use slice to get a sublist from a list.

    >>> my_list = [1, 2, 3, 4, 5]
    >>> my_list[1:3]
    [2, 3]

If you omit the first index, it will start from the beginning.

    >>> my_list = [1, 2, 3, 4, 5]
    >>> my_list[:3]
    [1, 2, 3]

If you omit the second index, it will go to the end.

    >>> my_list = [1, 2, 3, 4, 5]
    >>> my_list[3:]
    [4, 5]

The first index is called start index and the second index is called end index. The  third index is called step. The default step is 1.

    >>> my_list = [1, 2, 3, 4, 5]
    >>> # my_list[start:end:step]
    >>> my_list[1:4:2]
    [2, 4]

If you want to reverse a list, you can use negative step.

    >>> my_list = [1, 2, 3, 4, 5]
    >>> my_list[::-1]
    [5, 4, 3, 2, 1]

Lists are mutable. You can change an item in a list.

    >>> my_list = [1, 2, 3]
    >>> my_list[0] = "a"
    >>> my_list
    ['a', 2, 3]

You can manipulate the list with slices.

    >>> my_list = [1, 2, 3, 4, 5]
    >>> my_list[1:3] = ['a', 'b', 'c']
    >>> my_list
    [1, 'a', 'b', 'c', 4, 5]

#### 6.2. List Methods

There are many methods for lists. The most common ones are append(), insert(), remove(), pop(), and clear().

    >>> my_list = [1, 2, 3]
    >>> my_list.append(4) # Add an item to the end of the list
    >>> my_list
    [1, 2, 3, 4]
    >>> my_list.insert(0, 0) # Insert an item at a given position
    >>> my_list
    [0, 1, 2, 3, 4]
    >>> my_list.remove(0) # Remove the first item with a given value
    >>> my_list
    [1, 2, 3, 4]
    >>> my_list.pop(2) # Remove the item at a given position
    3
    >>> my_list
    [1, 2, 3]
    >>> my_list.clear() # Remove all items
    >>> my_list
    []

### 7. Tuples & Ranges

A tuple is a collection of items. You can use parentheses to represent a tuple.

    >>> my_tuple = (1, 2, 3) 
    >>> my_tuple
    (1, 2, 3)

Tuples are immutable. You cannot change an item in a tuple.

    >>> my_tuple = (1, 2, 3)
    >>> my_tuple[0] = "a"
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: 'tuple' object does not support item assignment

You can add more values using the `+` operator.

    >>> my_tuple = (1, 2, 3)
    >>> my_tuple + (4, ) # You must add a comma after the value to make it a tuple
    (1, 2, 3, 4)

Tuples are useful when you want to group multiple values together.

You can return multiple items from a tuple.

    >>> my_tuple = (1, 2, 3)
    >>> x, y, z = my_tuple
    >>> x
    1
    >>> y
    2
    >>> z
    3

You can pass arguments using a tuple. It is called substitution.

    >>> print("My name is %s %s" % ("John", "Doe"))
    My name is John Doe

Ranges are immutable sequences of numbers. You can use range() function to create a range.

    >>> my_range = range(5)
    >>> my_range
    range(0, 5)

You can convert a range to a list.

    >>> my_range = range(5)
    >>> list(my_range)
    [0, 1, 2, 3, 4]

Ranges has step argument.

    >>> my_range = range(0, 10, 2) # start, end, step
    >>> list(my_range)
    [0, 2, 4, 6, 8]

### 8. Dictionaries

A dictionary is a collection of key-value pairs. You can use curly braces to represent a dictionary.

    >>> my_dict = {"name": "John", "age": 30}
    >>> my_dict
    {'name': 'John', 'age': 30}

You can access a value using its key.

    >>> my_dict = {"name": "John", "age": 30}
    >>> my_dict["name"]
    'John'

If you access a key that does not exist, you will get an error.

    >>> my_dict = {"name": "John", "age": 30}
    >>> my_dict["address"]
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    KeyError: 'address'

Keys are inmutable. You cannot use a list as a key.

    >>> my_dict = {["name"]: "John", "age": 30}
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: unhashable type: 'list'

You can add a new key-value pair to a dictionary.

    >>> my_dict = {"name": "John", "age": 30}
    >>> my_dict["address"] = "123 Main St"
    >>> my_dict
    {'name': 'John', 'age': 30, 'address': '123 Main St'}

You can change the value of a key.

    >>> my_dict = {"name": "John", "age": 30}
    >>> my_dict["name"] = "Jane"
    >>> my_dict
    {'name': 'Jane', 'age': 30}

You can remove a key-value pair from a dictionary.

    >>> my_dict = {"name": "John", "age": 30}
    >>> del my_dict["name"]
    >>> my_dict
    {'age': 30}

You can pop a key-value pair from a dictionary.

    >>> my_dict = {"name": "John", "age": 30}
    >>> my_dict.pop("name")
    'John'
    >>> my_dict
    {'age': 30}

You cannot pop a key that does not exist.

    >>> my_dict = {"name": "John", "age": 30}
    >>> my_dict.pop("address")
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    KeyError: 'address'

You can read a dictionary using a get() method.

    >>> my_dict = {"name": "John", "age": 30}
    >>> my_dict.get("name")
    'John'
    >>> my_dict.get("address") # If the key does not exist, it will return None
    >>> my_dict.get("address", "123 Main St") # You can set a default value
    '123 Main St'

You can get all keys using the keys() method.

    >>> my_dict = {"name": "John", "age": 30}
    >>> my_dict.keys()
    dict_keys(['name', 'age'])
    >>> list(my_dict.keys())
    ['name', 'age']

You can save a dictionary to a variable using the dict() method.

    >>> my_dict = dict(name="John", age=30)
    >>> my_dict
    {'name': 'John', 'age': 30}

You can use the dict() function passing the value pairs as a list of tuples.

    >>> my_dict = dict([("name", "John"), ("age", 30)])
    >>> my_dict
    {'name': 'John', 'age': 30}

Dictionaries are useful when you want to store data in key-value pairs.

## Control Flow

### 1. Conditional and Comparison

Comparison operators are used to compare two values. They return True or False.

    >>> 1 == 1
    True
    >>> 1 == 2
    False
    >>> 1 != 1
    False
    >>> 1 != 2
    True
    >>> 1 > 2
    False
    >>> 1 < 2
    True
    >>> 1 >= 2
    False
    >>> 1 <= 2
    True

Some weird behavior with comparison operators could be confusing.

    >>> 'abc' < 'b'
    True
    >>> 'bac' < 'b'
    False

Operators like in and not in are used to check if a value is in a sequence.

    >>> 1 in [1, 2, 3]
    True
    >>> 4 in [1, 2, 3]
    False
    >>> 1 not in [1, 2, 3]
    False
    >>> 4 not in [1, 2, 3]
    True

Conditional statements are used to execute a block of code if a condition is True.

    >>> if True:
    ...     print("Was True")
    ...
    Was True
    >>> if 1 > 2:
    ...     print("Was True")
    ...
    >>> if 1 > 2:
    ...     print("Was True")
    ... else:
    ...     print("Was False")
    ...
    Was False

You can use elif to check multiple conditions.

    >>> name = "John"
    >>> if len(name) >= 4:
    ...     print("Name is long")
    ... elif len(name) == 4:
    ...     print("Name is 4 characters")
    ... else:
    ...     print("Name is short")
    ...
    Name is 4 characters

### 2. Boolean Logic

Boolean logic is used to combine and manipulate statements that are either True or False.

    >>> bool("")
    False
    >>> not ""
    True
    >>> not 1 > 2
    >>> if not 1 > 2:
    ...     print("no it isn't")
    ...
    no it isn't

Or operator returns the first True value or the last value if none is True.

    >>> 1 or 2
    1
    >>> 0 or 2
    2
    >>> 0 or []
    []
    >>> [] or 0
    0

And operator returns the first False value or the last value if none is False.

    >>> 1 and 2
    2
    >>> 0 and 2
    0
    >>> 0 and []
    0
    >>> [] and 0
    []

    >>> (1 > 2) and print("Hello")
    False
    >>> (1 < 2) and print("Hello")
    Hello

### 3. While Loops

While loops are used to execute a block of code while a condition is True.

    >>> i = 0
    >>> while i < 5:
    ...     print(i)
    ...     i += 1
    ...
    0
    1
    2
    3
    4

You can use keyboard interrupt (Ctrl + C) to stop a while loop.

    >>> while True:
    ...     print("Hello")
    ...
    Hello
    Hello
    Hello
    ^C
    KeyboardInterrupt

Normally you will have a counter variable to keep track of the number of iterations.

    >>> counter = 1
    >>> while counter <= 5:
    ...     print(counter)
    ...     counter += 1
    ...
    1
    2
    3
    4
    5

You can use else to execute a block of code when the condition is False.

    >>> counter = 1
    >>> while counter <= 10:
    ...     if counter % 2 == 0:
    ...         counter += 1
    ...         continue
    ...     print(f"We're counting odd numbers: {counter}")
    ...     counter += 1
    ...
    We're counting odd numbers: 1
    We're counting odd numbers: 3
    We're counting odd numbers: 5
    We're counting odd numbers: 7
    We're counting odd numbers: 9

You can break out of a while loop.

    >>> counter = 1
    >>> while counter <= 10:
    ...     if counter == 5:
    ...         break
    ...     print(counter)
    ...     counter += 1
    ...
    1
    2
    3
    4

### 4. For Statements

For statements are used to iterate over a sequence.

    >>>colors = ["red", "green", "blue", "purple"]
    >>> for color in colors:
    ...     print(color)
    ...
    red
    green
    blue
    purple

You can work with the variable inside the for loop.

    >>> colors = ["red", "green", "blue", "purple"]
    >>> for color in colors:
    ...     if color == "red":
    ...         continue
    ...     elif color == "blue":
    ...         break
    ...     print(color)
    ...
    green

