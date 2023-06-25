# Solving Problems with Built-in Python Types

In order to be proficient in Python, it's crucial to feel at ease working with the fundamental data types provided by the language. In this practical session, we will use these basic types to resolve some automated tests that are currently failing, thereby guaranteeing the proper functioning of the application. By the end of this practical lab, our familiarity with various data types in Python, such as strings, numbers, dictionaries, and lists, should greatly improve.

## Lab objectives:

- Implement *print_todo* function
    - Displays the information about a todo dictionary
- Implement *take_first* function
    - Extracts the first todo from a list and returns both the todo and the shortened list
- Implement *sum_points* function
    - Calculates the sum of the points of two todo arguments

## Scenario

Our current assignment involves developing a todo list application that operates in a terminal environment. The project is still in its initial phase, and one of our colleagues has already written a set of functions that we are required to implement. Our goal is to complete the implementation of the print_todo, take_first, and sum_points functions within the ~/tasker/tasker.py file.

Fortunately, our co-worker has provided documentation for the code using doctest, which means we have a set of automated tests available. These tests will be invaluable in ensuring that our implementations meet the specified requirements.

By the time we've implemented these functions, we'll have proven our knowledge of some of Python's built-in types such as strings, integers, dictionaries, lists, and tuples.

## Instructions

Copy or download the tasker.py file from the ~/tasker directory to your local machine. keep in mind that it was created with doctest, so you can run the tests with the following command:

```
python3 -m doctest tasker.py
```

After running the tests, you'll see that they're currently failing. Your task is to implement the print_todo, take_first, and sum_points functions so that the tests pass.

## Solution

For the first function, we need to implement the print_todo function. As the docstring indicates, this function should print the name and body of the todo task separated by a colon.

```
"""
  3     print_todo takes in a todo dictionary and prints it out
  4     with by separating the `name` from the `body` using a colon (:).
  5
  6     >>> todo = {'name': 'Example 1', 'body': 'This is a test task', 'points': '3'}
  7     >>> print_todo(todo)
  8     Example 1: This is a test task
  9     >>>
 10     """
 ```

To solve this problem, we'll use the print function to display the name and body of the todo dictionary.

```
def print_todo(todo):
    """
    print_todo takes in a todo dictionary and prints it out
    with by separating the `name` from the `body` using a colon (:).

    >>> todo = {'name': 'Example 1', 'body': 'This is a test task', 'points': '3'}
    >>> print_todo(todo)
    Example 1: This is a test task
    >>>
    """
    print(todo['name'] + ': ' + todo['body'])
```
Another solution could be using print and f-strings:

```
def print_todo2(todo):
    """
    print_todo takes in a todo dictionary and prints it out
    with by separating the `name` from the `body` using a colon (:).

    >>> todo = {'name': 'Example 1', 'body': 'This is a test task', 'points': '3'}
    >>> print_todo2(todo)
    Example 1: This is a test task
    >>>
    """
    print(f"{todo['name']}: {todo['body']}")
```

For the second task we need to implement the take_first function. This function should take a list of todo dictionaries and return the first todo dictionary and the remaining list of todos.

```
 13 def take_first(todos):
 14     """
 15     take_first receives a list of todos and removes the first todo
 16     and returns that todo and the remaining todos in a touple
 17
 18     >>> todos = [{'name': 'Example 1', 'body': 'This is a test task', 'points': '3'},
 19     ... {'name': 'Task 2', 'body': 'Yet another example task', 'points': '2'}]
 20     >>> todo, todos = take_first(todos)
 21     >>> todo
 22     {'name': 'Example 1', 'body': 'This is a test task', 'points': '3'}
 23     >>> todos
 24     [{'name': 'Task 2', 'body': 'Yet another example task', 'points': '2'}]
 25     """
 26     return
```
To solve this problem, we'll use the pop method to remove the first todo dictionary from the list and return it along with the remaining todos.

```
 13 def take_first(todos):
 14     """
 15     take_first receives a list of todos and removes the first todo
 16     and returns that todo and the remaining todos in a touple
 17
 18     >>> todos = [{'name': 'Example 1', 'body': 'This is a test task', 'points': '3'},
 19     ... {'name': 'Task 2', 'body': 'Yet another example task', 'points': '2'}]
 20     >>> todo, todos = take_first(todos)
 21     >>> todo
 22     {'name': 'Example 1', 'body': 'This is a test task', 'points': '3'}
 23     >>> todos
 24     [{'name': 'Task 2', 'body': 'Yet another example task', 'points': '2'}]
 25     """
 26     todo =todos.pop(0)
 27     return (todo, todos)
```

For the last task we need to implement the sum_points function. This function should take two todo dictionaries and return the sum of their points.

```
 29 def sum_points(todo1, todo2):
 30     """
 31     sum_points receives two todo dictionaries and returns sum of their `point` values.
 32
 33     >>> todos = [{'name': 'Example 1', 'body': 'This is a test task', 'points': '3'},
 34     ... {'name': 'Task 2', 'body': 'Yet another example task', 'points': '2'}]
 35     >>> sum_points(todos[0], todos[1])
 36     5
 37     """
 38
 39     return int(todo1['points']) + int(todo2['points'])
```


If everything went well, you should see the following output when you run the tests:

```
1 items had no tests:
    tasker
3 items passed all tests:
    2 tests in tasker.print_todo
    2 tests in tasker.sum_points
    4 tests in tasker.take_first
8 tests in 4 items.
8 passed and 0 failed.
Test passed.
```
