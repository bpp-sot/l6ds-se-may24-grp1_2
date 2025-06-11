# Python Essentials Tutorial


## 2. Data Structures (50 minutes)

Data structures are fundamental components in programming that allow us to organise and manage data efficiently. In Python, two of the most commonly used data structures are lists and dictionaries. Understanding these structures is crucial for effective data manipulation and storage in both data science and software development.

### 2.1 Lists (25 minutes)

#### Concept Introduction (5 minutes)
Lists in Python are ordered, mutable sequences that can hold elements of different types. They are defined using square brackets `[]` and elements are separated by commas.

Basic syntax:
```python
my_list = [1, 2, 3, "four", 5.0]
```

Key characteristics of lists:
- Ordered: Elements maintain their order
- Mutable: Can be modified after creation
- Allow duplicates: Can contain multiple identical items
- Indexed: Elements can be accessed by their position (starting from 0)

#### Common List Operations (10 minutes)

1. Creating a list:
   ```python
   fruits = ["apple", "banana", "cherry"]
   ```

2. Accessing elements:
   ```python
   print(fruits[0])  # Output: apple
   print(fruits[-1])  # Output: cherry (negative indexing)
   ```

3. Slicing:
   ```python
   print(fruits[1:3])  # Output: ['banana', 'cherry']
   ```

4. Adding elements:
   ```python
   fruits.append("date")
   fruits.insert(1, "blueberry")
   ```

5. Removing elements:
   ```python
   fruits.remove("banana")
   popped_fruit = fruits.pop()  # Removes and returns the last element
   ```

6. List comprehension:
   ```python
   squares = [x**2 for x in range(5)]  # Creates [0, 1, 4, 9, 16]
   ```

#### Live Coding: To-Do List Manager (10 minutes)

Let's create a simple to-do list manager using a list:

```python
def todo_manager():
    tasks = []

    while True:
        print("\n--- To-Do List Manager ---")
        print("1. Add task")
        print("2. View tasks")
        print("3. Mark task as done")
        print("4. Exit")

        choice = input("Enter your choice (1-4): ")

        if choice == '1':
            task = input("Enter the task: ")
            tasks.append(task)
            print("Task added successfully!")

        elif choice == '2':
            if tasks:
                print("Your tasks:")
                for i, task in enumerate(tasks, 1):
                    print(f"{i}. {task}")
            else:
                print("No tasks in the list.")

        elif choice == '3':
            if tasks:
                task_num = int(input("Enter the task number to mark as done: ")) - 1
                if 0 <= task_num < len(tasks):
                    done_task = tasks.pop(task_num)
                    print(f"Marked '{done_task}' as done!")
                else:
                    print("Invalid task number.")
            else:
                print("No tasks in the list.")

        elif choice == '4':
            print("Thank you for using To-Do List Manager!")
            break

        else:
            print("Invalid choice. Please try again.")

todo_manager()
```

This example demonstrates how lists can be used to store, manipulate, and manage data in a practical application.

### 2.2 Dictionaries (25 minutes)

#### Concept Introduction (5 minutes)
Dictionaries in Python are unordered collections of key-value pairs. They are defined using curly braces `{}` with each key-value pair separated by a colon `:`.

Basic syntax:
```python
my_dict = {"key1": value1, "key2": value2}
```

Key characteristics of dictionaries:
- Unordered (in Python versions < 3.7)
- Mutable: Can be modified after creation
- Keys must be unique and immutable (typically strings or numbers)
- Values can be of any type
- Fast lookups: Accessing values by key is very efficient

#### Common Dictionary Operations (10 minutes)

1. Creating a dictionary:
   ```python
   person = {"name": "Alice", "age": 30, "city": "New York"}
   ```

2. Accessing values:
   ```python
   print(person["name"])  # Output: Alice
   print(person.get("age"))  # Output: 30 (safer method)
   ```

3. Adding or updating key-value pairs:
   ```python
   person["job"] = "Engineer"
   person["age"] = 31
   ```

4. Removing key-value pairs:
   ```python
   del person["city"]
   job = person.pop("job")  # Removes and returns the value
   ```

5. Checking for keys:
   ```python
   if "name" in person:
       print("Name is present in the dictionary")
   ```

6. Dictionary comprehension:
   ```python
   squared_numbers = {x: x**2 for x in range(5)}  # Creates {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
   ```

#### Live Coding: Student Grade Manager (10 minutes)

Let's create a program that manages student grades using a dictionary:

```python
def grade_manager():
    grades = {}

    while True:
        print("\n--- Student Grade Manager ---")
        print("1. Add student grade")
        print("2. View all grades")
        print("3. Get student's grade")
        print("4. Calculate average grade")
        print("5. Exit")

        choice = input("Enter your choice (1-5): ")

        if choice == '1':
            name = input("Enter student name: ")
            grade = float(input("Enter student grade: "))
            grades[name] = grade
            print("Grade added successfully!")

        elif choice == '2':
            if grades:
                print("All grades:")
                for name, grade in grades.items():
                    print(f"{name}: {grade}")
            else:
                print("No grades recorded yet.")

        elif choice == '3':
            name = input("Enter student name: ")
            if name in grades:
                print(f"{name}'s grade: {grades[name]}")
            else:
                print("Student not found.")

        elif choice == '4':
            if grades:
                average = sum(grades.values()) / len(grades)
                print(f"Average grade: {average:.2f}")
            else:
                print("No grades recorded yet.")

        elif choice == '5':
            print("Thank you for using Student Grade Manager!")
            break

        else:
            print("Invalid choice. Please try again.")

grade_manager()
```

This example showcases how dictionaries can be used to store and manage structured data efficiently.

### Key Takeaways for Data Structures

1. Lists are versatile for storing ordered collections of items, while dictionaries excel at storing key-value pairs for quick lookups.
2. Both lists and dictionaries are mutable, allowing for dynamic data management.
3. List and dictionary comprehensions provide concise ways to create these data structures based on existing data or conditions.
4. Choosing the right data structure can significantly impact the efficiency and readability of your code.
5. Practice identifying situations where each data structure is most appropriate in your projects.
