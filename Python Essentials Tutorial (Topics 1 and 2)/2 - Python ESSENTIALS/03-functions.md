# Python Essentials Tutorial

[Previous sections remain the same]

## 3. Functions (40 minutes)

Functions are reusable blocks of code that perform a specific task. They are fundamental to writing clean, efficient, and maintainable code. Functions allow us to organise our code into logical units, avoid repetition, and make our programs more modular and easier to understand.

### 3.1 Concept Introduction (5 minutes)

In Python, we define functions using the `def` keyword, followed by the function name and a pair of parentheses `()`. The function body is indented.

Basic syntax:
```python
def function_name(parameter1, parameter2, ...):
    # Function body
    # Code to be executed
    return result  # Optional
```

Key characteristics of functions:
- Reusability: Write once, use many times
- Modularity: Break complex problems into smaller, manageable parts
- Abstraction: Hide complex implementation details behind a simple interface
- Scope: Variables defined inside a function are typically only accessible within that function

### 3.2 Defining and Calling Functions (10 minutes)

Let's start with a simple function that greets a person:

```python
def greet(name):
    """This function greets the person passed in as a parameter"""
    return f"Hello, {name}! How are you today?"

# Calling the function
message = greet("Alice")
print(message)  # Output: Hello, Alice! How are you today?
```

Notice the docstring (the string in triple quotes) that describes what the function does. This is a good practice for documenting your functions.

#### Parameters and Arguments

- Parameters are the variables listed in the function definition.
- Arguments are the values passed to the function when it is called.

```python
def power(base, exponent=2):
    """Raises base to the power of exponent"""
    return base ** exponent

print(power(3))     # Output: 9 (uses default exponent 2)
print(power(3, 3))  # Output: 27
```

In this example, `base` and `exponent` are parameters. The function call `power(3)` passes `3` as an argument for `base` and uses the default value `2` for `exponent`.

### 3.3 Return Values (5 minutes)

Functions can return values using the `return` statement. A function can return a single value, multiple values, or nothing (implicitly returns `None`).

```python
def calculate_rectangle_properties(length, width):
    """Calculate area and perimeter of a rectangle"""
    area = length * width
    perimeter = 2 * (length + width)
    return area, perimeter  # Returning multiple values

rect_area, rect_perimeter = calculate_rectangle_properties(5, 3)
print(f"Area: {rect_area}, Perimeter: {rect_perimeter}")
# Output: Area: 15, Perimeter: 16
```

### 3.4 Variable Scope (5 minutes)

Variables defined inside a function have a local scope and are not accessible outside the function. Variables defined outside all functions have a global scope.

```python
x = 10  # Global variable

def print_x():
    x = 20  # Local variable
    print("Local x:", x)

print_x()
print("Global x:", x)

# Output:
# Local x: 20
# Global x: 10
```

### 3.5 Live Coding: Temperature Converter (10 minutes)

Let's create a more complex example that demonstrates the use of functions in a practical scenario:

```python
def celsius_to_fahrenheit(celsius):
    """Convert Celsius to Fahrenheit"""
    return (celsius * 9/5) + 32

def fahrenheit_to_celsius(fahrenheit):
    """Convert Fahrenheit to Celsius"""
    return (fahrenheit - 32) * 5/9

def kelvin_to_celsius(kelvin):
    """Convert Kelvin to Celsius"""
    return kelvin - 273.15

def celsius_to_kelvin(celsius):
    """Convert Celsius to Kelvin"""
    return celsius + 273.15

def temperature_converter():
    print("Temperature Converter")
    print("1. Celsius to Fahrenheit")
    print("2. Fahrenheit to Celsius")
    print("3. Kelvin to Celsius")
    print("4. Celsius to Kelvin")

    choice = input("Enter your choice (1-4): ")
    temperature = float(input("Enter the temperature: "))

    if choice == '1':
        result = celsius_to_fahrenheit(temperature)
        print(f"{temperature}°C is equal to {result:.2f}°F")
    elif choice == '2':
        result = fahrenheit_to_celsius(temperature)
        print(f"{temperature}°F is equal to {result:.2f}°C")
    elif choice == '3':
        result = kelvin_to_celsius(temperature)
        print(f"{temperature}K is equal to {result:.2f}°C")
    elif choice == '4':
        result = celsius_to_kelvin(temperature)
        print(f"{temperature}°C is equal to {result:.2f}K")
    else:
        print("Invalid choice")

temperature_converter()
```

This example demonstrates how functions can be used to create a modular and easy-to-understand program. Each conversion is encapsulated in its own function, and the main `temperature_converter()` function orchestrates the program flow.

### 3.6 Exercise (5 minutes)

Write a function called `calculate_bmi` that takes a person's weight (in kilograms) and height (in meters) as parameters and returns their Body Mass Index (BMI). Then, write another function called `interpret_bmi` that takes the BMI as a parameter and returns a string interpretation ("Underweight", "Normal weight", "Overweight", or "Obese") based on standard BMI ranges.

### Key Takeaways for Functions

1. Functions help in organising code, promoting reusability, and improving readability.
2. Python functions can have default parameter values and return multiple values.
3. Understanding variable scope is crucial for writing bug-free code.
4. Well-designed functions should have a single, clear purpose and be named descriptively.
5. Docstrings are important for documenting what a function does, its parameters, and what it returns.
6. Practice identifying repetitive code in your projects and refactoring it into functions.

[The rest of the tutorial content follows...]