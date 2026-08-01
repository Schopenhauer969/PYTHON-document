# 🐍 Python — Complete Guide (Beginner to Advanced)

> A complete, hands-on guide to Python — from your first script to decorators, generators, and testing used in real production code.

---

## 📚 Table of Contents

1. [Introduction](#1-introduction)
2. [Prerequisites & Setup](#2-prerequisites--setup)
3. [Your First Program](#3-your-first-program)
4. [Variables & Data Types](#4-variables--data-types)
5. [Operators](#5-operators)
6. [Control Flow](#6-control-flow)
7. [Data Structures](#7-data-structures)
8. [Strings](#8-strings)
9. [Functions](#9-functions)
10. [Comprehensions](#10-comprehensions)
11. [OOP: Classes & Objects](#11-oop-classes--objects)
12. [Inheritance & Polymorphism](#12-inheritance--polymorphism)
13. [Exception Handling](#13-exception-handling)
14. [File I/O](#14-file-io)
15. [Modules & Packages](#15-modules--packages)
16. [Virtual Environments & pip](#16-virtual-environments--pip)
17. [Decorators](#17-decorators)
18. [Generators & Iterators](#18-generators--iterators)
19. [Context Managers](#19-context-managers)
20. [Type Hints](#20-type-hints)
21. [Testing](#21-testing)
22. [Best Practices](#22-best-practices)
23. [Full Example Project](#23-full-example-project)
24. [Resources](#24-resources)

---

## 1. Introduction

Python is a high-level, interpreted, general-purpose programming language known for its clean, readable syntax. It's widely used for web development, data science, automation, AI/ML, and scripting.

**Key facts:**
- Dynamically typed — no need to declare variable types
- Interpreted, not compiled — runs line by line
- Indentation-based syntax (no curly braces `{}`)
- Huge ecosystem: Django/Flask (web), Pandas/NumPy (data), TensorFlow/PyTorch (AI)

---

## 2. Prerequisites & Setup

- No prior coding experience required
- **Python 3.10+** installed
- A code editor: **VS Code**, **PyCharm**

```bash
# Verify installation
python3 --version
```

Expected output (example):
```
Python 3.12.1
```

**Running Python code — two ways:**

```bash
# 1. Run a script file
python3 script.py

# 2. Interactive REPL (great for quick experiments)
python3
>>> print("Hello from the REPL")
```

---

## 3. Your First Program

```python
# hello.py
print("Hello, World!")

name = input("What's your name? ")
print(f"Nice to meet you, {name}!")
```

```bash
python3 hello.py
```

---

## 4. Variables & Data Types

```python
# Variables — no type declaration needed (dynamically typed)
age = 25                    # int
price = 19.99                # float
name = "Sophea"              # str
is_active = True             # bool
nothing = None                # NoneType (Python's "null")

# Checking a type
print(type(age))    # <class 'int'>
print(type(name))   # <class 'str'>

# Multiple assignment
x, y, z = 1, 2, 3
a = b = c = 0  # All three variables get the value 0

# Constants (Python has no true constants — UPPER_CASE is just convention)
PI = 3.14159
MAX_USERS = 100

# f-strings — the modern, preferred way to format strings (Python 3.6+)
greeting = f"My name is {name} and I am {age} years old."
print(greeting)

# Type casting
str_num = "42"
num = int(str_num)      # "42" -> 42
text = str(42)           # 42 -> "42"
decimal = float("3.14")  # "3.14" -> 3.14

# Checking numeric types
print(isinstance(age, int))  # True
```

---

## 5. Operators

```python
# Arithmetic
print(10 + 5)    # 15
print(10 - 5)    # 5
print(10 * 5)    # 50
print(10 / 3)    # 3.333... (true division, always returns float)
print(10 // 3)   # 3  (floor division, discards remainder)
print(10 % 3)    # 1  (modulo/remainder)
print(2 ** 3)    # 8  (exponentiation)

# Comparison
print(5 == 5)    # True
print(5 != 3)    # True
print(10 > 5)    # True

# Logical
print(True and False)  # False
print(True or False)   # True
print(not True)        # False

# Membership operators
print(3 in [1, 2, 3])         # True
print("a" not in "hello")     # True

# Identity operators
a = [1, 2]
b = [1, 2]
print(a == b)   # True  — same VALUE
print(a is b)   # False — different OBJECTS in memory

# Walrus operator (Python 3.8+) — assign within an expression
if (n := len([1, 2, 3])) > 2:
    print(f"List has {n} items")
```

---

## 6. Control Flow

```python
# if / elif / else
score = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
else:
    print("Grade: C or below")

# Ternary (conditional expression)
status = "Pass" if score >= 60 else "Fail"

# match statement (Python 3.10+ — similar to switch)
day = "Monday"
match day:
    case "Saturday" | "Sunday":
        print("Weekend!")
    case "Monday":
        print("Start of the work week")
    case _:
        print("Just another weekday")

# for loop
for i in range(5):          # 0, 1, 2, 3, 4
    print(f"Iteration {i}")

for fruit in ["apple", "banana", "cherry"]:
    print(fruit)

# while loop
count = 0
while count < 3:
    print(f"Count: {count}")
    count += 1

# break and continue
for i in range(10):
    if i == 3:
        continue  # Skip this iteration
    if i == 6:
        break     # Exit the loop entirely
    print(i)

# else clause on loops (runs if the loop completes WITHOUT a break)
for i in range(5):
    if i == 10:
        break
else:
    print("Loop completed without breaking")

# enumerate — get index + value together
for index, fruit in enumerate(["apple", "banana"]):
    print(index, fruit)  # 0 apple / 1 banana

# zip — iterate over multiple sequences together
names = ["Sophea", "Dara"]
ages = [25, 30]
for name, age in zip(names, ages):
    print(f"{name} is {age}")
```

---

## 7. Data Structures

```python
# --- List (ordered, mutable, allows duplicates) ---
fruits = ["apple", "banana", "cherry"]
fruits.append("date")           # Add to end
fruits.insert(1, "avocado")     # Insert at index
fruits.remove("banana")         # Remove by value
popped = fruits.pop()           # Remove and return the last item
print(fruits[0])                 # Access by index
print(fruits[-1])                # Negative indexing = from the end
print(fruits[1:3])               # Slicing: items from index 1 to 2
print(len(fruits))                # Length
fruits.sort()                     # Sort in place
sorted_copy = sorted(fruits, reverse=True) # New sorted list, original unchanged

# --- Tuple (ordered, IMMUTABLE) ---
point = (10, 20)
x, y = point  # Unpacking
# point[0] = 5  # Error — tuples cannot be modified

# --- Set (unordered, unique values only) ---
unique_numbers = {1, 2, 2, 3, 3, 3}
print(unique_numbers)  # {1, 2, 3}
unique_numbers.add(4)
unique_numbers.discard(1)

set_a = {1, 2, 3}
set_b = {2, 3, 4}
print(set_a | set_b)  # Union: {1, 2, 3, 4}
print(set_a & set_b)  # Intersection: {2, 3}
print(set_a - set_b)  # Difference: {1}

# --- Dictionary (key-value pairs) ---
person = {
    "name": "Sophea",
    "age": 25,
    "city": "Phnom Penh"
}
print(person["name"])                # Access by key
print(person.get("email", "N/A"))    # Safe access with a default fallback
person["email"] = "sophea@example.com"  # Add/update a key
del person["city"]                    # Remove a key

for key, value in person.items():
    print(f"{key}: {value}")

print(person.keys())    # dict_keys([...])
print(person.values())  # dict_values([...])

# Nested data structures
users = [
    {"name": "Sophea", "roles": ["admin", "editor"]},
    {"name": "Dara", "roles": ["viewer"]}
]
print(users[0]["roles"][0])  # "admin"
```

---

## 8. Strings

```python
message = "  Hello, Python World!  "

print(message.strip())                 # Remove whitespace from both ends
print(message.upper())                  # "  HELLO, PYTHON WORLD!  "
print(message.lower())                  # "  hello, python world!  "
print(message.strip().split(", "))      # ["Hello", "Python World!"]
print(message.strip().replace("World", "Everyone"))
print(len(message.strip()))              # Length
print(message.strip()[0:5])              # Slicing: "Hello"
print(message.strip().startswith("Hello")) # True
print("Python" in message)                # True (substring check)

# f-strings with expressions and formatting
price = 19.999
print(f"Total: ${price:.2f}")     # "Total: $20.00"
print(f"{'centered':^20}")         # Centered within 20 characters
print(f"{42:05d}")                  # "00042" — zero-padded

# Joining and splitting
words = ["Python", "is", "fun"]
sentence = " ".join(words)           # "Python is fun"
back_to_list = sentence.split(" ")   # ["Python", "is", "fun"]

# Multi-line strings
paragraph = """This is line one.
This is line two.
This is line three."""
```

---

## 9. Functions

```python
# Basic function
def add(a, b):
    return a + b

# Default parameters
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("Sophea"))              # "Hello, Sophea!"
print(greet("Dara", "Hi"))          # "Hi, Dara!"

# Keyword arguments
def create_user(name, age, city="Unknown"):
    return {"name": name, "age": age, "city": city}

user = create_user(age=25, name="Sophea")  # Order doesn't matter with keywords

# *args — variable number of positional arguments
def sum_all(*numbers):
    return sum(numbers)

print(sum_all(1, 2, 3, 4))  # 10

# **kwargs — variable number of keyword arguments
def print_info(**details):
    for key, value in details.items():
        print(f"{key}: {value}")

print_info(name="Sophea", age=25)

# Combining all parameter types
def full_example(required, *args, default="value", **kwargs):
    print(required, args, default, kwargs)

# Lambda functions (anonymous, single-expression functions)
square = lambda x: x ** 2
print(square(5))  # 25

sorted_by_age = sorted([("Sophea", 25), ("Dara", 30)], key=lambda person: person[1])

# Docstrings — document what a function does
def calculate_area(radius):
    """
    Calculate the area of a circle.

    Args:
        radius (float): The circle's radius.

    Returns:
        float: The calculated area.
    """
    return 3.14159 * radius ** 2

print(calculate_area.__doc__)  # Prints the docstring
```

---

## 10. Comprehensions

```python
# List comprehension
squares = [x ** 2 for x in range(10)]
print(squares)  # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# With a condition
evens = [x for x in range(20) if x % 2 == 0]

# With if/else (conditional expression)
labels = ["even" if x % 2 == 0 else "odd" for x in range(5)]

# Nested comprehension (flattening a 2D list)
matrix = [[1, 2, 3], [4, 5, 6]]
flattened = [num for row in matrix for num in row]
print(flattened)  # [1, 2, 3, 4, 5, 6]

# Dictionary comprehension
squares_dict = {x: x ** 2 for x in range(5)}
print(squares_dict)  # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}

# Set comprehension
unique_lengths = {len(word) for word in ["hi", "hello", "hey", "sup"]}

# Generator expression (lazy — computed one item at a time, saves memory)
gen = (x ** 2 for x in range(1000000))
print(next(gen))  # 0 — only computes this one value
```

---

## 11. OOP: Classes & Objects

```python
class Person:
    # Class variable — shared across ALL instances
    species = "Homo sapiens"

    def __init__(self, name, age):
        # Instance variables — unique to each object
        self.name = name
        self.age = age

    def introduce(self):
        return f"Hi, I'm {self.name} and I'm {self.age} years old."

    # __str__ controls how the object looks when printed
    def __str__(self):
        return f"Person(name={self.name}, age={self.age})"

    # __repr__ is for debugging/developer-facing output
    def __repr__(self):
        return f"Person({self.name!r}, {self.age!r})"

    # __eq__ enables comparing objects with ==
    def __eq__(self, other):
        if not isinstance(other, Person):
            return False
        return self.name == other.name and self.age == other.age

# Creating objects (instances)
p1 = Person("Sophea", 25)
print(p1.introduce())   # "Hi, I'm Sophea and I'm 25 years old."
print(p1)                # Uses __str__: "Person(name=Sophea, age=25)"

p2 = Person("Sophea", 25)
print(p1 == p2)           # True — uses our custom __eq__

# Properties — controlled attribute access (getter/setter with clean syntax)
class Circle:
    def __init__(self, radius):
        self._radius = radius  # Convention: leading underscore = "private"

    @property
    def radius(self):
        return self._radius

    @radius.setter
    def radius(self, value):
        if value < 0:
            raise ValueError("Radius cannot be negative")
        self._radius = value

    @property
    def area(self):
        return 3.14159 * self._radius ** 2

c = Circle(5)
print(c.area)     # 78.53975
c.radius = 10     # Uses the setter
print(c.area)     # 314.159

# Class methods and static methods
class MathHelper:
    @staticmethod
    def add(a, b):
        return a + b  # Doesn't need access to the instance or class

    @classmethod
    def from_string(cls, data_string):
        a, b = map(int, data_string.split(","))
        return cls.add(a, b)

print(MathHelper.add(3, 4))                 # 7
print(MathHelper.from_string("10,20"))       # 30
```

---

## 12. Inheritance & Polymorphism

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def make_sound(self):
        return f"{self.name} makes a sound"


class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)  # Call the parent constructor
        self.breed = breed

    # Overriding the parent's method
    def make_sound(self):
        return f"{self.name} barks! (a {self.breed})"

    def fetch(self):
        return f"{self.name} fetches the ball!"


class Cat(Animal):
    def make_sound(self):
        return f"{self.name} meows!"


dog = Dog("Rex", "Golden Retriever")
cat = Cat("Whiskers")

print(dog.make_sound())  # "Rex barks! (a Golden Retriever)"
print(cat.make_sound())  # "Whiskers meows!"

# Polymorphism — treating different types through a common interface
animals = [dog, cat, Animal("Generic Creature")]
for animal in animals:
    print(animal.make_sound())  # Each calls its own version

# isinstance and issubclass
print(isinstance(dog, Animal))    # True
print(issubclass(Dog, Animal))    # True

# Multiple inheritance
class Swimmer:
    def swim(self):
        return "Swimming!"

class Flyer:
    def fly(self):
        return "Flying!"

class Duck(Animal, Swimmer, Flyer):
    def make_sound(self):
        return f"{self.name} quacks!"

duck = Duck("Donald")
print(duck.make_sound())  # "Donald quacks!"
print(duck.swim())         # "Swimming!"
print(duck.fly())          # "Flying!"

# Abstract base classes (enforce a contract on subclasses)
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

# shape = Shape()  # Error — cannot instantiate an abstract class
rect = Rectangle(10, 5)
print(rect.area())  # 50
```

---

## 13. Exception Handling

```python
# try / except / else / finally
def divide(a, b):
    try:
        result = a / b
    except ZeroDivisionError:
        print("Error: Cannot divide by zero")
        return None
    except TypeError:
        print("Error: Both arguments must be numbers")
        return None
    else:
        print("Division succeeded")  # Runs only if NO exception occurred
        return result
    finally:
        print("Division attempt finished")  # Always runs

print(divide(10, 2))  # 5.0
print(divide(10, 0))  # None (with error messages printed)

# Catching multiple exception types together
try:
    numbers = [1, 2, 3]
    print(numbers[10])
except (IndexError, KeyError) as e:
    print(f"Caught: {e}")

# Raising exceptions
def validate_age(age):
    if age < 0:
        raise ValueError(f"Age cannot be negative: {age}")
    return age

try:
    validate_age(-5)
except ValueError as e:
    print(f"Validation failed: {e}")

# Custom exceptions
class InsufficientFundsError(Exception):
    """Raised when a withdrawal exceeds the account balance."""
    def __init__(self, balance, amount):
        self.balance = balance
        self.amount = amount
        super().__init__(f"Cannot withdraw {amount}, balance is only {balance}")

def withdraw(balance, amount):
    if amount > balance:
        raise InsufficientFundsError(balance, amount)
    return balance - amount

try:
    withdraw(100, 150)
except InsufficientFundsError as e:
    print(f"Transaction failed: {e}")
```

---

## 14. File I/O

```python
# Writing to a file (using "with" — automatically closes the file)
with open("notes.txt", "w") as file:
    file.write("Hello, file world!\n")
    file.write("Second line.\n")

# Reading an entire file
with open("notes.txt", "r") as file:
    content = file.read()
    print(content)

# Reading line by line
with open("notes.txt", "r") as file:
    for line in file:
        print(line.strip())

# Reading all lines into a list
with open("notes.txt", "r") as file:
    lines = file.readlines()

# Appending to a file
with open("notes.txt", "a") as file:
    file.write("Appended line.\n")

# Working with JSON
import json

data = {"name": "Sophea", "age": 25, "skills": ["Python", "SQL"]}

with open("data.json", "w") as file:
    json.dump(data, file, indent=2)

with open("data.json", "r") as file:
    loaded_data = json.load(file)
    print(loaded_data["name"])

# Working with CSV
import csv

with open("users.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerow(["name", "age"])
    writer.writerow(["Sophea", 25])
    writer.writerow(["Dara", 30])

with open("users.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        print(row["name"], row["age"])

# Working with file paths (modern, cross-platform way)
from pathlib import Path

path = Path("data") / "users.csv"
print(path.exists())
print(path.parent)
print(path.suffix)  # ".csv"
```

---

## 15. Modules & Packages

```python
# mathutils.py
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

PI = 3.14159
```

```python
# main.py
import mathutils
print(mathutils.add(2, 3))       # 5
print(mathutils.PI)

# Importing specific names
from mathutils import add, PI
print(add(2, 3))

# Importing with an alias
import mathutils as mu
print(mu.subtract(10, 4))

# Standard library modules commonly used
import os
import sys
import random
import datetime
import math

print(os.getcwd())                    # Current working directory
print(random.randint(1, 100))          # Random integer
print(datetime.datetime.now())          # Current date/time
print(math.sqrt(16))                    # 4.0

# Package structure example
# myproject/
# ├── mypackage/
# │   ├── __init__.py
# │   ├── module_a.py
# │   └── module_b.py
# └── main.py

# In main.py:
# from mypackage import module_a
# from mypackage.module_b import some_function
```

---

## 16. Virtual Environments & pip

```bash
# Create a virtual environment (isolates project dependencies)
python3 -m venv venv

# Activate it (Linux/macOS)
source venv/bin/activate

# Activate it (Windows)
venv\Scripts\activate

# Install packages
pip install requests pandas

# Save dependencies to a file
pip freeze > requirements.txt

# Install from a requirements file (e.g. on another machine)
pip install -r requirements.txt

# Deactivate the virtual environment
deactivate
```

```txt
# requirements.txt example
requests==2.31.0
pandas==2.1.4
```

---

## 17. Decorators

```python
import functools
import time

# A basic decorator — wraps a function to add behavior
def log_calls(func):
    @functools.wraps(func)  # Preserves the original function's name/docstring
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__} with args={args}, kwargs={kwargs}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} returned {result}")
        return result
    return wrapper

@log_calls
def add(a, b):
    return a + b

add(3, 4)
# Output:
# Calling add with args=(3, 4), kwargs={}
# add returned 7

# A timing decorator (very common real-world use case)
def timer(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        elapsed = time.time() - start
        print(f"{func.__name__} took {elapsed:.4f} seconds")
        return result
    return wrapper

@timer
def slow_function():
    time.sleep(1)

slow_function()

# Decorators with arguments
def repeat(times):
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            for _ in range(times):
                func(*args, **kwargs)
        return wrapper
    return decorator

@repeat(times=3)
def greet(name):
    print(f"Hello, {name}!")

greet("Sophea")  # Prints the greeting 3 times

# Built-in decorators recap: @staticmethod, @classmethod, @property (see section 11)
```

---

## 18. Generators & Iterators

```python
# A generator function — uses "yield" to produce values lazily, one at a time
def count_up_to(n):
    count = 1
    while count <= n:
        yield count
        count += 1

for number in count_up_to(5):
    print(number)  # 1, 2, 3, 4, 5

# Generators are memory-efficient — values are computed on demand
gen = count_up_to(1000000)
print(next(gen))  # 1 — only this value is computed so far
print(next(gen))  # 2

# A generator expression (compact syntax)
squares_gen = (x ** 2 for x in range(10))

# Practical example: reading a huge file line by line without loading it all into memory
def read_large_file(file_path):
    with open(file_path, "r") as file:
        for line in file:
            yield line.strip()

# Custom iterator class (implementing the iterator protocol manually)
class CountDown:
    def __init__(self, start):
        self.current = start

    def __iter__(self):
        return self  # An iterator returns itself

    def __next__(self):
        if self.current <= 0:
            raise StopIteration
        self.current -= 1
        return self.current + 1

for num in CountDown(5):
    print(num)  # 5, 4, 3, 2, 1
```

---

## 19. Context Managers

```python
# The "with" statement uses context managers to reliably set up/tear down resources
with open("file.txt", "w") as f:
    f.write("Hello")
# The file is automatically closed here, even if an error occurs

# Creating a custom context manager using a class
class DatabaseConnection:
    def __enter__(self):
        print("Opening database connection")
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        print("Closing database connection")
        return False  # False means: don't suppress any exception that occurred

    def query(self, sql):
        print(f"Running query: {sql}")

with DatabaseConnection() as db:
    db.query("SELECT * FROM users")
# Output:
# Opening database connection
# Running query: SELECT * FROM users
# Closing database connection

# Creating a context manager using a generator (simpler, common pattern)
from contextlib import contextmanager

@contextmanager
def timer_context(label):
    import time
    start = time.time()
    print(f"Starting: {label}")
    yield              # Code inside the "with" block runs here
    elapsed = time.time() - start
    print(f"{label} took {elapsed:.4f} seconds")

with timer_context("data processing"):
    total = sum(range(1000000))
```

---

## 20. Type Hints

```python
# Basic type hints (Python 3.5+)
def add(a: int, b: int) -> int:
    return a + b

name: str = "Sophea"
age: int = 25
price: float = 19.99
is_active: bool = True

# Type hints for collections (Python 3.9+ syntax — built-in generics)
def get_names() -> list[str]:
    return ["Sophea", "Dara"]

def get_ages() -> dict[str, int]:
    return {"Sophea": 25, "Dara": 30}

# Optional — value can be the type OR None
from typing import Optional

def find_user(user_id: int) -> Optional[str]:
    if user_id == 1:
        return "Sophea"
    return None

# Union — value can be one of several types
from typing import Union

def process(value: Union[int, str]) -> str:
    return str(value)

# Modern union syntax (Python 3.10+)
def process_modern(value: int | str) -> str:
    return str(value)

# Type aliases
UserId = int
UserName = str

def get_user(user_id: UserId) -> UserName:
    return "Sophea"

# Type hints in classes
class Product:
    def __init__(self, name: str, price: float) -> None:
        self.name: str = name
        self.price: float = price

# Callable type hints (for functions passed as arguments)
from typing import Callable

def apply_operation(a: int, b: int, operation: Callable[[int, int], int]) -> int:
    return operation(a, b)

print(apply_operation(3, 4, lambda x, y: x + y))  # 7

# Checking types statically with mypy (a separate tool, run via CLI)
# pip install mypy
# mypy script.py
```

---

## 21. Testing

```python
# test_math_utils.py — using the built-in unittest module
import unittest

def add(a, b):
    return a + b

def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b

class TestMathUtils(unittest.TestCase):

    def test_add_positive_numbers(self):
        self.assertEqual(add(2, 3), 5)

    def test_add_negative_numbers(self):
        self.assertEqual(add(-2, -3), -5)

    def test_divide_raises_on_zero(self):
        with self.assertRaises(ValueError):
            divide(10, 0)

    def setUp(self):
        # Runs before EVERY test method
        self.sample_data = [1, 2, 3]

    def tearDown(self):
        # Runs after EVERY test method
        pass

if __name__ == "__main__":
    unittest.main()
```

```bash
python3 -m unittest test_math_utils.py
```

**Using pytest (more popular, less boilerplate):**

```bash
pip install pytest
```

```python
# test_math_utils_pytest.py
import pytest

def add(a, b):
    return a + b

def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b

def test_add():
    assert add(2, 3) == 5

def test_divide_by_zero():
    with pytest.raises(ValueError):
        divide(10, 0)

# Parametrized tests — run the same test with multiple inputs
@pytest.mark.parametrize("a, b, expected", [
    (1, 2, 3),
    (0, 0, 0),
    (-1, 1, 0),
])
def test_add_parametrized(a, b, expected):
    assert add(a, b) == expected

# Fixtures — reusable setup for tests
@pytest.fixture
def sample_list():
    return [1, 2, 3, 4, 5]

def test_list_length(sample_list):
    assert len(sample_list) == 5
```

```bash
pytest test_math_utils_pytest.py -v
```

---

## 22. Best Practices

- ✅ Follow **PEP 8** style guide: `snake_case` for variables/functions, `PascalCase` for classes
- ✅ Use f-strings for string formatting instead of `%` or `.format()`
- ✅ Use `with` statements for files, connections, and other resources
- ✅ Write docstrings for public functions, classes, and modules
- ✅ Use type hints for better editor support and self-documenting code
- ✅ Prefer list/dict comprehensions over manual loops when they stay readable
- ✅ Never catch a bare `except:` — always catch specific exception types
- ✅ Use virtual environments per project to isolate dependencies
- ✅ Use `is` for comparing to `None`, not `==` (`if x is None:`)
- ✅ Format code with **Black** and lint with **Ruff** or **Flake8**

---

## 23. Full Example Project

A simple **Contact Book** combining classes, file I/O, JSON, and exception handling:

```python
# contact_book.py
import json
from pathlib import Path
from dataclasses import dataclass, asdict


@dataclass
class Contact:
    name: str
    phone: str
    email: str


class ContactNotFoundError(Exception):
    """Raised when a contact cannot be found by name."""
    pass


class ContactBook:
    def __init__(self, storage_path: str = "contacts.json"):
        self.storage_path = Path(storage_path)
        self.contacts: list[Contact] = self._load()

    def _load(self) -> list[Contact]:
        if not self.storage_path.exists():
            return []
        with open(self.storage_path, "r") as file:
            data = json.load(file)
            return [Contact(**item) for item in data]

    def _save(self) -> None:
        with open(self.storage_path, "w") as file:
            json.dump([asdict(c) for c in self.contacts], file, indent=2)

    def add_contact(self, name: str, phone: str, email: str) -> Contact:
        contact = Contact(name=name, phone=phone, email=email)
        self.contacts.append(contact)
        self._save()
        return contact

    def find_contact(self, name: str) -> Contact:
        for contact in self.contacts:
            if contact.name.lower() == name.lower():
                return contact
        raise ContactNotFoundError(f"No contact named '{name}'")

    def delete_contact(self, name: str) -> None:
        contact = self.find_contact(name)  # Raises if not found
        self.contacts.remove(contact)
        self._save()

    def list_all(self) -> list[Contact]:
        return self.contacts


if __name__ == "__main__":
    book = ContactBook("contacts.json")

    book.add_contact("Sophea", "012-345-678", "sophea@example.com")
    book.add_contact("Dara", "098-765-432", "dara@example.com")

    print("All contacts:")
    for c in book.list_all():
        print(f"  {c.name} — {c.phone} — {c.email}")

    try:
        found = book.find_contact("Sophea")
        print(f"\nFound: {found}")

        book.find_contact("Unknown Person")  # Raises ContactNotFoundError
    except ContactNotFoundError as e:
        print(f"\nError: {e}")
```

---

## 24. Resources

- Official docs: `https://docs.python.org/3/`
- PEP 8 style guide: `https://peps.python.org/pep-0008/`
- Real Python tutorials: `https://realpython.com`

---

<p align="center">
  Made with ❤️ for developers learning Python.
</p>
