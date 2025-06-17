# 1. Control Structures

Control structures are fundamental building blocks in programming that allow us to control the flow of execution in our code. They enable us to make decisions, repeat actions, and create more dynamic and responsive programs. In Python, we'll focus on two main types of control structures: conditional statements (if-else) and loops.

## 1.1 If-Else Statements

Conditional statements allow our programs to make decisions based on certain conditions. The if-else statement is the most common type of conditional statement in Python.

Basic syntax:
```python
if condition:
    # code to execute if condition is True
else:
    # code to execute if condition is False
```

We can also use `elif` (short for "else if") to check multiple conditions:

```python
if condition1:
    # code to execute if condition1 is True
elif condition2:
    # code to execute if condition2 is True
else:
    # code to execute if all conditions are False
```

### Live Coding: Number Categorisation
Let's create a program that categorises a number as positive, negative, or zero.

```python
def categorise_number(num):
    if num > 0:
        return "Positive"
    elif num < 0:
        return "Negative"
    else:
        return "Zero"

# Test the function
print(categorise_number(5))    # Output: Positive
print(categorise_number(-3))   # Output: Negative
print(categorise_number(0))    # Output: Zero
```

### Exercise (5 minutes)
Write a function that takes a student's score (0-100) and returns their grade according to the following criteria:
- A: 90-100
- B: 80-89
- C: 70-79
- D: 60-69
- F: Below 60

## 1.2 Loops (20 minutes)

Loops allow us to repeat a block of code multiple times. Python provides two main types of loops: `for` loops and `while` loops.

### For Loops (10 minutes)

For loops are used to iterate over a sequence (like a list, tuple, or string) or other iterable objects.

Basic syntax:
```python
for item in sequence:
    # code to execute for each item
```

Live Coding: Sum Calculation

Let's create a program that calculates the sum of numbers in a list:

```python
def calculate_sum(numbers):
    total = 0
    for num in numbers:
        total += num
    return total

# Test the function
numbers = [1, 2, 3, 4, 5]

print(f"The sum of {numbers} is: {calculate_sum(numbers)}")  # Output: The sum of [1, 2, 3, 4, 5] is: 15
```

### While Loops (10 minutes)

While loops repeat a block of code as long as a condition is True.

Basic syntax:
```python
while condition:
    # code to execute while condition is True
```

Live Coding: Guessing Game

Let's create a simple number guessing game:

```python
import random

def guessing_game():
    number = random.randint(1, 100)
    attempts = 0

    print("I'm thinking of a number between 1 and 100.")

    while True:
        guess = int(input("Take a guess: "))
        attempts += 1

        if guess < number:
            print("Too low!")
        elif guess > number:
            print("Too high!")
        else:
            print(f"Congratulations! You guessed the number in {attempts} attempts!")
            break

guessing_game()
```

### Exercise (5 minutes)
Write a program that prints the first 10 Fibonacci numbers using a for loop or a while loop.

## Key Takeaways for Control Structures

1. Conditional statements (if-else) allow your program to make decisions based on specific conditions.
2. Loops (for and while) enable you to repeat code blocks, which is crucial for processing collections of data or implementing iterative algorithms.
3. Choosing the right control structure can make your code more efficient and easier to read.
4. Practice is key to mastering these concepts – try to identify situations in your own projects where you can apply these control structures.
