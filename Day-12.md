# DAY-12 | 08 July 2026

## What I Learned

Today I continued **Data Visualization and Exploratory Data Analysis (EDA)** using Pandas, Matplotlib, and Seaborn.

I practiced different visualization techniques such as **Count Plot, Box Plot, Scatter Plot, Bar Plot, Histogram, and Correlation Heatmap**. I also learned how the `hue` parameter can be used to divide data into different groups.

I applied these concepts to the **Titanic dataset** and the **House Price dataset** to understand distributions, relationships, categories, correlations, and outliers.

### Important Concepts

- **Count Plot:** Used to display the number of observations in different categories.
- **Box Plot:** Used to understand data distribution and identify potential outliers.
- **Scatter Plot:** Used to study the relationship between two numerical variables.
- **Bar Plot:** Used to compare numerical values across different categories.
- **Histogram:** Used to understand the distribution of numerical data.
- **Hue:** Used to divide data into groups using different colors.
- **Correlation:** Measures the strength and direction of the relationship between numerical variables.
- **Heatmap:** Represents values using colors and is useful for visualizing correlation matrices.
- **EDA:** Exploratory Data Analysis is the process of analyzing and visualizing data to discover patterns, relationships, distributions, and outliers before Machine Learning.

---

## Topics Covered

- Count Plot, Box Plot and Scatter Plot
- Bar Plot and Histogram
- Correlation Heatmap
- `hue` and Outlier Detection
- Exploratory Data Analysis using Titanic and House Price datasets

---

## Hands-on Practice

## 1. Titanic Survival and Gender Count

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.read_csv("train.csv")

# Survival Count
plt.figure(figsize=(8,5))

sns.countplot(
    data=df,
    x="Survived",
    palette="Set3"
)

plt.title("Titanic Passenger Survival Count")
plt.xlabel("Survived")
plt.ylabel("Number of Passengers")

plt.show()


# Gender Count
plt.figure(figsize=(8,5))

sns.countplot(
    data=df,
    x="Sex",
    palette="Set2"
)

plt.title("Titanic Passenger Gender Count")
plt.xlabel("Gender")
plt.ylabel("Number of Passengers")

plt.show()
```


![Titanic Survival and Gender Count](Images/Day-12/program1.png)

---

## 2. Titanic Fare Distribution and Outliers

```python
plt.figure(figsize=(8,5))

sns.boxplot(
    data=df,
    x="Fare",
    color="Purple"
)

plt.title("Ticket Fare Distribution & Outliers")
plt.xlabel("Fare")

plt.show()
```


![Titanic Fare Box Plot](Images/Day-12/program2.png)

---

## 3. Titanic Age vs Fare

```python
plt.figure(figsize=(8,5))

sns.scatterplot(
    data=df,
    x="Age",
    y="Fare",
    hue="Survived"
)

plt.xlabel("Age")
plt.ylabel("Fare")

plt.grid(True)

plt.show()
```



![Titanic Age vs Fare](Images/Day-12/program3.png)

---

## 4. Titanic Correlation Matrix

```python
columns = [
    "Survived",
    "Pclass",
    "Age",
    "Fare"
]

corr = df[columns].corr()

print("Correlation Matrix:")
print(corr)

plt.figure(figsize=(8,5))

sns.heatmap(
    data=corr,
    annot=True,
    vmax=1,
    vmin=-1,
    cmap="coolwarm"
)

plt.title("Titanic Features Correlation Heatmap")

plt.show()
```


![Titanic Correlation Heatmap](Images/Day-12/program4.png)

---

# 🏠 House Price Dataset — EDA

## 5. Loading and Selecting Important Features

```python
df = pd.read_csv("kc_house_data.csv.zip")

print(df.columns)

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

print(df.head())
```


![House Price Dataset](Images/Day-12/program5.png)

---

## 6. House Price Distribution

```python
plt.figure(figsize=(10,5))

sns.histplot(
    data=df,
    x="price",
    kde=True,
    color="Blue",
    bins=50
)

plt.title(
    "Price Distribution",
    fontsize=14
)

plt.xlabel(
    "Price",
    fontsize=12
)

plt.ylabel(
    "Number of Houses",
    fontsize=12
)

plt.ticklabel_format(
    style="plain",
    axis="x"
)

plt.show()
```

The distribution is **right-skewed**, meaning that most houses have lower or moderate prices while a smaller number of houses have very high prices.


![House Price Distribution](Images/Day-12/program6.png)

---

## 7. Bedroom Count and Outlier Detection

```python
# Bedroom Count

sns.countplot(
    data=df,
    x="bedrooms",
    hue="bedrooms",
    palette="Set2",
    legend=False
)

plt.title(
    "Bedroom Count: How Many Bedrooms Do People Have",
    fontsize=14
)

plt.xlabel(
    "Number of Bedrooms",
    fontsize=12
)

plt.ylabel(
    "Number of Houses",
    fontsize=12
)

plt.show()


# Box Plot

plt.figure(figsize=(8,5))

sns.boxplot(
    data=df,
    x="bedrooms"
)

plt.title("Bedroom Distribution and Outliers")

plt.show()


# Potential outliers

giant_outlier = df[df["bedrooms"] > 10]

print("Houses with more than 10 bedrooms:")
print(giant_outlier)
```


![Bedroom Count and Outliers](Images/Day-12/program7.png)

---

## 8. House Size vs Price

```python
plt.figure(figsize=(10,5))

sns.scatterplot(
    data=df,
    x="sqft_living",
    y="price",
    hue="bedrooms",
    palette="pastel"
)

plt.title(
    "Size vs Price",
    fontsize=14
)

plt.xlabel(
    "Living Area (sqft)",
    fontsize=12
)

plt.ylabel(
    "Price",
    fontsize=12
)

plt.ticklabel_format(
    style="plain",
    axis="y"
)

plt.show()
```

This plot helps analyze the relationship between the **living area of a house and its price**.


![House Size vs Price](Images/Day-12/program8.png)

---

## 9. Waterfront View vs Price

```python
plt.figure(figsize=(8,5))

sns.boxplot(
    x="waterfront",
    y="price",
    data=df,
    hue="waterfront",
    palette="pastel",
    legend=False
)

plt.title(
    "Waterfront View vs Price",
    fontsize=14
)

plt.xticks(
    [0,1],
    ["No Waterfront", "Waterfront"]
)

plt.xlabel(
    "House Location",
    fontsize=12
)

plt.ylabel(
    "Price ($)",
    fontsize=12
)

plt.ticklabel_format(
    style="plain",
    axis="y"
)

plt.show()
```


![Waterfront View vs Price](Images/Day-12/program9.png)

---

## 10. House Condition vs Price

```python
plt.figure(figsize=(8,5))

sns.barplot(
    x="condition",
    y="price",
    data=df,
    hue="condition",
    palette="coolwarm",
    legend=False
)

plt.title(
    "House Condition vs Price",
    fontsize=14
)

plt.xlabel(
    "House Condition Rating",
    fontsize=12
)

plt.ylabel(
    "Average Price ($)",
    fontsize=12
)

plt.ticklabel_format(
    style="plain",
    axis="y"
)

plt.show()
```


![House Condition vs Price](Images/Day-12/program10.png)

---

## 11. House Price Correlation Heatmap

```python
correlation_map = df.corr()

print("Correlation Matrix:")
print(correlation_map)

plt.figure(figsize=(10,8))

sns.heatmap(
    correlation_map,
    annot=True,
    cmap="mako",
    linewidth=0.5,
    vmin=-1,
    vmax=1
)

plt.title(
    "House Price Correlation Heatmap",
    fontsize=16
)

plt.show()
```


![House Price Correlation Heatmap](Images/Day-12/program11.png)

---

## 12. Exporting the Filtered Dataset

```python
df.to_csv(
    "kc_house_filtered.csv",
    index=False
)

print("Filtered dataset saved successfully.")

print(df.columns)
```


![Filtered Dataset](Images/Day-12/program12.png)

---

## Summary

Today I continued learning **Data Visualization and Exploratory Data Analysis (EDA)** using Pandas, Matplotlib, and Seaborn. I practiced Count Plots, Box Plots, Scatter Plots, Bar Plots, Histograms, and Correlation Heatmaps using the Titanic and House Price datasets. I analyzed categorical data, numerical distributions, relationships between variables, correlations, and potential outliers. I also selected important features from the House Price dataset and saved the filtered dataset as a new CSV file.

