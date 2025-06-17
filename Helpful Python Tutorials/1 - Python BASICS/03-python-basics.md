# 3. Python Basics

## 3.1 Variables and Data Types

### Explain what variables are and how to create them
Variables in Python are used to store data in memory. They act as containers for values that can be changed throughout your program.

To create a variable in Python:
1. Choose a name for your variable.
2. Use the assignment operator (=) to give it a value.

Example:
```python
x = 5
name = "Alice"
```

Python variable naming rules:
- Must start with a letter or underscore
- Can contain letters, numbers, and underscores
- Are case-sensitive (age and Age are different variables)
- Cannot be Python keywords (like 'if', 'for', 'while', etc.)

### Demonstrate basic data types: int, float, str, bool
Python has several built-in data types. Here are the most common ones:

1. Integer (int): Whole numbers, positive or negative.
   ```python
   age = 25
   year = 2023
   ```

2. Float: Decimal numbers.
   ```python
   height = 1.75
   pi = 3.14159
   ```

3. String (str): Text, enclosed in single or double quotes.
   ```python
   name = "Alice"
   message = 'Hello, World!'
   ```

4. Boolean (bool): True or False values.
   ```python
   is_student = True
   has_license = False
   ```

### Show how to check the type of a variable (type() function)
Python provides the `type()` function to check the data type of a variable:

```python
age = 25
height = 1.75
name = "Alice"
is_student = True

print(type(age))       # Output: <class 'int'>
print(type(height))    # Output: <class 'float'>
print(type(name))      # Output: <class 'str'>
print(type(is_student)) # Output: <class 'bool'>
```

## 3.2 Basic Operations

### Arithmetic operations: +, -, *, /, //, %, **
Python supports various arithmetic operations:

1. Addition (+): `5 + 3` equals 8
2. Subtraction (-): `5 - 3` equals 2
3. Multiplication (*): `5 * 3` equals 15
4. Division (/): `5 / 3` equals 1.6666666666666667
5. Floor Division (//): `5 // 3` equals 1 (rounds down to nearest integer)
6. Modulus (%): `5 % 3` equals 2 (remainder of division)
7. Exponentiation (**): `5 ** 3` equals 125 (5 to the power of 3)

Example:
```python
x = 10
y = 3

print(x + y)  # Output: 13
print(x - y)  # Output: 7
print(x * y)  # Output: 30
print(x / y)  # Output: 3.3333333333333335
print(x // y) # Output: 3
print(x % y)  # Output: 1
print(x ** y) # Output: 1000
```

### Comparison operations: ==, !=, <, >, <=, >=
Comparison operations return boolean values (True or False):

1. Equal to (==): `5 == 5` is True
2. Not equal to (!=): `5 != 3` is True
3. Less than (<): `5 < 3` is False
4. Greater than (>): `5 > 3` is True
5. Less than or equal to (<=): `5 <= 5` is True
6. Greater than or equal to (>=): `5 >= 3` is True

Example:
```python
x = 10
y = 3

print(x == y)  # Output: False
print(x != y)  # Output: True
print(x < y)   # Output: False
print(x > y)   # Output: True
print(x <= y)  # Output: False
print(x >= y)  # Output: True
```

### Logical operations: and, or, not
Logical operations are used to combine boolean values:

1. and: True if both operands are True
2. or: True if at least one operand is True
3. not: Inverts the boolean value

Example:
```python
x = True
y = False

print(x and y)  # Output: False
print(x or y)   # Output: True
print(not x)    # Output: False
```

## 3.3 Strings and String Manipulation

### Creating strings with single and double quotes
Strings in Python can be created using either single or double quotes:

```python
single_quoted = 'Hello, World!'
double_quoted = "Python is fun!"
```

You can use single quotes inside double-quoted strings and vice versa:

```python
mixed = "It's a beautiful day"
also_mixed = 'She said, "Hello!"'
```

### String concatenation and repetition
Strings can be combined (concatenated) using the + operator:

```python
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name

print(full_name)  # Output: John Doe
```

Strings can be repeated using the * operator:

```python
cheer = "Hip " * 2 + "Hooray!"

print(cheer)  # Output: Hip Hip Hooray!
```

### String indexing and slicing
Characters in a string can be accessed using indexing (starting from 0):

```python
message = "Hello, World!"

print(message[0])   # Output: H
print(message[-1])  # Output: ! (negative indexing starts from the end)
```

Slicing allows you to extract a substring:

```python
print(message[0:5])  # Output: Hello
print(message[7:])   # Output: World!
print(message[:5])   # Output: Hello
```

### Useful string methods: upper(), lower(), strip(), split()
Python provides many useful string methods:

1. upper(): Converts string to uppercase
2. lower(): Converts string to lowercase
3. strip(): Removes whitespace from the beginning and end
4. split(): Splits the string into a list of substrings

Example:
```python
text = "  Python is Amazing  "

print(text.upper())         # Output: "  PYTHON IS AMAZING  "
print(text.lower())         # Output: "  python is amazing  "
print(text.strip())         # Output: "Python is Amazing"
print(text.split())         # Output: ['Python', 'is', 'Amazing']
```

## 3.4 Lists and List Operations

### Creating lists
Lists are ordered collections of items, which can be of different types:

```python
fruits = ["apple", "banana", "cherry"]
mixed_list = [1, "hello", 3.14, True]
```

### Accessing list elements (indexing and slicing)
List elements can be accessed using indexing, similar to strings:

```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])   # Output: apple
print(fruits[-1])  # Output: cherry
```

Slicing works the same way as with strings:

```python
print(fruits[0:2])  # Output: ['apple', 'banana']
```

### List methods: append(), extend(), insert(), remove(), pop()
Python provides several methods to manipulate lists:

1. append(): Adds an item to the end of the list
2. extend(): Adds all items from another iterable to the end of the list
3. insert(): Inserts an item at a specified position
4. remove(): Removes the first occurrence of a specified item
5. pop(): Removes and returns the item at a specified position (or the last item if no position is specified)

Example:
```python
fruits = ["apple", "banana", "cherry"]
fruits.append("date")

print(fruits)  # Output: ['apple', 'banana', 'cherry', 'date']

fruits.extend(["elderberry", "fig"])

print(fruits)  # Output: ['apple', 'banana', 'cherry', 'date', 'elderberry', 'fig']

fruits.insert(1, "blueberry")

print(fruits)  # Output: ['apple', 'blueberry', 'banana', 'cherry', 'date', 'elderberry', 'fig']

fruits.remove("banana")

print(fruits)  # Output: ['apple', 'blueberry', 'cherry', 'date', 'elderberry', 'fig']

popped = fruits.pop()

print(popped)  # Output: fig
print(fruits)  # Output: ['apple', 'blueberry', 'cherry', 'date', 'elderberry']
```

### List comprehensions (basic introduction)
List comprehensions provide a concise way to create lists:

```python
squares = [x**2 for x in range(5)]

print(squares)  # Output: [0, 1, 4, 9, 16]

even_numbers = [x for x in range(10) if x % 2 == 0]

print(even_numbers)  # Output: [0, 2, 4, 6, 8]
```

## 3.5 Dictionaries

### Creating dictionaries
Dictionaries are collections of key-value pairs:

```python
person = {"name": "Alice", "age": 30, "city": "New York"}
```

### Accessing and modifying dictionary elements
Dictionary elements are accessed using their keys:

```python
print(person["name"])  # Output: Alice

person["age"] = 31  # Modifying a value
person["job"] = "Engineer"  # Adding a new key-value pair

print(person)  # Output: {'name': 'Alice', 'age': 31, 'city': 'New York', 'job': 'Engineer'}
```

### Dictionary methods: keys(), values(), items()
Dictionaries have several useful methods:

1. keys(): Returns a view of all keys in the dictionary
2. values(): Returns a view of all values in the dictionary
3. items(): Returns a view of all key-value pairs in the dictionary

Example:
```python
print(person.keys())    # Output: dict_keys(['name', 'age', 'city', 'job'])
print(person.values())  # Output: dict_values(['Alice', 31, 'New York', 'Engineer'])
print(person.items())   # Output: dict_items([('name', 'Alice'), ('age', 31), ('city', 'New York'), ('job', 'Engineer')])
```

These views are dynamic, meaning they update when the dictionary changes.