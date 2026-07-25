# **DAY-09** | *3 July 2026*

## 🎯 Today's Goal

Learn how to clean and preprocess datasets using Pandas by handling missing values, changing data types, grouping data, and exploring the Titanic dataset using various indexing and filtering techniques.

## 📚 Topics Covered

1. Data Cleaning in Pandas
2. Handling Missing Values
3. Grouping Data
4. Titanic Dataset Exploration

## 📖 What I Learned

Today's session focused on one of the most important stages of Data Analysis and Machine Learning: **data preprocessing**. Real-world datasets often contain missing values, incorrect data types, duplicate records, and inconsistent information. Before building any Machine Learning model, these issues must be identified and handled properly. Pandas provides several built-in functions that simplify the process of cleaning and preparing data.

### Changing the Data Type of a Column

Sometimes the data type of a column is not suitable for analysis. Pandas allows us to convert one data type into another using the `astype()` function.

Syntax:

```python
df["column_name"] = df["column_name"].astype(new_data_type)
```

Example:

```python
df["Age"] = df["Age"].astype(float)
```

Changing data types ensures that numerical operations, calculations, and visualizations can be performed correctly.

---

### Handling Missing Values

Missing values are common in real-world datasets and can negatively affect analysis and Machine Learning models if left untreated.

#### `isnull()`

The `isnull()` function checks every value in the DataFrame and returns `True` for missing values and `False` otherwise.

Syntax:

```python
df.isnull()
```

---

#### `isnull().sum()`

Instead of displaying every missing value, `isnull().sum()` counts the total number of missing values present in each column.

Syntax:

```python
df.isnull().sum()
```

This is one of the first functions used while exploring a dataset because it quickly identifies incomplete columns.

---

### Mean

The **mean** is the average value of all numerical entries in a column.

Syntax:

```python
df["Age"].mean()
```

The mean is commonly used to replace missing numerical values when the data is approximately symmetric.

---

### Median

The **median** is the middle value after arranging the data in ascending order.

Syntax:

```python
df["Age"].median()
```

Unlike the mean, the median is not heavily affected by extreme values (outliers). Therefore, it is often preferred for replacing missing values in skewed datasets.

---

### `fillna()`

The `fillna()` function replaces missing values with a specified value.

Syntax:

```python
df["Age"] = df["Age"].fillna(median)
```

Missing values can be replaced using:

- Mean
- Median
- Mode
- Constant values
- Custom values

This method preserves all rows while filling incomplete data.

---

### `dropna()`

The `dropna()` function removes rows or columns containing missing values.

Syntax:

```python
df.dropna()
```

To remove rows where a specific column contains missing values:

```python
df.dropna(subset=["Gender"])
```

This is useful when only a few missing records exist and removing them will not significantly affect the dataset.

---

### `groupby()`

The `groupby()` function divides data into groups based on one or more columns and performs aggregate operations such as mean, sum, count, minimum, and maximum.

Syntax:

```python
df.groupby("Gender")["Age"].mean()
```

Example:

```python
cols = ["Age", "Income"]

df.groupby("Gender")[cols].mean()
```

Grouping helps compare statistics across different categories and is frequently used during Exploratory Data Analysis (EDA).

---

### Exploring the Titanic Dataset

After learning the fundamentals of data cleaning, I worked with the famous **Titanic dataset**, which is widely used for learning data analysis and Machine Learning.

I loaded the dataset using `pd.read_csv()` and explored its structure using several inspection functions.

I practiced:

- Viewing the first and last records using `head()` and `tail()`.
- Finding the dimensions of the dataset using `shape`.
- Understanding the dataset using `info()`.
- Selecting rows and columns using `loc` and `iloc`.
- Filtering passengers based on conditions such as gender, passenger class, fare, and survival status.
- Handling missing values in the **Age** column using the median.
- Removing records with missing values in the **Embarked** column.
- Performing basic exploratory analysis before applying Machine Learning algorithms.

Working with the Titanic dataset helped me understand how the concepts learned in previous sessions are applied to real-world datasets.

---
## 👩‍💻 Hands-on Practice

## Program 1: Calculating Mean and Median

**Question:**

Calculate the mean and median of the **Age** column in a DataFrame.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

mean = df["Age"].mean()
print("Mean Age:", mean)

median = df["Age"].median()
print("Median Age:", median)
```


```markdown
![Program 1 Output](Images/Day-09/program1.png)
```

---

## Program 2: Filling Missing Values using `fillna()`

**Question:**

Replace missing values in the **Income** column with its mean.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

mean_income = df["Income"].mean()

df["Income"] = df["Income"].fillna(mean_income)

print(df.isnull().sum())
```


```markdown
![Program 2 Output](Images/Day-09/program2.png)
```

---

## Program 3: Removing Missing Values using `dropna()`

**Question:**

Remove rows where the **Gender** column contains missing values.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

df = df.dropna(subset=["Gender"])

print(df)

print(df.isnull().sum())
```


```markdown
![Program 3 Output](Images/Day-09/program3.png)
```

---

## Program 4: Grouping Data using `groupby()`

**Question:**

Group the dataset by **Gender** and calculate the average Age and Income.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df.groupby("Gender")["Age"].mean())

cols = ["Age", "Income"]

print(df.groupby("Gender")[cols].mean())
```

```markdown
![Program 4 Output](Images/Day-09/program4.png)
```

---

## Program 5: Loading and Inspecting the Titanic Dataset

**Question:**

Load the Titanic dataset and inspect its basic information.

### Code

```python
import pandas as pd

df = pd.read_csv("train.csv")

print(df.head(2))

print(df.tail(2))

print(df.shape)

print(df.info())
```


```markdown
![Program 5 Output](Images/Day-09/program5.png)
```

---

## Program 6: Selecting Data using `loc` and `iloc`

**Question:**

Retrieve specific rows and columns from the Titanic dataset using `loc` and `iloc`.

### Code

```python
import pandas as pd

df = pd.read_csv("train.csv")

print(df.loc[0:4, ["Name", "Sex", "Age"]])

print(df.iloc[10:15, 0:5])
```


```markdown
![Program 6 Output](Images/Day-09/program6.png)
```

---

## Program 7: Filtering Records from the Titanic Dataset

**Question:**

Filter passengers based on different conditions such as survival status, passenger class, gender, and fare.

### Code

```python
import pandas as pd

df = pd.read_csv("train.csv")

survived = df[df["Survived"] == 1]
print("Survived Passengers:", len(survived))

pclass = df[df["Pclass"] == 1]
print("First Class Passengers:", len(pclass))

female_survivors = df[(df["Sex"] == "female") & (df["Survived"] == 1)]
print("Female Survivors:", len(female_survivors))

fare = df[df["Fare"] > 100]
print("Passengers with Fare > 100:", len(fare))
```


```markdown
![Program 7 Output](Images/Day-09/program7.png)
```

---

## Program 8: Cleaning Missing Values in the Titanic Dataset

**Question:**

Replace missing values in the **Age** column using the median and remove rows with missing values in the **Embarked** column.

### Code

```python
import pandas as pd

df = pd.read_csv("train.csv")

median = df["Age"].median()

print("Median Age:", median)

df["Age"] = df["Age"].fillna(median)

print(df.isnull().sum())

df = df.dropna(subset=["Embarked"])

print(df.isnull().sum())
```


```markdown
![Program 8 Output](Images/Day-09/program8.png)
```

---

## 📝 Summary

- Learned techniques for handling missing values in datasets.
- Calculated statistical measures such as mean and median.
- Filled missing values using `fillna()` and removed incomplete records using `dropna()`.
- Grouped data using the `groupby()` function to analyze category-wise statistics.
- Explored the Titanic dataset using inspection functions like `head()`, `tail()`, `shape`, and `info()`.
- Practiced selecting and filtering data using `loc`, `iloc`, and Boolean indexing.
- Applied data cleaning techniques to prepare the dataset for further analysis and Machine Learning tasks.

## 💡 Key Takeaway

Data preprocessing is one of the most important steps in the Machine Learning pipeline. Learning how to identify missing values, clean datasets, group records, and explore real-world data using Pandas provides a strong foundation for exploratory data analysis and building accurate Machine Learning models.
