# Python

Quick reference for Python tips, patterns, and stdlib.

---

## Data Structures

### Lists

```python
nums = [1, 2, 3, 4, 5]

# Comprehensions
squares = [x**2 for x in nums]
evens   = [x for x in nums if x % 2 == 0]

# Useful methods
nums.append(6)          # add to end
nums.extend([7, 8])     # add multiple
nums.pop()              # remove last
nums.sort(reverse=True) # sort in place
sorted(nums)            # return new sorted list
```

### Dictionaries

```python
d = {"a": 1, "b": 2}

d.get("c", 0)               # safe access with default
d.items()                   # (key, value) pairs
d.keys() / d.values()

# Dict comprehension
squares = {x: x**2 for x in range(5)}

# Merge (Python 3.9+)
merged = d1 | d2
```

### Sets

```python
s = {1, 2, 3}
s.add(4)
s.discard(99)       # no error if missing

a | b   # union
a & b   # intersection
a - b   # difference
```

---

## Strings

```python
s = "hello world"

s.upper() / s.lower() / s.title()
s.strip()           # remove whitespace
s.split()           # split on whitespace
", ".join(["a","b","c"])   # "a, b, c"
s.replace("hello", "hi")
s.startswith("he") / s.endswith("ld")
f"Value is {42:.2f}"       # f-string formatting
```

---

## Functions

```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

# Lambda
double = lambda x: x * 2

# *args and **kwargs
def func(*args, **kwargs):
    print(args, kwargs)

# Type hints (Python 3.5+)
def add(a: int, b: int) -> int:
    return a + b
```

---

## Classes

```python
class Animal:
    def __init__(self, name: str):
        self.name = name

    def speak(self) -> str:
        return f"{self.name} makes a sound"

    def __repr__(self) -> str:
        return f"Animal({self.name!r})"


class Dog(Animal):
    def speak(self) -> str:
        return f"{self.name} barks"
```

---

## Error Handling

```python
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print(f"Error: {e}")
except (TypeError, ValueError):
    pass
else:
    print("No error")
finally:
    print("Always runs")
```

---

## Useful stdlib

```python
from pathlib import Path
from collections import defaultdict, Counter
from itertools import chain, product
import json, os, sys, re

# Pathlib
p = Path("data/file.txt")
p.read_text() / p.write_text("content")
p.parent / p.stem / p.suffix
list(Path(".").glob("**/*.py"))

# Collections
counts = Counter(["a", "b", "a", "c", "a"])
counts.most_common(2)   # [("a", 3), ("b", 1)]

dd = defaultdict(list)
dd["key"].append(1)     # no KeyError
```

---

## See Also

- [list-comprehensions.md](list-comprehensions.md) - comprehension patterns
- [decorators.md](decorators.md) - writing and using decorators
