# How to Perform Basic Data Analysis with Pandas

This guide will walk you through the process of performing basic data analysis using Pandas, a powerful data manipulation library in Python. We'll cover loading data, cleaning and preprocessing, basic statistical analysis, and grouping and aggregating data.

## 1. Loading Data from Various Sources

Pandas can read data from many different file formats. We'll focus on the most common ones: CSV, Excel, and SQL databases.

### Loading a CSV file

```python
import pandas as pd

# Load CSV file
df = pd.read_csv('your_file.csv')

# Display the first few rows
print(df.head())
```

### Loading an Excel file

```python
# Load Excel file
df = pd.read_excel('your_file.xlsx', sheet_name='Sheet1')

# Display the first few rows
print(df.head())
```

### Loading from a SQL database

```python
from sqlalchemy import create_engine

# Create a database engine
engine = create_engine('sqlite:///your_database.db')

# Read data from a SQL query
df = pd.read_sql_query("SELECT * FROM your_table", engine)

# Display the first few rows
print(df.head())
```

## 2. Cleaning and Preprocessing Data

Data cleaning is a crucial step in any data analysis process. Here are some common cleaning tasks:

### Handling missing values

```python
# Check for missing values
print(df.isnull().sum())

# Drop rows with any missing values
df_cleaned = df.dropna()

# Or, fill missing values with a specific value or method
df['column_name'].fillna(0, inplace=True)  # Fill with 0
df['column_name'].fillna(df['column_name'].mean(), inplace=True)  # Fill with mean
```

### Removing duplicates

```python
# Remove duplicate rows
df_unique = df.drop_duplicates()
```

### Converting data types

```python
# Convert a column to a different data type
df['date_column'] = pd.to_datetime(df['date_column'])
df['numeric_column'] = pd.to_numeric(df['numeric_column'], errors='coerce')
```

### Renaming columns

```python
# Rename columns
df = df.rename(columns={'old_name': 'new_name', 'another_old_name': 'another_new_name'})
```

## 3. Basic Statistical Analysis

Pandas provides many built-in methods for statistical analysis.

### Descriptive statistics

```python
# Get basic statistics of numerical columns
print(df.describe())

# Get information about the DataFrame, including data types
print(df.info())

# Calculate correlation between numerical columns
print(df.corr())
```

### Value counts for categorical data

```python
# Get value counts for a categorical column
print(df['category_column'].value_counts())

# Get value counts as percentages
print(df['category_column'].value_counts(normalize=True))
```

## 4. Grouping and Aggregating Data

Grouping and aggregating are powerful tools for summarising data.

### Basic grouping and aggregation

```python
# Group by a column and calculate mean of other columns
grouped = df.groupby('category_column').mean()
print(grouped)

# Group by multiple columns
grouped = df.groupby(['category1', 'category2']).mean()
print(grouped)
```

### Aggregating with multiple functions

```python
# Apply multiple aggregation functions
result = df.groupby('category_column').agg({
    'numeric_column1': ['mean', 'median', 'std'],
    'numeric_column2': ['min', 'max']
})
print(result)
```

## 5. Basic Data Visualisation with Pandas

Pandas integrates well with Matplotlib for quick visualisations.

```python
import matplotlib.pyplot as plt

# Create a bar plot
df['category_column'].value_counts().plot(kind='bar')
plt.title('Count of Categories')
plt.xlabel('Category')
plt.ylabel('Count')
plt.show()

# Create a line plot of a time series
df.set_index('date_column')['numeric_column'].plot()
plt.title('Time Series of Numeric Column')
plt.xlabel('Date')
plt.ylabel('Value')
plt.show()
```

## Tips for Data Analysis with Pandas

1. Always start by exploring your data with `df.head()`, `df.info()`, and `df.describe()`.

2. Use `df.columns` to get a list of column names, which is helpful for large datasets.

3. Pandas operations often return a new DataFrame. If you want to modify the original DataFrame, use `inplace=True` where available, or reassign the result back to the variable.

4. Chain operations for more concise code: `df = df.dropna().reset_index(drop=True)`

5. Use `df.loc[]` for label-based indexing and `df.iloc[]` for integer-based indexing.

6. Pandas has powerful string manipulation methods. Access them via `df['column'].str`.

7. For large datasets, consider using `df.sample(n)` to work with a random subset of your data during initial exploration.

Remember, this guide covers just the basics. Pandas is a powerful library with many more capabilities. As you become more comfortable with these operations, explore the Pandas documentation for more advanced features and methods.

Happy data analysing!