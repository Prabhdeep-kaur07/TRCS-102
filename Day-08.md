# **DAY-08** | *02 July 2026*

## 🎯 Today's Goal

Learn the fundamentals of the Pandas library, understand its data structures, and perform basic data loading, inspection, indexing, and filtering operations for data analysis.

## 📚 Topics Covered

1. Introduction to Pandas
2. Pandas Data Structures
3. Reading and Inspecting Data
4. Indexing and Filtering

## 📖 What I Learned

Today's session introduced me to **Pandas**, one of the most widely used Python libraries for data manipulation and analysis. While NumPy is mainly used for numerical computations, Pandas provides powerful and flexible data structures that make working with structured datasets much easier. It is extensively used in Data Science, Machine Learning, Artificial Intelligence, and Data Analytics.

### What is Pandas?

Pandas is an open-source Python library built on top of NumPy. It provides easy-to-use and efficient data structures for storing, organizing, cleaning, analyzing, and manipulating structured data. It is capable of handling data from various sources such as CSV files, Excel spreadsheets, SQL databases, and JSON files.

### Need of Pandas

Python lists and NumPy arrays work well for small datasets, but real-world datasets usually contain multiple columns with different types of data, missing values, and millions of records. Pandas simplifies these tasks by providing powerful tools for data manipulation and analysis.

Some advantages of Pandas include:

- Reading data from different file formats.
- Fast data filtering and sorting.
- Handling missing values.
- Statistical analysis of datasets.
- Data cleaning and preprocessing.
- Easy integration with NumPy, Matplotlib, and Scikit-learn.

### Installing Pandas in VS Code

To install Pandas in the active Python environment, open the VS Code terminal and execute:

```bash
pip install pandas
```

To verify the installation:

```python
import pandas as pd

print(pd.__version__)
```

### Pandas Data Structures

Pandas mainly provides two data structures:

#### 1. Series

A **Series** is a one-dimensional labeled array that can store integers, floating-point numbers, strings, or other Python objects. It is similar to a single column in a spreadsheet or database table.

Series contain:

- Index
- Values

Example:

```python
import pandas as pd

age = pd.Series([18, 19, 20])

print(age)
```

#### 2. DataFrame

A **DataFrame** is a two-dimensional table consisting of rows and columns. Each column can store different data types. DataFrames are the most commonly used data structure in Pandas because most datasets are stored in tabular form.

Example:

```python
student = {
    "Name": ["Simran", "Riya"],
    "Age": [20, 21]
}

df = pd.DataFrame(student)

print(df)
```

### Reading Data

One of the biggest advantages of Pandas is the ability to read datasets from external files.

The most commonly used function is:

```python
pd.read_csv("data.csv")
```

Other supported formats include:

- Excel
- JSON
- SQL Database
- HTML Tables

### Data Inspection Functions

Before performing any analysis or building a Machine Learning model, it is important to understand the structure and quality of the dataset. Pandas provides several built-in functions that allow us to inspect and summarize data quickly.

#### 1. `head()`

The `head()` function displays the first five rows of a DataFrame by default. It is useful for getting a quick preview of the dataset and verifying that it has been loaded correctly.

Syntax:

```python
df.head()
```

To display a specific number of rows:

```python
df.head(10)
```

---

#### 2. `tail()`

The `tail()` function displays the last five rows of a DataFrame by default. It is commonly used to verify the ending records of a dataset.

Syntax:

```python
df.tail()
```

Example:

```python
df.tail(3)
```

---

#### 3. `info()`

The `info()` function provides a concise summary of the DataFrame.

It displays:

- Total number of rows and columns
- Column names
- Number of non-null values
- Data type of each column
- Memory usage

Syntax:

```python
df.info()
```

This function is especially useful for identifying missing values and understanding the structure of the dataset.

---

#### 4. `describe()`

The `describe()` function generates descriptive statistics for all numerical columns in the DataFrame.

It calculates:

- Count
- Mean
- Standard Deviation
- Minimum value
- Maximum value
- 25th Percentile
- 50th Percentile (Median)
- 75th Percentile

Syntax:

```python
df.describe()
```

This helps in understanding the distribution of numerical data before analysis.

---

#### 5. `shape`

The `shape` attribute returns the dimensions of the DataFrame as a tuple.

It tells us:

- Number of rows
- Number of columns

Syntax:

```python
df.shape
```

Example output:

```python
(1000, 8)
```

This means the dataset contains **1000 rows** and **8 columns**.

---

#### 6. `dtypes`

The `dtypes` attribute displays the data type of every column in the DataFrame.

Syntax:

```python
df.dtypes
```

Common data types include:

- `int64`
- `float64`
- `object` (strings)
- `bool`

Knowing the data types helps determine whether any columns need to be converted before analysis.

---

#### 7. `columns`

The `columns` attribute returns the names of all columns in the DataFrame.

Syntax:

```python
df.columns
```

Example output:

```python
Index(['CustomerID', 'Age', 'Income', 'Gender'], dtype='object')
```

This is useful when selecting, renaming, or accessing specific columns.

---

Together, these inspection functions provide a quick overview of the dataset's structure, content, and quality. They are usually the first functions executed after loading any dataset because they help identify missing values, understand data types, and verify that the data has been imported correctly.

### Indexing using loc and iloc

Pandas provides two methods for selecting rows and columns.

#### loc

The **loc** method selects data using **row labels** and **column names**. Both the starting and ending indices are included.

Example:

```python
df.loc[0:3, "CustomerID":"Income"]
```

#### iloc

The **iloc** method selects data using **row positions** and **column positions**. The last index is excluded, similar to Python slicing.

Example:

```python
df.iloc[1:4, 1:4]
```

Using `loc` and `iloc` allows efficient extraction of specific rows and columns for analysis.

### Boolean Indexing (Filtering)

Boolean indexing is used to filter records that satisfy a particular condition.

Examples:

```python
df[df["Income"] > 50000]
```

```python
df[df["Age"] > 40]
```

Filtering helps extract meaningful subsets of data and is one of the most frequently used operations in data analysis.

---

## Hands-on Practice

## Program 1: Creating a Pandas Series

**Question:**

Create a NumPy array from a Python list and convert it into a Pandas Series.

### Code

```python
import pandas as pd
import numpy as np

list1 = [10, 20, 30, 40]

arr = np.array(list1)
print(type(arr))

series1 = pd.Series(list1, name="Age")

print(series1)
print(type(series1))
```

```markdown
![Program 1 Output](Images/Day-08/program1.png)
```

---

## Program 2: Creating a Pandas DataFrame

**Question:**

Create a Pandas DataFrame using a Python dictionary.

### Code

```python
import pandas as pd

student = {
    "Name": ["Sima", "Riya", "Ryan"],
    "Course": ["BCA", "B.Tech", "BCA"],
    "RollNo": [1, 2, 3]
}

df = pd.DataFrame(student)

print(df)
print(df.shape)
```


```markdown
![Program 2 Output](Images/Day-08/program2.png)
```

---

## Program 3: Reading a CSV File

**Question:**

Read a CSV file into a Pandas DataFrame.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df)
```

```markdown
![Program 3 Output](Images/Day-08/program3.png)
```

---

## Program 4: Inspecting the Dataset

**Question:**

Display the basic information and summary statistics of a dataset using different Pandas inspection functions.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df.head())

print(df.tail())

print(df.info())

print(df.describe())

print(df.shape)

print(df.dtypes)

print(df.columns)
```

```markdown
![Program 4 Output](Images/Day-08/program4.png)
```

---

## Program 5: Selecting Data Using loc

**Question:**

Select rows and columns from a DataFrame using the `loc` method.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

cols = ["CustomerID", "Income"]

print(df.loc[0:5, cols])

print(df.loc[0:3, "CustomerID":"Income"])

col = ["Gender", "Purchased"]

print(df.loc[4:5, col])
```

```markdown
![Program 5 Output](Images/Day-08/program5.png)
```

---

## Program 6: Selecting Data Using iloc

**Question:**

Select rows and columns from a DataFrame using the `iloc` method.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df.iloc[1:4, 1:4])

row_record = df.loc[1:4, ["CustomerID", "Age"]]

print(row_record)
```

```markdown
![Program 6 Output](Images/Day-08/program6.png)
```

---

## Program 7: Boolean Indexing (Filtering)

**Question:**

Filter records from a DataFrame using Boolean indexing based on different conditions.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df[df["Income"] > 50000])

print(df[df["Age"] > 40])
```

```markdown
![Program 7 Output](Images/Day-08/program7.png)
```

---

## 💻 What I Practiced

- Installed and imported the Pandas library.
- Created Pandas Series from Python lists and NumPy arrays.
- Built DataFrames using Python dictionaries.
- Loaded datasets from CSV files using `read_csv()`.
- Inspected datasets using `head()`, `tail()`, `info()`, `describe()`, `shape`, `dtypes`, and `columns`.
- Retrieved data using the `loc` and `iloc` indexing methods.
- Filtered records using Boolean indexing based on specified conditions.

## 💡 Key Takeaway

Today's session introduced me to **Pandas**, one of the most essential libraries for data analysis in Python. I learned how to create Series and DataFrames, load datasets from CSV files, inspect the structure of data, and retrieve specific records using indexing techniques. I also explored Boolean indexing to filter data efficiently. These concepts form the foundation of data preprocessing and exploratory data analysis, which are critical steps before building Machine Learning models.
