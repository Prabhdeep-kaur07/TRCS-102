# **DAY-14** | *13 July 2026*

## What I Learned

Today I started working with **Machine Learning models** using the preprocessed House Price dataset.

I learned how to separate a dataset into **features (X)** and a **target (y)**, split the data into training and testing sets, train a Linear Regression model, make predictions, and evaluate model performance.

### Features and Target

In supervised Machine Learning, the **features (X)** are the input variables or clues used by the model to make predictions, while the **target (y)** is the value that we want the model to predict.

For the House Price dataset:

- **X:** All columns except `price`
- **y:** `price`

### Train-Test Split

I used `train_test_split()` to divide the dataset into:

- **80% Training Data:** Used to train the Machine Learning model.
- **20% Testing Data:** Used to evaluate how well the model performs on unseen data.

I used `random_state=42` so that the same split is obtained every time the code is executed.

### Simple Linear Regression

Simple Linear Regression uses **one feature** to predict the target.

In this practice, I used `Scaled_size` as the only feature to predict house prices.

The model tries to find the best-fit straight line between the input feature and the target.

### Multiple Linear Regression

Multiple Linear Regression uses **multiple features** to predict the target.

For house price prediction, the model uses several features such as:

- Bedrooms
- Bathrooms
- House size
- Floors
- Waterfront
- Condition
- Location features

This allows the model to consider multiple factors when predicting house prices.

### Model Prediction

After training the model using `fit()`, I used `predict()` to generate predicted house prices for the test data.

I also used the trained multiple linear regression model to predict the price of a custom house.

### Model Evaluation

I used two evaluation metrics:

**Mean Absolute Error (MAE):**

MAE measures the average absolute difference between the actual and predicted values. A lower MAE generally indicates better prediction performance.

**R² Score:**

R² measures how well the model explains the variation in the target variable. A value closer to 1 generally indicates a better fit.

### Polynomial Regression

I also got introduced to **Polynomial Regression**, which can model non-linear relationships by adding polynomial features.

I used `PolynomialFeatures(degree=2)` together with `LinearRegression()` to create a polynomial regression model.

---

## Topics Covered

- Features, Target and Train-Test Split
- Simple and Multiple Linear Regression
- Prediction and Model Evaluation
- MAE and R² Score
- Introduction to Polynomial Regression

---

## Hands-on Practice

## 1. Importing Libraries and Loading Dataset

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error, r2_score

df = pd.read_csv("kc_house_preprocessed.csv")

print("Successfully loaded")

df
```

### 📷 Screenshot

![Loading Preprocessed Dataset](Images/Day-14/program1.png)

---

## 2. Separating Features and Target

```python
# Separate features (X) from target (y)

x = df.drop(columns=["price"])
y = df["price"]

# Perform 80/20 train-test split

x_train, x_test, y_train, y_test = train_test_split(
    x,
    y,
    test_size=0.20,
    random_state=42
)

print(f"Training set has: {x_train.shape[0]:,} rows")
print(f"Test set has: {x_test.shape[0]:,} rows")
```

### 📷 Screenshot

![Train Test Split](Images/Day-14/program2.png)

---

## 3. Simple Linear Regression

```python
# Use only house size as the feature

x_train_simple = x_train[["Scaled_size"]]
x_test_simple = x_test[["Scaled_size"]]

# Initialize the model

model = LinearRegression()

# Train the model

model.fit(
    x_train_simple,
    y_train
)

print(
    "Simple Linear Regression model has been trained successfully"
)
```

### 📷 Screenshot

![Simple Linear Regression Training](Images/Day-14/program3.png)

---

## 4. Making Predictions with Simple Linear Regression

```python
y_pred_simple = model.predict(x_test_simple)

print(y_pred_simple)
```

### 📷 Screenshot

![Simple Linear Regression Predictions](Images/Day-14/program4.png)

---

## 5. Actual vs Predicted Prices

```python
plt.figure(figsize=(10,6))

plt.scatter(
    x_test_simple["Scaled_size"],
    y_test,
    color="limegreen",
    alpha=0.3,
    label="Actual test houses"
)

plt.plot(
    x_test_simple["Scaled_size"],
    y_pred_simple,
    color="crimson",
    linewidth=3,
    label="Robot Prediction line"
)

plt.xlabel("House Size (Scaled MinMaxScaler)")
plt.ylabel("Price ($)")

plt.title(
    "House Prediction: Actual vs. Best-Fit Line"
)

plt.legend()

plt.show()
```

### 📷 Screenshot

![Actual vs Predicted Prices](Images/Day-14/program5.png)

---

## 6. Multiple Linear Regression

```python
multiple_model = LinearRegression()

# Train using all available training features

multiple_model.fit(
    x_train,
    y_train
)

# Predict prices for the test set

y_pred_multiple = multiple_model.predict(x_test)

print("Multiple Linear Regression model has been trained")
print("Predictions made successfully")
```

### 📷 Screenshot

![Multiple Linear Regression](Images/Day-14/program6.png)

---

## 7. Predicting the Price of a Custom House

```python
custom_house = pd.DataFrame([{
    "bedrooms": 3.0,
    "bathrooms": 2.0,
    "Scaled_size": 0.35,
    "floors": 2.0,
    "waterfront": 1,
    "sqft_living": 1800.0,
    "condition": 4,
    "Loc_Budget": 0,
    "Loc_Mid-Range": 1,
    "Loc_Premium": 0
}])

custom_house = custom_house[x_train.columns]

predicted_price = multiple_model.predict(
    custom_house
)[0]

print(
    f"Predicted price for our custom house: "
    f"${predicted_price:,.2f}"
)
```

### 📷 Screenshot

![Custom House Prediction](Images/Day-14/program7.png)

---

## 8. Evaluating Simple and Multiple Regression Models

```python
# Simple Linear Regression

mae_simple = mean_absolute_error(
    y_test,
    y_pred_simple
)

r2_simple = r2_score(
    y_test,
    y_pred_simple
)


# Multiple Linear Regression

mae_multiple = mean_absolute_error(
    y_test,
    y_pred_multiple
)

r2_multiple = r2_score(
    y_test,
    y_pred_multiple
)


print("=== Model Performance Comparison ===")

print(
    f"Simple Model (Size only): "
    f"MAE = ${mae_simple:,.2f} | "
    f"R² Score = {r2_simple:.4f}"
)

print(
    f"Multiple Model (All Clues): "
    f"MAE = ${mae_multiple:,.2f} | "
    f"R² Score = {r2_multiple:.4f}"
)
```

### 📷 Screenshot

![Model Performance Comparison](Images/Day-14/program8.png)

---

## 9. Polynomial Regression

```python
from sklearn.preprocessing import PolynomialFeatures
from sklearn.pipeline import make_pipeline

df = pd.read_csv("kc_house_preprocessed.csv")

df_sample = df.sample(
    n=80,
    random_state=42
)

x = df_sample.drop(
    columns="price"
)

y = df_sample["price"]

x_train, x_test, y_train, y_test = train_test_split(
    x,
    y,
    test_size=0.20,
    random_state=42
)

poly_model = make_pipeline(
    PolynomialFeatures(degree=2),
    LinearRegression()
)

poly_model.fit(
    x_train,
    y_train
)

print(
    "Polynomial Regression model trained successfully!"
)
```

### 📷 Screenshot

![Polynomial Regression](Images/Day-14/program9.png)

---

## 10. Evaluating Polynomial Regression

```python
# Predict on test data

y_pred = poly_model.predict(x_test)

# Predict on training data

y_pred_train = poly_model.predict(x_train)


# Calculate MAE and R² Score

mae = mean_absolute_error(
    y_test,
    y_pred
)

r2_test = r2_score(
    y_test,
    y_pred
)

r2_train = r2_score(
    y_train,
    y_pred_train
)


print("--- Model Performance Summary ---")

print(
    f"Average Miss (MAE): ${mae:,.2f}"
)

print(
    f"Test R² Score: {r2_test:.2f}"
)

print(
    f"Training R² Score: {r2_train:.2f}"
)
```

### 📷 Screenshot

![Polynomial Regression Performance](Images/Day-14/program10.png)

---

## Summary

Today I started Machine Learning with the House Price dataset. I learned how to divide data into features and target variables and perform an 80/20 train-test split. I trained Simple Linear Regression using house size and Multiple Linear Regression using multiple features. I generated predictions, visualized the best-fit line, predicted the price of a custom house, and compared models using MAE and R² Score. I also practiced Polynomial Regression to model more complex relationships in the data.
