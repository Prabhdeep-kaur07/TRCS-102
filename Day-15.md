# **DAY-15** | *14 July 2026*

## What I Learned

Today I continued learning **Machine Learning models** and explored regularization techniques for regression. I also started **Classification** using Logistic Regression with the Titanic dataset.

### Polynomial Regression and Overfitting

I practiced a higher-degree polynomial regression model using `degree=6`. Increasing the polynomial degree makes the model more flexible, but it can also cause **overfitting**, where the model learns the training data too closely.

### Ridge and Lasso Regression

I learned about regularization techniques that help control model complexity.

- **Ridge Regression:** Uses L2 regularization and reduces the impact of large coefficients.
- **Lasso Regression:** Uses L1 regularization and can reduce some coefficients to zero, which can help with feature selection.
- **Alpha:** Controls the strength of regularization. A larger alpha means stronger regularization.

### Classification

I was introduced to **Logistic Regression**, which is used for classification problems.

Classification can be:

- **Binary Classification:** Two possible classes, such as Survived or Not Survived.
- **Multi-class Classification:** More than two classes, such as different passenger classes.

For the Titanic dataset, I used `Survived` as the target for binary classification.

### Data Preprocessing for Classification

Before training the classification model, missing values were handled and the categorical `Sex` column was converted into a numerical feature using mapping.

### Model Evaluation

I used **Accuracy** and a **Confusion Matrix** to evaluate the classification model.

A confusion matrix shows the number of correct and incorrect predictions by comparing the actual and predicted classes.

---

## Topics Covered

- Polynomial Regression and Overfitting
- Ridge and Lasso Regularization
- Logistic Regression
- Binary Classification and Confusion Matrix

---

## Hands-on Practice

## 1. Preparing Data for Polynomial Regression

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression, Ridge, Lasso
from sklearn.metrics import mean_absolute_error, r2_score
from sklearn.preprocessing import PolynomialFeatures
from sklearn.pipeline import make_pipeline

df = pd.read_csv("kc_house_preprocessed.csv")

df_sample = df.sample(
    n=80,
    random_state=42
)

x = df_sample[["Scaled_size"]]
y = df_sample["price"]

x_train, x_test, y_train, y_test = train_test_split(
    x,
    y,
    test_size=0.20,
    random_state=42
)

print(f"Training set: {x_train.shape[0]} houses")
print(f"Test set: {x_test.shape[0]} houses")
```

### 📷 Screenshot

![Polynomial Regression Dataset](Images/Day-15/program1.png)

---

## 2. Degree 6 Polynomial Regression

```python
# Degree 6 Polynomial Regression

wild_model = make_pipeline(
    PolynomialFeatures(degree=6),
    LinearRegression()
)

wild_model.fit(
    x_train,
    y_train
)

y_pred_wild = wild_model.predict(x_test)

mae_wild = mean_absolute_error(
    y_test,
    y_pred_wild
)

accuracy_wild = r2_score(
    y_test,
    y_pred_wild
)

print("--- Wild Robot Performance Summary ---")

print(
    f"Average Miss (MAE): ${mae_wild:,.2f}"
)

print(
    f"Accuracy: R² Score: {accuracy_wild:.2%}"
)
```

### 📷 Screenshot

![Polynomial Regression](Images/Day-15/program2.png)

---

## 3. Ridge Regression

```python
ridge_model = make_pipeline(
    PolynomialFeatures(degree=6),
    Ridge(alpha=0.1)
)

ridge_model.fit(
    x_train,
    y_train
)

y_pred_ridge = ridge_model.predict(x_test)

mae_ridge = mean_absolute_error(
    y_test,
    y_pred_ridge
)

accuracy_ridge = r2_score(
    y_test,
    y_pred_ridge
)

print("--- Ridge Robot Performance Summary ---")

print(
    f"Average Miss (MAE): ${mae_ridge:,.2f}"
)

print(
    f"Accuracy: R² Score: {accuracy_ridge:.2%}"
)
```

### 📷 Screenshot

![Ridge Regression](Images/Day-15/program3.png)

---

## 4. Lasso Regression

```python
lasso_model = make_pipeline(
    PolynomialFeatures(degree=6),
    Lasso(
        alpha=100.0,
        max_iter=10000
    )
)

lasso_model.fit(
    x_train,
    y_train
)

y_pred_lasso = lasso_model.predict(x_test)

mae_lasso = mean_absolute_error(
    y_test,
    y_pred_lasso
)

accuracy_lasso = r2_score(
    y_test,
    y_pred_lasso
)

print("--- Lasso Robot Performance Summary ---")

print(
    f"Average Miss (MAE): ${mae_lasso:,.2f}"
)

print(
    f"Accuracy: R² Score: {accuracy_lasso:.2%}"
)
```

### 📷 Screenshot

![Lasso Regression](Images/Day-15/program4.png)

---

# Titanic Classification

## 5. Preprocessing Titanic Dataset

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import (
    accuracy_score,
    confusion_matrix,
    classification_report
)

df = pd.read_csv("train.csv")

# Fill missing Age values with median
df["Age"] = df["Age"].fillna(
    df["Age"].median()
)

# Fill missing Embarked values with mode
most_common_embarked = df["Embarked"].mode()[0]

df["Embarked"] = df["Embarked"].fillna(
    most_common_embarked
)

# Convert Sex into numerical values
df["IsFemale"] = df["Sex"].map({
    "female": 1,
    "male": 0
})

# Select features
features = [
    "Age",
    "Fare",
    "SibSp",
    "Parch",
    "IsFemale"
]

print(
    "Preprocessing complete!"
)

print(
    df[features].head()
)
```

### 📷 Screenshot

![Titanic Preprocessing](Images/Day-15/program5.png)

---

## 6. Train-Test Split for Classification

```python
# Binary Classification
# Target: Survived

x = df[features]
y = df["Survived"]

x_train, x_test, y_train, y_test = train_test_split(
    x,
    y,
    test_size=0.20,
    random_state=42
)

print(
    f"Training set size: {x_train.shape[0]} rows"
)

print(
    f"Testing set size: {x_test.shape[0]} rows"
)
```

### 📷 Screenshot

![Classification Train Test Split](Images/Day-15/program6.png)

---

## 7. Binary Logistic Regression

```python
binary_model = LogisticRegression(
    max_iter=1000
)

binary_model.fit(
    x_train,
    y_train
)

y_pred = binary_model.predict(
    x_test
)

accuracy_bin = accuracy_score(
    y_test,
    y_pred
)

print(
    f"Binary Classification Accuracy: "
    f"{accuracy_bin:.4f} "
    f"({accuracy_bin * 100:.2f}%)"
)

print("-" * 50)

print(
    "Binary Logistic Regression model "
    "trained successfully!"
)
```

### 📷 Screenshot

![Binary Logistic Regression](Images/Day-15/program7.png)

---

## 8. Confusion Matrix

```python
y_pred = binary_model.predict(
    x_test
)

# Calculate accuracy
accuracy_bin = accuracy_score(
    y_test,
    y_pred
)

print(
    f"Binary Classification Accuracy: "
    f"{accuracy_bin:.4f} "
    f"({accuracy_bin * 100:.2f}%)"
)

# Confusion Matrix
cm_bin = confusion_matrix(
    y_test,
    y_pred
)

print("Confusion Matrix:")
print(cm_bin)

plt.figure(figsize=(6,4))

sns.heatmap(
    cm_bin,
    annot=True,
    fmt="d",
    cmap="coolwarm",
    xticklabels=[
        "Predicted: Not Survived",
        "Predicted: Survived"
    ],
    yticklabels=[
        "Actual: Not Survived",
        "Actual: Survived"
    ]
)

plt.title(
    "Binary Confusion Matrix"
)

plt.ylabel(
    "Actual Label"
)

plt.xlabel(
    "Predicted Label"
)

plt.tight_layout()

plt.show()
```

### 📷 Screenshot

![Confusion Matrix](Images/Day-15/program8.png)

---

## Summary

Today I explored regularization techniques and classification in Machine Learning. I practiced high-degree Polynomial Regression and learned how Ridge and Lasso regularization can help control model complexity. I then started classification using the Titanic dataset, handled missing values, converted categorical data into numerical form, and trained a Logistic Regression model for binary classification. Finally, I evaluated the model using accuracy and a confusion matrix.

## Key Takeaways

- Higher-degree polynomial models can become more complex and may overfit.
- Ridge and Lasso are regularization techniques used to control model complexity.
- Ridge uses L2 regularization, while Lasso uses L1 regularization.
- Logistic Regression can be used for classification problems.
- Binary classification has two possible classes.
- Missing values and categorical features should be handled before model training.
- Accuracy measures the proportion of correct predictions.
- A confusion matrix provides a detailed view of classification predictions.
