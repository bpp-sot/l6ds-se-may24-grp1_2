# Python Essentials Tutorial


## 4. Object-Oriented Programming (OOP) Basics (50 minutes)

Object-Oriented Programming is a programming paradigm that organises code into objects, which are instances of classes. OOP helps in creating modular, reusable, and easier to maintain code by mimicking real-world objects and their interactions.

### 4.1 Concept Introduction (10 minutes)

In OOP, we design our code around objects that contain both data (attributes) and code (methods). The main concepts in OOP are:

1. **Classes**: Blueprints for creating objects.
2. **Objects**: Instances of classes.
3. **Attributes**: Data stored inside an object.
4. **Methods**: Functions that belong to a class and can operate on its attributes.

Key benefits of OOP:
- Encapsulation: Bundling of data and methods that operate on that data.
- Inheritance: Ability to create new classes based on existing classes.
- Polymorphism: Ability of objects to take on multiple forms.
- Abstraction: Hiding complex implementation details and exposing only necessary parts.

### 4.2 Defining a Class (10 minutes)

Let's start by defining a simple class:

```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

# Creating an instance of the Car class
my_car = Car('audi', 'a4', 2019)
print(my_car.get_descriptive_name())
my_car.read_odometer()

# Updating the odometer reading
my_car.update_odometer(23500)
my_car.read_odometer()
```

In this example:
- `__init__` is a special method (constructor) that initialises a new object.
- `self` refers to the instance being created or operated on.
- We defined methods that can access and modify the object's attributes.

### 4.3 Inheritance (10 minutes)

Inheritance allows us to create a new class based on an existing class. This promotes code reuse and allows for specialised versions of classes.

```python
class ElectricCar(Car):
    def __init__(self, make, model, year, battery_size):
        super().__init__(make, model, year)
        self.battery_size = battery_size

    def describe_battery(self):
        print(f"This car has a {self.battery_size}-kWh battery.")

    # Override the parent class method
    def update_odometer(self, mileage):
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("Electric cars don't allow odometer rollbacks!")

# Creating an instance of ElectricCar
my_tesla = ElectricCar('tesla', 'model s', 2019, 75)
print(my_tesla.get_descriptive_name())
my_tesla.describe_battery()
my_tesla.update_odometer(10000)
my_tesla.read_odometer()
```

Here, `ElectricCar` inherits from `Car`, but adds its own attribute (`battery_size`) and method (`describe_battery`). It also overrides the `update_odometer` method.

### 4.4 Live Coding: Bank Account System (15 minutes)

Let's create a more complex example that demonstrates the use of OOP in a practical scenario:

```python
class BankAccount:
    def __init__(self, account_number, balance=0):
        self.account_number = account_number
        self.balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"Deposited ${amount}. New balance: ${self.balance}")
        else:
            print("Invalid deposit amount.")

    def withdraw(self, amount):
        if 0 < amount <= self.balance:
            self.balance -= amount
            print(f"Withdrew ${amount}. New balance: ${self.balance}")
        else:
            print("Invalid withdrawal amount or insufficient funds.")

    def get_balance(self):
        return self.balance

class SavingsAccount(BankAccount):
    def __init__(self, account_number, balance=0, interest_rate=0.01):
        super().__init__(account_number, balance)
        self.interest_rate = interest_rate

    def apply_interest(self):
        interest = self.balance * self.interest_rate
        self.deposit(interest)
        print(f"Applied interest of ${interest:.2f}")

class CheckingAccount(BankAccount):
    def __init__(self, account_number, balance=0, overdraft_limit=100):
        super().__init__(account_number, balance)
        self.overdraft_limit = overdraft_limit

    def withdraw(self, amount):
        if amount > 0 and self.balance + self.overdraft_limit >= amount:
            self.balance -= amount
            print(f"Withdrew ${amount}. New balance: ${self.balance}")
        else:
            print("Invalid withdrawal amount or exceeded overdraft limit.")

# Using the bank account system
savings = SavingsAccount("SA001", 1000, 0.05)
checking = CheckingAccount("CA001", 500, 200)

savings.deposit(500)
savings.apply_interest()
savings.withdraw(200)

checking.deposit(100)
checking.withdraw(700)  # This should work due to overdraft
checking.withdraw(200)  # This should fail
```

This example demonstrates:
- Creating a base `BankAccount` class with common functionality
- Creating specialised `SavingsAccount` and `CheckingAccount` classes through inheritance
- Overriding methods to provide specialised behaviour
- Using objects to model a real-world banking system

### 4.5 Exercise (5 minutes)

Design a `Student` class with attributes for name, age, and grades (a list). Include methods to add a grade, calculate the average grade, and return a string representation of the student. Then, create a `GraduateStudent` class that inherits from `Student` and adds attributes for research topic and advisor.

### Key Takeaways for OOP

1. OOP helps in organising code into reusable and logical structures.
2. Classes act as blueprints for creating objects with specific attributes and behaviors.
3. Inheritance allows for code reuse and the creation of specialised versions of classes.
4. Proper use of OOP can lead to more maintainable and scalable code.
5. OOP concepts like encapsulation and abstraction help in managing complex systems by hiding unnecessary details.
6. Practice identifying real-world objects and their interactions to model them effectively in your code.
