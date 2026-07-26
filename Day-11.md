# 🗓️ **DAY-11** | *07 July 2026*

## 🎯 Today's Goal

Learn statistical data visualization techniques using Seaborn by creating Histograms, Box Plots, and Correlation Heatmaps, and understand how these graphs help analyze data distributions, detect outliers, and identify relationships between variables.

## 📚 Topics Covered

1. Histogram
2. Box Plot
3. Correlation Matrix
4. Heatmap

## 📖 What I Learned

Today's session focused on statistical data visualization using the **Seaborn** library. Unlike basic plots, statistical plots help us understand how data is distributed, detect unusual values (outliers), and discover relationships between variables before building Machine Learning models.

---

## Histogram

A **Histogram** is a graphical representation of the distribution of numerical data. It groups data into intervals called **bins** and displays the number of observations in each interval.

Unlike a bar chart, a histogram is used for **continuous numerical data**, where the bars touch each other because the values belong to continuous ranges.

### Syntax

```python
sns.histplot(data=df, x="column_name")
```

### Applications

- Understanding data distribution.
- Finding the most common values.
- Detecting skewness.
- Identifying possible outliers.
- Checking whether data follows a normal distribution.

---

## Terms Used in Histogram

### Bins

A **bin** is an interval that groups similar values together.

Example:

If marks range from 0 to 100,

```
0–20
20–40
40–60
60–80
80–100
```

Each interval represents one bin.

Increasing the number of bins provides more detail, while fewer bins produce a smoother distribution.

---

### KDE (Kernel Density Estimation)

KDE is a smooth curve drawn over the histogram that estimates the probability density of the data.

Instead of showing rectangular bars only, KDE provides a continuous view of the distribution.

Syntax:

```python
kde=True
```

Advantages:

- Makes the distribution easier to understand.
- Highlights peaks in the data.
- Smooths irregularities caused by bins.

---

### Count

The **Count** on the Y-axis represents the number of observations that fall within each bin.

---

## Box Plot

A **Box Plot** (also called a Box-and-Whisker Plot) summarizes the distribution of numerical data using five important statistical values.

It is mainly used for:

- Detecting outliers.
- Comparing multiple datasets.
- Understanding spread and variability.

### Syntax

```python
sns.boxplot(data=df, x="column_name")
```

---

## Parts of a Box Plot

### Minimum

The smallest value excluding outliers.

---

### First Quartile (Q1)

The value below which 25% of observations lie.

---

### Median (Q2)

The middle value of the dataset.

It divides the data into two equal halves.

---

### Third Quartile (Q3)

The value below which 75% of observations lie.

---

### Maximum

The largest value excluding outliers.

---

### Interquartile Range (IQR)

The spread of the middle 50% of the data.

Formula:

```
IQR = Q3 − Q1
```

---

### Whiskers

The lines extending from the box.

They represent the normal range of the data.

---

### Outliers

Outliers are observations that are much larger or smaller than the rest of the data.

In a box plot, they appear as individual points outside the whiskers.

Detecting outliers is important because they can significantly affect statistical analysis and Machine Learning models.

---

## Correlation Matrix

A **Correlation Matrix** is a table showing the correlation coefficients between every pair of numerical variables.

It helps determine how strongly variables are related.

In Pandas:

```python
corr_matrix = df.corr()
```

---

## Correlation Coefficient

Correlation values always lie between **-1 and +1**.

### +1 (Perfect Positive Correlation)

As one variable increases, the other also increases.

Example:

Study Hours ↑ → Marks ↑

---

### -1 (Perfect Negative Correlation)

As one variable increases, the other decreases.

Example:

Speed ↑ → Travel Time ↓

---

### 0 (No Correlation)

There is no linear relationship between the variables.

---

## Heatmap

A **Heatmap** is a color-coded representation of numerical values.

When applied to a correlation matrix, it makes relationships easier to identify visually.

### Syntax

```python
sns.heatmap(corr_matrix)
```

---

## Terms Used in Heatmap

### annot=True

Displays the numerical correlation values inside each cell.

---

### cmap

Specifies the color palette.

Example:

```python
cmap="YlGnBu"
```

Yellow → Green → Blue

---

### vmin and vmax

Define the minimum and maximum values shown on the color scale.

Example:

```python
vmin=-1
vmax=1
```

This ensures all correlation values are displayed consistently.

---

### linewidth

Adds lines between cells to improve readability.

Example:

```python
linewidth=1
```

---

## Importance in Machine Learning

These visualization techniques are frequently used during Exploratory Data Analysis (EDA).

- Histograms help understand feature distributions.
- Box Plots detect outliers that may require preprocessing.
- Correlation Matrices identify highly related features.
- Heatmaps provide a visual representation of relationships between variables.

Together, these plots help data scientists understand datasets before feature engineering, model selection, and training.

## 💻 Hands-on Practice

## Program 1: Histogram with Kernel Density Estimation (KDE)

**Question:**

Generate random candy distribution data and visualize it using a histogram with a Kernel Density Estimation (KDE) curve.

### Code

```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

np.random.seed(42)

candies = np.random.normal(loc=20, scale=4, size=30).astype(int)

df_candy = pd.DataFrame({"Candies": candies})

print(df_candy)

sns.set_theme(style="whitegrid")

plt.figure(figsize=(7,4))

sns.histplot(
    data=df_candy,
    x="Candies",
    kde=True,
    color="powderblue",
    bins=6
)

plt.title("Candy Distribution Among Kids", fontsize=14)
plt.xlabel("Number of Candies", fontsize=12)
plt.ylabel("Number of Kids (Count)", fontsize=12)

plt.show()
```


```markdown
![Program 1 Output](Images/Day-11/program1.png)
```

---

## Program 2: Box Plot for Outlier Detection

**Question:**

Create a Box Plot to identify outliers in frog jump distances.

### Code

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

frog_jumps = [5,6,4,7,5,7,7,6,6,8,7,5,18,20]

df_frogs = pd.DataFrame({
    "JumpDistance": frog_jumps
})

plt.figure(figsize=(7,3.5))

sns.boxplot(
    data=df_frogs,
    x="JumpDistance",
    color="lightgreen"
)

plt.title(
    "Frog Jump Distance & Outlier Detection",
    fontsize=14,
    color="pink"
)

plt.xlabel("Jump Distance (Feet)", fontsize=12)

plt.show()
```


```markdown
![Program 2 Output](Images/Day-11/program2.png)
```

---

## Program 3: Correlation Matrix and Heatmap

**Question:**

Calculate the correlation matrix of different video game features and visualize it using a heatmap.

### Code

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.DataFrame({
    "PlayTime_Hours": [10,50,80,20,95],
    "Popularity_Score": [40,85,90,30,98],
    "Game_Difficulty": [8,5,3,9,2]
})

corr_matrix = df.corr()

print("Correlation Matrix:\n")
print(corr_matrix)

plt.figure(figsize=(6,4.5))

sns.heatmap(
    corr_matrix,
    annot=True,
    cmap="YlGnBu",
    vmin=-1,
    vmax=1,
    linewidth=1
)

plt.title(
    "Video Game Features Correlation Matrix",
    fontsize=14
)

plt.show()
```


```markdown
![Program 3 Output](Images/Day-11/program3.png)
```

---

## Program 4: Histogram using the Titanic Dataset

**Question:**

Visualize the age distribution of Titanic passengers using a histogram with KDE.

### Code

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.read_csv("train.csv")

plt.figure(figsize=(8,5))

sns.histplot(
    data=df,
    x="Age",
    kde=True,
    color="limegreen"
)

plt.title(
    "Titanic Passenger Age Distribution",
    fontsize=14,
    color="blue"
)

plt.xlabel("Age", fontsize=12, color="blue")

plt.ylabel("Count", fontsize=12, color="blue")

plt.show()
```

```markdown
![Program 4 Output](Images/Day-11/program4.png)
```

---

## 📝 Summary

- Learned statistical data visualization techniques using the Seaborn library.
- Created histograms to understand the distribution of numerical data.
- Used Kernel Density Estimation (KDE) to visualize smooth probability distributions.
- Created Box Plots to summarize data and identify outliers.
- Calculated correlation matrices to measure relationships between numerical features.
- Visualized correlations using heatmaps for easier interpretation.
- Applied visualization techniques to both synthetic datasets and the real-world Titanic dataset.

## 💡 Key Takeaway

Data visualization is an essential step in Exploratory Data Analysis (EDA). Histograms reveal how data is distributed, Box Plots help detect outliers, and Correlation Heatmaps uncover relationships between variables. Together, these visualization techniques provide valuable insights that support better data preprocessing, feature selection, and Machine Learning model development.
