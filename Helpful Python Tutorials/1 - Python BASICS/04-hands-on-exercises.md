# 4. Hands-on Exercises

## Exercise 1: Creating Variables for Customer Information

### Task
Create variables to store customer information including name, account number, and contact details. Then, print out a summary of the customer information.

### Step-by-step Solution
1. Create variables for customer information:

```python
customer_name = "John Doe"
account_number = "AC1234567"
email = "john.doe@example.com"
phone_number = "+1 (555) 123-4567"
balance = 1000.50
```

2. Print a summary of the customer information:

```python
print("Customer Summary:")
print(f"Name: {customer_name}")
print(f"Account Number: {account_number}")
print(f"Email: {email}")
print(f"Phone: {phone_number}")
print(f"Balance: ${balance:.2f}")
```

### Expected Output
```
Customer Summary:
Name: John Doe
Account Number: AC1234567
Email: john.doe@example.com
Phone: +1 (555) 123-4567
Balance: $1000.50
```

### Additional Challenge
Create a dictionary to store the customer information instead of individual variables. Then, print the summary using the dictionary.

```python
customer = {
    "name": "John Doe",
    "account_number": "AC1234567",
    "email": "john.doe@example.com",
    "phone_number": "+1 (555) 123-4567",
    "balance": 1000.50
}

print("Customer Summary:")

for key, value in customer.items():
    if key == "balance":
        print(f"{key.capitalize()}: ${value:.2f}")
    else:
        print(f"{key.capitalize()}: {value}")
```

## Exercise 2: Using Lists for Transaction Data

### Task
Create a list to store transaction amounts for the past week. Calculate the total amount and the average transaction amount.

### Step-by-step Solution
1. Create a list of transaction amounts:

```python
transactions = [120.50, 75.00, 32.45, 81.20, 200.00, 140.75, 15.30]
```

2. Calculate the total amount:

```python
total_amount = sum(transactions)
```

3. Calculate the average transaction amount:

```python
average_amount = total_amount / len(transactions)
```

4. Print the results:

```python
print(f"Transaction Data:")
print(f"Transactions: {transactions}")
print(f"Total Amount: ${total_amount:.2f}")
print(f"Average Transaction Amount: ${average_amount:.2f}")
```

### Expected Output
```
Transaction Data:
Transactions: [120.5, 75.0, 32.45, 81.2, 200.0, 140.75, 15.3]
Total Amount: $665.20
Average Transaction Amount: $95.03
```

### Additional Challenge
Find and print the highest and lowest transaction amounts. Also, count how many transactions were above the average amount.

```python
highest_transaction = max(transactions)
lowest_transaction = min(transactions)
above_average_count = sum(1 for transaction in transactions if transaction > average_amount)

print(f"Highest Transaction: ${highest_transaction:.2f}")
print(f"Lowest Transaction: ${lowest_transaction:.2f}")
print(f"Number of transactions above average: {above_average_count}")
```

## Exercise 3: Implementing Dictionaries for Employee Details

### Task
Create a dictionary to store employee details including name, position, and salary. Add a new employee, update an existing employee's salary, and print out all employee information.

### Step-by-step Solution
1. Create a dictionary with employee details:

```python
employees = {
    "E001": {"name": "Alice Smith", "position": "Software Developer", "salary": 75000},
    "E002": {"name": "Bob Johnson", "position": "Project Manager", "salary": 85000},
    "E003": {"name": "Charlie Brown", "position": "Data Analyst", "salary": 70000}
}
```

2. Add a new employee:

```python
employees["E004"] = {"name": "Diana Prince", "position": "UX Designer", "salary": 72000}
```

3. Update an existing employee's salary:

```python
employees["E002"]["salary"] = 90000
```

4. Print out all employee information:

```python
print("Employee Details:")

for emp_id, emp_info in employees.items():
    print(f"Employee ID: {emp_id}")

    for key, value in emp_info.items():
        if key == "salary":
            print(f"  {key.capitalize()}: ${value:,}")
        else:
            print(f"  {key.capitalize()}: {value}")

    print()  # Empty line for readability
```

### Expected Output
```
Employee Details:
Employee ID: E001
  Name: Alice Smith
  Position: Software Developer
  Salary: $75,000

Employee ID: E002
  Name: Bob Johnson
  Position: Project Manager
  Salary: $90,000

Employee ID: E003
  Name: Charlie Brown
  Position: Data Analyst
  Salary: $70,000

Employee ID: E004
  Name: Diana Prince
  Position: UX Designer
  Salary: $72,000
```

### Additional Challenge
Implement a function to give all employees a raise based on a percentage. Then use this function to give everyone a 5% raise and print the updated employee information.

```python
def give_raise(employees, percentage):
    for emp_info in employees.values():
        emp_info["salary"] *= (1 + percentage / 100)

# Give everyone a 5% raise
give_raise(employees, 5)

print("Employee Details After 5% Raise:")
for emp_id, emp_info in employees.items():
    print(f"Employee ID: {emp_id}")

    for key, value in emp_info.items():
        if key == "salary":
            print(f"  {key.capitalize()}: ${value:,.2f}")
        else:
            print(f"  {key.capitalize()}: {value}")

    print()  # Empty line for readability
```