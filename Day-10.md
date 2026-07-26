# **DAY-10** | *06 July 2026*

## 🎯 Today's Goal

Practice additional data manipulation using Pandas and learn the fundamentals of Data Visualization using Matplotlib and Seaborn.

## 📚 Topics Covered

1. Pandas Practice
2. Data Visualization
3. Installing Visualization Libraries
4. Line Plot
5. Bar Plot
6. Scatter Plot

## 📖 What I Learned

Today's session focused on strengthening my Pandas skills through coding practice on different datasets and introducing Data Visualization, which helps transform raw data into meaningful graphical representations. Visualizations make it easier to identify trends, relationships, patterns, and outliers that may not be obvious from numerical data alone.

### Pandas Practice

I practiced solving different data manipulation problems using Pandas on multiple datasets. These exercises helped reinforce concepts such as data selection, filtering, indexing, grouping, handling missing values, and basic exploratory data analysis (EDA). Working with different datasets improved my understanding of applying Pandas functions to real-world scenarios.

---

### What is Data Visualization?

Data Visualization is the process of representing data graphically using charts and plots. Instead of analyzing large tables of numbers, visualizations help us understand the data quickly and make informed decisions.

Data visualization is widely used in:

- Data Analysis
- Machine Learning
- Business Intelligence
- Scientific Research
- Artificial Intelligence

Some benefits of Data Visualization include:

- Understanding trends and patterns.
- Identifying outliers and anomalies.
- Comparing different categories.
- Discovering relationships between variables.
- Communicating insights effectively.

---

### Installing Visualization Libraries

Before creating visualizations, the required Python libraries must be installed.

Install Matplotlib:

```bash
pip install matplotlib
```

Install Seaborn:

```bash
pip install seaborn
```

Install Scikit-learn:

```bash
pip install scikit-learn
```

These libraries serve different purposes:

- **Matplotlib** is the core plotting library used to create a wide variety of charts.
- **Seaborn** is built on top of Matplotlib and provides attractive statistical visualizations with simpler syntax.
- **Scikit-learn** is primarily a Machine Learning library but is often used alongside Pandas and Matplotlib for data preprocessing and model development.

---

### Line Plot

A Line Plot displays data points connected by straight lines. It is mainly used to show trends or changes over time.

Common uses include:

- Stock prices
- Temperature changes
- Sales growth
- Performance analysis

Syntax:

```python
plt.plot(x, y)
```

Advantages:

- Easy to observe trends.
- Suitable for continuous data.
- Useful for comparing multiple datasets.

---

### Bar Plot

A Bar Plot represents categorical data using rectangular bars. The height of each bar indicates the value associated with a category.

Common uses include:

- Comparing sales of different products.
- Student marks comparison.
- Population of cities.
- Department-wise performance.

Syntax:

```python
plt.bar(x, y)
```

Advantages:

- Easy comparison between categories.
- Simple to understand.
- Suitable for discrete data.

---

### Scatter Plot

A Scatter Plot displays individual data points to show the relationship between two numerical variables.

It is commonly used to:

- Detect correlations.
- Identify clusters.
- Find outliers.
- Analyze relationships between variables.

Syntax:

```python
plt.scatter(x, y)
```

Advantages:

- Shows relationships clearly.
- Detects unusual observations.
- Useful before building Machine Learning models.

---
## Hands-on Practice

## Program 1: Grouping Data using `groupby()`

**Question:**

Calculate the average Age and Fare of passengers based on their survival status.

### Code

```python
import pandas as pd

df = pd.read_csv("train.csv")

col = ["Age", "Fare"]

print(df.groupby("Survived")[col].mean())
```

```markdown
![Program 1 Output](Images/Day-10/program1.png)
```

---

## Program 2: House Price Dataset Exploration

**Question:**

Load the house price dataset and explore selected rows, columns, and property prices.

### Code

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df.loc[0:3, "date":"bathrooms"])

print(df.iloc[0:4, 0:4])

print(df[df["price"] > 2000000])

print(df[(df["price"] >= 2000000) & (df["yr_built"] > 1970)])
```

```markdown
![Program 2 Output](Images/Day-10/program2.png)
```

---

## Program 3: Data Cleaning and Analysis

**Question:**

Check missing values and calculate average house prices, bedrooms, and bathrooms city-wise.

### Code

```python
import pandas as pd

df = pd.read_csv("kc_house_data.csv.zip")

print(df.isnull().sum())

cols = ["price", "bedrooms", "bathrooms"]

print(df.groupby("city")[cols].mean())

friendly_cols = [
    "price",
    "bedrooms",
    "bathrooms",
    "sqft_living",
    "floors",
    "waterfront",
    "yr_built",
    "condition"
]

df = df[friendly_cols]

print(df.describe())
```

```markdown
![Program 3 Output](Images/Day-10/program3.png)
```

---

## Program 4: Line Plot

**Question:**

Create a line plot to visualize speed over different training days.

### Code

```python
import matplotlib.pyplot as plt

days = [1, 2, 3, 4, 5]
speed = [10, 25, 45, 70, 95]

plt.figure(figsize=(7,4))

plt.plot(
    days,
    speed,
    color="red",
    marker="o",
    linestyle="--",
    linewidth=2,
    label="Speed"
)

plt.title("Speed over Days", fontsize=14)

plt.xlabel("Days of Training")

plt.ylabel("Flight Speed (mph)")

plt.grid(True)

plt.legend()

plt.show()
```

```markdown
![Program 4 Output](Images/Day-10/program4.png)
```

---

## Program 5: Bar Plot

**Question:**

Create a bar chart showing the number of treats eaten by friends.

### Code

```python
import matplotlib.pyplot as plt

treats = ["Chocolates", "Gummy Bears", "Cookies", "Ice Cream"]

counts = [4, 6, 5, 3]

plt.figure(figsize=(7,4))

plt.bar(
    treats,
    counts,
    color="pink",
    edgecolor="skyblue"
)

plt.title("Treats Eaten by Friends This Week")

plt.xlabel("Types of Treats")

plt.ylabel("Total Eaten Count")

plt.show()
```

```markdown
![Program 5 Output](Images/Day-10/program5.png)
```

---

## Program 6: Scatter Plot

**Question:**

Create a scatter plot to visualize treasure chest locations on a map.

### Code

```python
import matplotlib.pyplot as plt

east_coords = [2,4,1,5,3,2.5,4.5,1.5]

north_coords = [3,1,4,2,5,3.5,1.5,4.2]

plt.figure(figsize=(7,4))

plt.scatter(
    east_coords,
    north_coords,
    color="gold",
    marker="X",
    s=100,
    edgecolor="darkgoldenrod"
)

plt.title("Treasure Chest Location on the Map")

plt.xlabel("East-West Coordinates")

plt.ylabel("North-South Coordinates")

plt.grid(True)

plt.show()
```

```markdown
![Program 6 Output](Images/Day-10/program6.png)
```

---

## 📝 Summary

- Practiced solving data analysis problems using different real-world datasets.
- Performed filtering, indexing, grouping, and statistical analysis using Pandas.
- Explored the House Price dataset using data inspection and aggregation techniques.
- Installed Matplotlib, Seaborn, and Scikit-learn for data visualization and machine learning.
- Learned how to create and customize Line, Bar, and Scatter plots to represent data graphically.
- Understood how different chart types help identify trends, compare categories, and analyze relationships between variables.

## 💡 Key Takeaway

Data visualization transforms raw numerical data into meaningful graphical insights, making it easier to identify trends, compare categories, and discover relationships. Combined with Pandas for data manipulation, visualization tools such as Matplotlib and Seaborn form an essential part of every data analysis and Machine Learning workflow.
