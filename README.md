# 🐍 Python — មគ្គុទ្ទេសសម្រាប់អ្នកចាប់ផ្តើមរហូតដល់កម្រិតខ្ពស់
> **Python Guide: From Beginner to Advanced**  
> សៀវភៅណែនាំ Python ពីដំបូងរហូតដល់កម្រិតខ្ពស់ — ជាភាសាខ្មែរ 🇰🇭

---

## 📚 តារាងមាតិកា / Table of Contents

- [🌱 Level 1 — មូលដ្ឋានគ្រឹះ / Basics](#-level-1--មូលដ្ឋានគ្រឹះ--basics)
- [🌿 Level 2 — រចនាសម្ព័ន្ធទិន្នន័យ / Data Structures](#-level-2--រចនាសម្ព័ន្ធទិន្នន័យ--data-structures)
- [🌳 Level 3 — មុខងារ & OOP / Functions & OOP](#-level-3--មុខងារ--oop--functions--oop)
- [🔥 Level 4 — កម្រិតមធ្យម / Intermediate](#-level-4--កម្រិតមធ្យម--intermediate)
- [⚡ Level 5 — កម្រិតខ្ពស់ / Advanced](#-level-5--កម្រិតខ្ពស់--advanced)

---

## 🌱 Level 1 — មូលដ្ឋានគ្រឹះ / Basics

### 1.1 លក្ខខណ្ឌប្រតិបត្តិ / Running Python

```bash
# ពិនិត្យ Python version
python --version

# រត់ file
python hello.py

# Python interactive shell
python
```

> 💬 **ពន្យល់:** Python ប្រើ interpreter ដូច្នេះអ្នកអាចសរសេរ code ហើយ run ភ្លាម ឬ save ជា `.py` file ក៏បាន។

---

### 1.2 អថេរ & ប្រភេទទិន្នន័យ / Variables & Data Types

```python
# ចំនួនគត់ / Integer
age = 25

# ចំនួនទសភាគ / Float
price = 9.99

# អក្សរ / String
name = "សុខ"

# Boolean (True/False)
is_student = True

# គ្មានតម្លៃ / None
nothing = None

# ពិនិត្យប្រភេទ / Check type
print(type(age))       # <class 'int'>
print(type(price))     # <class 'float'>
print(type(name))      # <class 'str'>
```

> 💬 **ពន្យល់:** Python គ្មាន `int x = 5` ដូច Java ទេ — គ្រាន់តែ `x = 5` Python ស្វែងយល់ប្រភេទដោយខ្លួនឯង (dynamic typing)។

---

### 1.3 Input & Output

```python
# បោះពុម្ព / Print
print("សួស្ដី ពិភពលោក!")
print(f"ឈ្មោះ: {name}, អាយុ: {age}")

# ទទួលទិន្នន័យពីអ្នកប្រើ / User input
user_name = input("បញ្ចូលឈ្មោះ: ")
print(f"សួស្ដី {user_name}!")
```

> 💬 **ពន្យល់:** `f""` គឺ f-string — ជាមធ្យោបាយងាយស្រួល បញ្ចូលអថេរទៅក្នុងអក្សរ។ `input()` ត្រឡប់ string តែងតែ ដូច្នេះប្រើ `int(input())` ប្រសិនចង់បានលេខ។

---

### 1.4 Operators / ប្រមាណវិធី

```python
# គណិតវិទ្យា
print(10 + 3)   # 13
print(10 - 3)   # 7
print(10 * 3)   # 30
print(10 / 3)   # 3.333...
print(10 // 3)  # 3  (ចែកទាំងស្រុង / floor division)
print(10 % 3)   # 1  (សំណល់ / remainder)
print(2 ** 8)   # 256 (ការ៉េ)

# ប្រៀបធៀប
print(5 > 3)    # True
print(5 == 5)   # True
print(5 != 4)   # True

# តក្ក
print(True and False)  # False
print(True or False)   # True
print(not True)        # False
```

---

### 1.5 លក្ខខណ្ឌ / Conditionals

```python
score = 85

if score >= 90:
    print("A — ល្អឥតខ្ចោះ")
elif score >= 80:
    print("B — ល្អ")
elif score >= 70:
    print("C — មធ្យម")
else:
    print("D — ត្រូវខិតខំ")
```

> 💬 **ពន្យល់:** Python ប្រើ indentation (ចន្លោះ 4 spaces) ជំនួស `{}` — ត្រូវប្រយ័ត្ន! ខុស indent = error ភ្លាម។

---

### 1.6 Loops / ចំណ្លង

```python
# for loop
for i in range(5):
    print(i)  # 0, 1, 2, 3, 4

# for loop លើ list
fruits = ["ក្រូច", "ស្វាយ", "ផ្លែឈើ"]
for fruit in fruits:
    print(fruit)

# while loop
count = 0
while count < 3:
    print(f"ចំណ្លងទី {count}")
    count += 1

# break & continue
for i in range(10):
    if i == 3:
        continue   # រំលង 3
    if i == 7:
        break      # ឈប់នៅ 7
    print(i)
```

> 💬 **ពន្យល់:** `range(5)` ផ្ដល់ `0,1,2,3,4` (មិនរួមបញ្ចូល 5)។ `break` ចេញពី loop, `continue` រំលង iteration នោះ។

---

## 🌿 Level 2 — រចនាសម្ព័ន្ធទិន្នន័យ / Data Structures

### 2.1 List / បញ្ជី

```python
# បង្កើត list
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", True, 3.14]

# Access
print(numbers[0])    # 1 (ចាប់ពី 0)
print(numbers[-1])   # 5 (ចុងក្រោយ)
print(numbers[1:4])  # [2, 3, 4] (slicing)

# Methods
numbers.append(6)        # បន្ថែមមួយ
numbers.extend([7, 8])   # បន្ថែមច្រើន
numbers.insert(0, 0)     # បន្ថែមនៅ index
numbers.remove(3)        # លុប value
popped = numbers.pop()   # លុបចុងក្រោយ ហើយទទួលយក
numbers.sort()           # តម្រៀប
numbers.reverse()        # បញ្ច្រាស
print(len(numbers))      # រាប់ចំនួន

# List comprehension (Python style!)
squares = [x**2 for x in range(1, 6)]
# [1, 4, 9, 16, 25]

evens = [x for x in range(20) if x % 2 == 0]
# [0, 2, 4, 6, ..., 18]
```

> 💬 **ពន្យល់:** List comprehension គឺ Python magic — វាកូដខ្លី ហើយ fast ជាង loop ធម្មតា។ `[expression for item in iterable if condition]`

---

### 2.2 Tuple / ជាអចិន្ត្រៃយ៍

```python
# Tuple — ប្រែប្រួលមិនបាន (immutable)
point = (10, 20)
rgb = (255, 128, 0)

x, y = point   # unpacking
print(x, y)    # 10 20

# Tuple ល្អសម្រាប់ data ថេរ
days = ("ច័ន្ទ", "អង្គារ", "ពុធ", "ព្រហស្បតិ៍", "សុក្រ")
```

> 💬 **ពន្យល់:** Tuple ដូច list ដែរ ប៉ុន្តែ `()` ជំនួស `[]` ហើយ **ផ្លាស់ប្ដូរមិនបាន**។ ប្រើសម្រាប់ data ដែលមិនគួរប្រែ។

---

### 2.3 Dictionary / វចនានុក្រម

```python
# Dictionary — key: value pairs
student = {
    "name": "ដារា",
    "age": 20,
    "grade": "A"
}

# Access
print(student["name"])           # ដារា
print(student.get("age", 0))     # 20 (safe access)

# Edit
student["age"] = 21
student["email"] = "dara@email.com"  # បន្ថែម key ថ្មី

# Methods
print(student.keys())    # dict_keys([...])
print(student.values())  # dict_values([...])
print(student.items())   # dict_items([...])

# Loop
for key, value in student.items():
    print(f"{key}: {value}")

# Dict comprehension
squared = {x: x**2 for x in range(1, 6)}
# {1:1, 2:4, 3:9, 4:16, 5:25}
```

---

### 2.4 Set / សំណុំ

```python
# Set — unique values only, គ្មានលំដាប់
fruits = {"ក្រូច", "ស្វាយ", "ក្រូច"}  # "ក្រូច" នឹងមានតែ 1
print(fruits)  # {'ស្វាយ', 'ក្រូច'}

a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

print(a | b)   # union: {1,2,3,4,5,6}
print(a & b)   # intersection: {3,4}
print(a - b)   # difference: {1,2}
```

> 💬 **ពន្យល់:** Set ល្អសម្រាប់ **លុប duplicate** ហើយ **ពិនិត្យ membership** លឿន — `5 in a` ។

---

## 🌳 Level 3 — មុខងារ & OOP / Functions & OOP

### 3.1 Functions / មុខងារ

```python
# មុខងារ basic
def greet(name):
    return f"សួស្ដី {name}!"

print(greet("ចន្ទ"))

# Default parameter
def greet_with_title(name, title="លោក"):
    return f"សួស្ដី {title} {name}!"

print(greet_with_title("ដារា"))           # សួស្ដី លោក ដារា!
print(greet_with_title("ចាន់ដា", "អ្នកស្រី"))  # សួស្ដី អ្នកស្រី ចាន់ដា!

# *args — ទទួល argument ច្រើន
def add_all(*numbers):
    return sum(numbers)

print(add_all(1, 2, 3, 4, 5))  # 15

# **kwargs — ទទួល keyword argument ច្រើន
def display_info(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

display_info(name="ដារា", age=20, city="ភ្នំពេញ")

# Lambda — មុខងារខ្លី
square = lambda x: x ** 2
print(square(5))  # 25

double = lambda x: x * 2
nums = [1, 2, 3, 4]
print(list(map(double, nums)))          # [2, 4, 6, 8]
print(list(filter(lambda x: x > 2, nums)))  # [3, 4]
```

> 💬 **ពន្យល់:** `*args` ផ្ដល់ tuple, `**kwargs` ផ្ដល់ dict។ Lambda ជា "anonymous function" — ប្រើសម្រាប់ logic ខ្លី។

---

### 3.2 OOP — Classes & Objects

```python
# Class ជា "blueprint" / ប្លង់
class Animal:
    # Class variable — ចែករំលែក
    kingdom = "Animalia"

    # Constructor
    def __init__(self, name, sound):
        self.name = name     # instance variable
        self.sound = sound

    # Method
    def speak(self):
        return f"{self.name} និយាយ: {self.sound}!"

    # String representation
    def __str__(self):
        return f"Animal({self.name})"


# បង្កើត Object
dog = Animal("ឆ្កែ", "ហ៊ូ")
cat = Animal("ឆ្មា", "ម៉ូ")

print(dog.speak())     # ឆ្កែ និយាយ: ហ៊ូ!
print(cat.name)        # ឆ្មា
print(Animal.kingdom)  # Animalia
```

---

### 3.3 Inheritance / ការបន្ត

```python
class Vehicle:
    def __init__(self, brand, speed):
        self.brand = brand
        self.speed = speed

    def move(self):
        return f"{self.brand} ធ្វើដំណើរ"


class Car(Vehicle):  # Car extends Vehicle
    def __init__(self, brand, speed, doors):
        super().__init__(brand, speed)  # ហៅ parent constructor
        self.doors = doors

    def move(self):  # Override
        return f"{self.brand} បើកបរ {self.speed}km/h"

    def honk(self):
        return "ប៉ូ! ប៉ូ!"


class Bicycle(Vehicle):
    def move(self):
        return f"{self.brand} ជិះកង់ {self.speed}km/h"


my_car = Car("Toyota", 120, 4)
my_bike = Bicycle("Giant", 25)

print(my_car.move())    # Toyota បើកបរ 120km/h
print(my_bike.move())   # Giant ជិះកង់ 25km/h
print(my_car.honk())    # ប៉ូ! ប៉ូ!

# Polymorphism
vehicles = [my_car, my_bike]
for v in vehicles:
    print(v.move())  # ហៅ move() ខុសគ្នាតាម class
```

> 💬 **ពន្យល់:** `super()` ហៅ method ពី parent class។ **Polymorphism** — object ខុសគ្នា respond ខុសគ្នា ទៅ method តែមួយ។

---

### 3.4 Encapsulation & Properties

```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.__balance = balance  # private (double underscore)

    @property
    def balance(self):
        return self.__balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            return f"បញ្ចូលបាន ${amount}"
        return "Amount ត្រូវតែធំជាង 0"

    def withdraw(self, amount):
        if amount > self.__balance:
            return "Balance មិនគ្រប់"
        self.__balance -= amount
        return f"ដកបាន ${amount}"


acc = BankAccount("ដារា", 1000)
print(acc.balance)       # 1000 (via property)
print(acc.deposit(500))  # បញ្ចូលបាន $500
print(acc.balance)       # 1500
# acc.__balance = 999999  # ❌ ធ្វើបាន outside class ប៉ុន្តែ bad practice
```

---

## 🔥 Level 4 — កម្រិតមធ្យម / Intermediate

### 4.1 Error Handling / ដោះស្រាយ Error

```python
# try/except
try:
    x = int(input("បញ្ចូលលេខ: "))
    result = 100 / x
    print(f"លទ្ធផល: {result}")
except ValueError:
    print("❌ ត្រូវបញ្ចូលលេខ!")
except ZeroDivisionError:
    print("❌ មិនអាចចែកនឹង 0!")
except Exception as e:
    print(f"❌ Error: {e}")
else:
    print("✅ ជោគជ័យ!")
finally:
    print("👋 រួចរាល់ (ជានិច្ច)")


# Custom Exception
class AgeError(Exception):
    def __init__(self, age):
        self.age = age
        super().__init__(f"អាយុ {age} មិនត្រឹមត្រូវ!")


def validate_age(age):
    if age < 0 or age > 150:
        raise AgeError(age)
    return f"អាយុ {age} — ត្រឹមត្រូវ"


try:
    print(validate_age(200))
except AgeError as e:
    print(e)
```

---

### 4.2 File Handling / ការដោះស្រាយ File

```python
# Write file
with open("data.txt", "w", encoding="utf-8") as f:
    f.write("ជំរាបសួរ Python!\n")
    f.write("ភ្នំពេញ កម្ពុជា\n")

# Read file
with open("data.txt", "r", encoding="utf-8") as f:
    content = f.read()
    print(content)

# Read line by line
with open("data.txt", "r", encoding="utf-8") as f:
    for line in f:
        print(line.strip())

# Append
with open("data.txt", "a", encoding="utf-8") as f:
    f.write("បន្ថែម line ថ្មី\n")

# JSON file
import json

data = {"name": "ដារា", "age": 20, "city": "ភ្នំពេញ"}

with open("data.json", "w", encoding="utf-8") as f:
    json.dump(data, f, ensure_ascii=False, indent=2)

with open("data.json", "r", encoding="utf-8") as f:
    loaded = json.load(f)
    print(loaded["name"])  # ដារា
```

> 💬 **ពន្យល់:** `with open(...)` ជំនួស `f.open()` / `f.close()` — Python close file ដោយស្វ័យប្រវត្តិ (safe)។ `encoding="utf-8"` ចាំបាច់សម្រាប់ Khmer text។

---

### 4.3 Modules & Packages

```python
# ប្រើ built-in modules
import math
import random
import datetime
import os

print(math.pi)             # 3.14159...
print(math.sqrt(16))       # 4.0
print(random.randint(1, 6))  # ជាប់ random 1-6
print(datetime.date.today())  # 2024-01-15

# Import specific
from math import pi, sqrt
from random import choice

fruits = ["ក្រូច", "ស្វាយ", "ចេក"]
print(choice(fruits))  # random fruit

# ដំឡើង package ខាងក្រៅ
# pip install requests pandas numpy
import requests  # HTTP requests
```

---

### 4.4 Decorators / Decorator

```python
import time
import functools

# Basic decorator
def timer(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"⏱️ {func.__name__} ចំណាយ {end - start:.4f}s")
        return result
    return wrapper


@timer
def slow_function():
    time.sleep(1)
    return "រួចរាល់"


@timer
def add(a, b):
    return a + b


print(slow_function())
print(add(5, 3))


# Decorator with arguments
def repeat(times):
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            for _ in range(times):
                result = func(*args, **kwargs)
            return result
        return wrapper
    return decorator


@repeat(3)
def say_hello():
    print("ជំរាបសួរ!")

say_hello()  # print 3 times
```

> 💬 **ពន្យល់:** Decorator ជា function ដែល **"ផ្ដោត"** លើ function ផ្សេង ដើម្បីបន្ថែម behavior ។ `@timer` = `slow_function = timer(slow_function)`

---

### 4.5 Generators & Iterators

```python
# Generator — ផ្ញើ value ម្ដង​មួយ (lazy evaluation)
def count_up(limit):
    i = 0
    while i < limit:
        yield i   # yield ជំនួស return
        i += 1

gen = count_up(5)
print(next(gen))  # 0
print(next(gen))  # 1

for num in count_up(3):
    print(num)   # 0, 1, 2

# Generator expression
squares = (x**2 for x in range(1000000))  # () ជំនួស []
# ប្រើ memory តិចជាង list ច្រើន!

# Fibonacci generator
def fibonacci():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

fib = fibonacci()
for _ in range(10):
    print(next(fib), end=" ")  # 0 1 1 2 3 5 8 13 21 34
```

---

### 4.6 Context Managers

```python
# Custom context manager
class Timer:
    def __enter__(self):
        self.start = time.time()
        return self

    def __exit__(self, *args):
        self.elapsed = time.time() - self.start
        print(f"⏱️ ចំណាយ: {self.elapsed:.4f}s")


with Timer() as t:
    # ដំណើរការ code ណាមួយ
    total = sum(range(1000000))

# contextlib
from contextlib import contextmanager

@contextmanager
def managed_resource(name):
    print(f"🔓 បើក {name}")
    try:
        yield name
    finally:
        print(f"🔒 បិទ {name}")

with managed_resource("Database") as r:
    print(f"ប្រើ {r}")
```

---

## ⚡ Level 5 — កម្រិតខ្ពស់ / Advanced

### 5.1 Comprehensions (ទូទាំង)

```python
# List
squares = [x**2 for x in range(10)]

# Dict
word_len = {word: len(word) for word in ["Python", "ខ្មែរ", "Code"]}

# Set
unique_lengths = {len(word) for word in ["hello", "hi", "hey"]}

# Nested
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flat = [num for row in matrix for num in row]
# [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Conditional
even_squares = [x**2 for x in range(20) if x % 2 == 0]
```

---

### 5.2 Functional Programming

```python
from functools import reduce

nums = [1, 2, 3, 4, 5]

# map — ដំណើរការលើ element ទាំងអស់
doubled = list(map(lambda x: x * 2, nums))
# [2, 4, 6, 8, 10]

# filter — ច្រោះ element
big = list(filter(lambda x: x > 3, nums))
# [4, 5]

# reduce — ប្រមូល​ទៅ value តែ​មួយ
total = reduce(lambda a, b: a + b, nums)
# 15

# Chain operations
result = list(
    filter(
        lambda x: x > 10,
        map(lambda x: x ** 2, nums)
    )
)
# [16, 25]
```

---

### 5.3 Type Hints / ប្រភេទ Annotation

```python
from typing import List, Dict, Optional, Union, Tuple, Callable

def greet(name: str) -> str:
    return f"ជំរាបសួរ {name}!"

def add(a: int, b: int) -> int:
    return a + b

def get_user(id: int) -> Optional[Dict]:
    # Optional = អាច return None ឬ Dict
    users = {1: {"name": "ដារា"}}
    return users.get(id)

def process(items: List[int], multiplier: float = 1.0) -> List[float]:
    return [item * multiplier for item in items]

# Python 3.10+
def calculate(value: int | float) -> int | float:
    return value * 2

# Callable type
def apply(func: Callable[[int], int], value: int) -> int:
    return func(value)
```

> 💬 **ពន្យល់:** Type hints មិន enforce ដោយ Python ទេ ប៉ុន្តែ ជួយ editor (VS Code) ហើយ ធ្វើ code ច្បាស់ជាង។

---

### 5.4 Dataclasses

```python
from dataclasses import dataclass, field
from typing import List

@dataclass
class Student:
    name: str
    age: int
    grade: float = 0.0
    courses: List[str] = field(default_factory=list)

    def is_passing(self) -> bool:
        return self.grade >= 50

    def __post_init__(self):
        if self.age < 0:
            raise ValueError("អាយុ​ ត្រូវតែ >= 0")


student = Student("ដារា", 20, 85.5, ["Python", "Math"])
print(student)            # Student(name='ដារា', age=20, ...)
print(student.is_passing())  # True

# Auto-generated: __init__, __repr__, __eq__
s1 = Student("ចន្ទ", 18, 70.0)
s2 = Student("ចន្ទ", 18, 70.0)
print(s1 == s2)  # True
```

---

### 5.5 Async / Await — Asynchronous Programming

```python
import asyncio
import aiohttp  # pip install aiohttp

# Async function
async def fetch_data(url: str) -> str:
    async with aiohttp.ClientSession() as session:
        async with session.get(url) as response:
            return await response.text()


async def main():
    # ដំណើរការ concurrently (ក្នុងពេលតែមួយ)
    urls = [
        "https://api.example.com/data/1",
        "https://api.example.com/data/2",
        "https://api.example.com/data/3",
    ]
    tasks = [fetch_data(url) for url in urls]
    results = await asyncio.gather(*tasks)

    for result in results:
        print(result[:100])


asyncio.run(main())


# Simple async example
async def say_after(delay: float, message: str):
    await asyncio.sleep(delay)
    print(message)


async def demo():
    print("ចាប់ផ្ដើម")
    await asyncio.gather(
        say_after(2, "ល្អ! (2s)"),
        say_after(1, "ជំរាបសួរ! (1s)"),  # ចេញមុន
    )
    print("រួចរាល់")

asyncio.run(demo())
```

> 💬 **ពន្យល់:** `async/await` ជួយ run tasks ច្រើនក្នុងពេលតែមួយដោយ **មិន block** thread — ល្អសម្រាប់ network requests, I/O operations។

---

### 5.6 Metaclasses

```python
# Metaclass — class ដែលបង្កើត class
class SingletonMeta(type):
    """Singleton pattern — instance តែ​មួយ"""
    _instances = {}

    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]


class Database(metaclass=SingletonMeta):
    def __init__(self):
        self.connected = False

    def connect(self):
        self.connected = True
        print("✅ Connected to Database")


db1 = Database()
db2 = Database()
print(db1 is db2)  # True — same instance!
```

---

### 5.7 Design Patterns

```python
# Observer Pattern
class EventEmitter:
    def __init__(self):
        self._listeners: dict = {}

    def on(self, event: str, callback):
        self._listeners.setdefault(event, []).append(callback)

    def emit(self, event: str, *args):
        for cb in self._listeners.get(event, []):
            cb(*args)


emitter = EventEmitter()
emitter.on("login", lambda user: print(f"👤 {user} បានចូល"))
emitter.on("login", lambda user: print(f"📧 ផ្ញើ email ទៅ {user}"))
emitter.emit("login", "ដារា")


# Strategy Pattern
from abc import ABC, abstractmethod

class SortStrategy(ABC):
    @abstractmethod
    def sort(self, data: list) -> list:
        pass

class BubbleSort(SortStrategy):
    def sort(self, data: list) -> list:
        # simplified
        return sorted(data)

class QuickSort(SortStrategy):
    def sort(self, data: list) -> list:
        if len(data) <= 1:
            return data
        pivot = data[len(data) // 2]
        left = [x for x in data if x < pivot]
        mid = [x for x in data if x == pivot]
        right = [x for x in data if x > pivot]
        return self.sort(left) + mid + self.sort(right)

class Sorter:
    def __init__(self, strategy: SortStrategy):
        self.strategy = strategy

    def sort(self, data):
        return self.strategy.sort(data)

nums = [3, 1, 4, 1, 5, 9, 2, 6]
sorter = Sorter(QuickSort())
print(sorter.sort(nums))
```

---

### 5.8 Testing / ការធ្វើ Test

```python
# unittest
import unittest

def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("មិនអាចចែកនឹង 0")
    return a / b

class TestDivide(unittest.TestCase):

    def test_normal(self):
        self.assertEqual(divide(10, 2), 5)

    def test_float(self):
        self.assertAlmostEqual(divide(1, 3), 0.333, places=3)

    def test_zero(self):
        with self.assertRaises(ZeroDivisionError):
            divide(5, 0)

    def setUp(self):
        """Run មុន test នីមួយៗ"""
        print("🔧 Setup")

    def tearDown(self):
        """Run ក្រោយ test នីមួយៗ"""
        print("🧹 Teardown")


if __name__ == "__main__":
    unittest.main()
```

```bash
# pytest (pip install pytest)
pytest test_math.py -v
pytest test_math.py --cov  # with coverage
```

---

### 5.9 Performance Tips

```python
# 1. ប្រើ set/dict ជំនួស list សម្រាប់ lookup
items_list = [1, 2, 3, ..., 1000000]
items_set  = set(items_list)

# ❌ 느린
999999 in items_list  # O(n)

# ✅ 빠른
999999 in items_set   # O(1)


# 2. ប្រើ generator ជំនួស list ប្រសិន memory សំខាន់
total = sum(x**2 for x in range(1000000))  # ✅ memory efficient


# 3. join strings ជំនួស +=
words = ["ភ្នំពេញ", "Cambodia", "Python"]
# ❌
result = ""
for w in words:
    result += w + " "

# ✅
result = " ".join(words)


# 4. lru_cache — cache function results
from functools import lru_cache

@lru_cache(maxsize=128)
def fibonacci(n: int) -> int:
    if n < 2:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

print(fibonacci(50))  # លឿន! (cache results)


# 5. slots — ប្រើ memory តិចជាង ចំពោះ class
class Point:
    __slots__ = ['x', 'y']  # ការពារ dynamic attributes
    def __init__(self, x, y):
        self.x = x
        self.y = y
```

---

## 📦 Project Structure / រចនាសម្ព័ន្ធ Project

```
my_project/
│
├── src/
│   ├── __init__.py
│   ├── main.py
│   ├── models/
│   │   ├── __init__.py
│   │   └── user.py
│   └── utils/
│       ├── __init__.py
│       └── helpers.py
│
├── tests/
│   ├── __init__.py
│   ├── test_models.py
│   └── test_utils.py
│
├── requirements.txt      # dependencies
├── requirements-dev.txt  # dev dependencies
├── .env                  # environment variables (secret)
├── .gitignore
├── README.md
└── setup.py / pyproject.toml
```

```bash
# Virtual environment
python -m venv venv
source venv/bin/activate      # Linux/Mac
venv\Scripts\activate         # Windows

pip install -r requirements.txt
pip freeze > requirements.txt
```

---

## 🛠️ Essential Libraries

| Library | ប្រើសម្រាប់ | Install |
|---------|------------|---------|
| `requests` | HTTP calls | `pip install requests` |
| `pandas` | Data analysis | `pip install pandas` |
| `numpy` | Math/Arrays | `pip install numpy` |
| `fastapi` | Web API | `pip install fastapi` |
| `sqlalchemy` | Database ORM | `pip install sqlalchemy` |
| `pytest` | Testing | `pip install pytest` |
| `pydantic` | Data validation | `pip install pydantic` |
| `celery` | Task queue | `pip install celery` |

---

## ✅ Best Practices / គោលការណ៍ល្អ

```python
# ✅ Naming conventions
user_name = "ដារា"          # snake_case សម្រាប់ variable
MAX_SIZE = 100              # UPPER_CASE សម្រាប់ constant
class UserAccount:          # PascalCase សម្រាប់ class
    def get_balance(self):  # snake_case សម្រាប់ method
        pass

# ✅ Docstrings
def calculate_tax(income: float, rate: float = 0.1) -> float:
    """
    គណនា tax ពី income.

    Args:
        income: ចំណូលប្រចាំឆ្នាំ
        rate: អត្រា tax (default 10%)

    Returns:
        ចំនួន tax ដែលត្រូវបង់

    Raises:
        ValueError: ប្រសិន income < 0
    """
    if income < 0:
        raise ValueError("Income ត្រូវតែ >= 0")
    return income * rate

# ✅ ប្រើ constants
MAX_RETRIES = 3
DATABASE_URL = "postgresql://localhost/mydb"

# ✅ List ទទេ vs None
def get_items() -> list:
    return []  # return empty list, not None
```

---

## 🔗 ធនធាន / Resources

- 📖 [Official Python Docs](https://docs.python.org/3/)
- 🎓 [Real Python Tutorials](https://realpython.com)
- 💻 [Python Exercises](https://exercism.org/tracks/python)
- 📦 [PyPI — Package Index](https://pypi.org)
- 🐙 [Awesome Python](https://github.com/vinta/awesome-python)

---

<div align="center">

**🇰🇭 សិក្សា Python ជាភាសាខ្មែរ — រីករាយក្នុងការ code! 🐍**

*Made with ❤️ for Khmer developers*

</div>
