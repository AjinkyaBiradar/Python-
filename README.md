# Python

A concise reference guide to Python — a high-level, interpreted, general-purpose programming language.

---

## 1. Introduction

**Python** is a high-level, interpreted programming language known for its simple, readable syntax and versatility.

**Why it's used:**
- Easy to learn and read — close to plain English syntax.
- Huge standard library and third-party ecosystem (PyPI).
- Cross-platform (Windows, macOS, Linux).

**Common use cases:** Web development, data science/ML, automation/scripting, backend APIs, DevOps, game development, and more.

---

## 2. Installation

Download from [python.org](https://www.python.org/downloads/) or install via package manager:

```bash
# Windows (via winget)
winget install Python.Python.3

# macOS (via Homebrew)
brew install python3

# Linux (Debian/Ubuntu)
sudo apt install python3
```

Check version:
```bash
python --version
```

Run a script:
```bash
python script.py
```

---

## 3. Basic Syntax

```python
# This is a comment
print("Hello, World!")   # Output text

name = "Alice"            # Variable assignment
if name == "Alice":
    print("Hi Alice!")     # Indentation defines code blocks
```

- No semicolons required.
- Indentation (spaces) defines blocks — not `{}`.
- Case-sensitive.

---

## 4. Data Types

| Type | Example | Description |
|---|---|---|
| `int` | `10` | Whole numbers |
| `float` | `3.14` | Decimal numbers |
| `str` | `"hello"` | Text |
| `bool` | `True`/`False` | Boolean values |
| `list` | `[1, 2, 3]` | Ordered, mutable collection |
| `tuple` | `(1, 2, 3)` | Ordered, immutable collection |
| `dict` | `{"key": "value"}` | Key-value pairs |
| `set` | `{1, 2, 3}` | Unordered, unique values |
| `NoneType` | `None` | Represents "no value" |

```python
x = 10
print(type(x))   # <class 'int'>
```

---

## 5. Variables & Operators

```python
x = 10
y = 3

# Arithmetic
x + y, x - y, x * y, x / y, x // y, x % y, x ** y

# Comparison
x > y, x < y, x == y, x != y

# Logical
x > 5 and y < 5
x > 5 or y > 5
not(x > 5)
```

---

## 6. Control Flow

```python
# If-else
if x > y:
    print("x is greater")
elif x == y:
    print("equal")
else:
    print("y is greater")

# For loop
for i in range(5):
    print(i)

# While loop
n = 0
while n < 5:
    n += 1
```

---

## 7. Functions

```python
def greet(name, greeting="Hello"):
    """Returns a greeting message."""
    return f"{greeting}, {name}!"

print(greet("Alice"))              # Hello, Alice!
print(greet("Bob", "Hi"))          # Hi, Bob!

# Lambda (anonymous) function
square = lambda x: x ** 2
print(square(5))                   # 25
```

---

## 8. Data Structures

```python
# List — ordered, mutable
fruits = ["apple", "banana", "cherry"]
fruits.append("mango")

# Tuple — ordered, immutable
point = (10, 20)

# Dictionary — key-value pairs
person = {"name": "Alice", "age": 25}
person["city"] = "New York"

# Set — unique, unordered
unique_nums = {1, 2, 2, 3}   # {1, 2, 3}
```

---

## 9. Object-Oriented Programming (OOP)

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        return f"{self.name} makes a sound."

class Dog(Animal):
    def speak(self):
        return f"{self.name} barks."

d = Dog("Rex")
print(d.speak())   # Rex barks.
```

Key concepts: **Class**, **Object**, **Inheritance**, **Encapsulation**, **Polymorphism**.

---

## 10. File Handling

```python
# Writing to a file
with open("data.txt", "w") as f:
    f.write("Hello, file!")

# Reading from a file
with open("data.txt", "r") as f:
    content = f.read()
    print(content)
```

---

## 11. Exception Handling

```python
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print("Error:", e)
finally:
    print("Execution complete.")
```

---

## 12. Modules & Packages

```python
import math
print(math.sqrt(16))         # 4.0

from datetime import datetime
print(datetime.now())

# Installing external packages
# pip install requests
import requests
```

---

## 13. Popular Libraries

| Domain | Libraries |
|---|---|
| Data Science | NumPy, Pandas, Matplotlib |
| Machine Learning | Scikit-learn, TensorFlow, PyTorch |
| Web Development | Django, Flask, FastAPI |
| Automation/Scripting | os, sys, shutil, subprocess |
| Web Scraping | BeautifulSoup, Scrapy |

---

## 14. Example Code Snippet

```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True

primes = [n for n in range(2, 20) if is_prime(n)]
print(primes)   # [2, 3, 5, 7, 11, 13, 17, 19]
```

---

## 15. References

- Official Documentation: [https://docs.python.org/3/](https://docs.python.org/3/)
- Python Package Index (PyPI): [https://pypi.org/](https://pypi.org/)
- Python GitHub: [https://github.com/python/cpython](https://github.com/python/cpython)
