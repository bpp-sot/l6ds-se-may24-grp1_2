# 5. Python in Data Science

## 5.1 Introduction to Key Libraries

Python's popularity in data science is largely due to its powerful libraries. We'll introduce three fundamental libraries: NumPy, Pandas, and Matplotlib.

### NumPy: Numerical Computing Library

NumPy (Numerical Python) is the fundamental package for scientific computing in Python. It provides support for large, multi-dimensional arrays and matrices, along with a collection of mathematical functions to operate on these arrays efficiently.

Key features:
- Multi-dimensional array object
- Tools for integrating C/C++ and Fortran code
- Useful linear algebra, Fourier transform, and random number capabilities

To use NumPy, you first need to import it:

```python
import numpy as np
```

### Pandas: Data Manipulation and Analysis

Pandas is built on top of NumPy and provides high-performance, easy-to-use data structures and data analysis tools. It's particularly good at handling structured data.

Key features:
- DataFrame object for data manipulation with integrated indexing
- Tools for reading and writing data between in-memory data structures and different file formats
- Data alignment and integrated handling of missing data
- Reshaping and pivoting of data sets

To use Pandas, import it like this:

```python
import pandas as pd
```

### Matplotlib: Data Visualisation

Matplotlib is a plotting library that provides a MATLAB-like interface. It produces publication-quality figures in a variety of hardcopy formats and interactive environments.

Key features:
- Create plots, histograms, power spectra, bar charts, errorcharts, scatterplots, etc., with just a few lines of code
- MATLAB-like interface for easy adoption
- Support for custom labels and texts

To use Matplotlib, typically you'll import its pyplot module:

```python
import matplotlib.pyplot as plt
```

## 5.2 Brief Demonstrations

Let's look at some basic examples of how to use these libraries.

### Creating a NumPy array

NumPy's main object is the homogeneous multidimensional array. Let's create a simple array and perform some operations:

```python
import numpy as np

# Create a 1D array
arr = np.array([1, 2, 3, 4, 5])

print("Original array:", arr)

# Perform operations
print("Mean:", arr.mean())
print("Standard deviation:", arr.std())
print("Array doubled:", arr * 2)

# Create a 2D array
matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

print("\n2D Array:")
print(matrix)

# Matrix operations
print("Sum of all elements:", matrix.sum())
print("Sum of each column:", matrix.sum(axis=0))
print("Sum of each row:", matrix.sum(axis=1))
```

Expected Output:
```
Original array: [1 2 3 4 5]
Mean: 3.0
Standard deviation: 1.4142135623730951
Array doubled: [ 2  4  6  8 10]

2D Array:
[[1 2 3]
 [4 5 6]
 [7 8 9]]
Sum of all elements: 45
Sum of each column: [12 15 18]
Sum of each row: [ 6 15 24]
```

### Reading a CSV file with Pandas

Pandas is excellent for handling structured data, like CSV files. Let's read a CSV file and perform some basic operations:

```python
import pandas as pd

# Read CSV file
# Note: Replace 'data.csv' with the path to your actual CSV file
df = pd.read_csv('data.csv')

# Display first few rows
print(df.head())

# Get basic information about the dataset
print(df.info())

# Compute summary statistics
print(df.describe())

# Select a single column
print(df['column_name'])

# Filter rows based on a condition
print(df[df['column_name'] > 5])

# Group by a column and compute mean
print(df.groupby('category_column')['value_column'].mean())
```

Note: The exact output will depend on the content of your CSV file.

### Creating a simple plot with Matplotlib

Matplotlib is used for creating a wide range of static, animated, and interactive visualisations. Here's a simple example:

```python
import matplotlib.pyplot as plt
import numpy as np

# Generate some data
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Create a line plot
plt.figure(figsize=(10, 6))
plt.plot(x, y, label='sin(x)')
plt.title('Sine Wave')
plt.xlabel('x')
plt.ylabel('sin(x)')
plt.legend()
plt.grid(True)

# Show the plot
plt.show()
```

This will display a plot of the sine function.

## 5.3 Practical Exercise: Basic Data Analysis

Let's combine these libraries to perform a simple data analysis task.

Task: Analyze a dataset of student scores.

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Create a sample dataset
data = {
    'Student': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Math': [85, 76, 90, 82, 95],
    'Science': [92, 88, 75, 79, 86],
    'Literature': [78, 92, 87, 81, 89]
}

# Create a DataFrame
df = pd.DataFrame(data)

# Set 'Student' as the index
df.set_index('Student', inplace=True)

print("Dataset:")
print(df)

# Compute average scores
average_scores = df.mean()

print("\nAverage Scores:")
print(average_scores)

# Find the highest score in each subject
highest_scores = df.max()

print("\nHighest Scores:")
print(highest_scores)

# Visualise the data
df.plot(kind='bar', figsize=(10, 6))

plt.title('Student Scores')
plt.xlabel('Student')
plt.ylabel('Score')
plt.legend(title='Subject')
plt.tight_layout()
plt.show()

# Compute correlation between subjects
correlation = df.corr()

print("\nCorrelation between subjects:")
print(correlation)

# Visualise correlation
plt.figure(figsize=(8, 6))
plt.imshow(correlation, cmap='coolwarm')
plt.colorbar()
plt.xticks(range(len(correlation.columns)), correlation.columns)
plt.yticks(range(len(correlation.columns)), correlation.columns)
plt.title('Correlation between Subjects')
plt.tight_layout()
plt.show()
```

This script demonstrates:
1. Creating a DataFrame with Pandas
2. Basic data analysis (computing averages and finding maximum values)
3. Data visualisation with Matplotlib (bar chart and heatmap)
4. Computing correlations between variables

By running this script, you'll see the dataset, average scores, highest scores, a bar chart of student scores, and a correlation heatmap.

This exercise gives a taste of how Python libraries can be used together for data analysis and visualisation tasks.