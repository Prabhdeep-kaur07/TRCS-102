# **DAY-13** | *09 July 2026*

## What I Learned

Today I learned about important **data preprocessing techniques** used to prepare a dataset before applying Machine Learning models.

I worked with the filtered House Price dataset and practiced checking for missing values, detecting and handling outliers, feature scaling, and converting categorical data into numerical form.

### Missing Values

Missing values are values that are absent from a dataset. I used `isnull().sum()` to check the number of missing values present in each column.

### Outlier Detection and Capping

Outliers are unusually high or low values that can affect analysis and Machine Learning models.

I used the **IQR (Interquartile Range)** method to detect outliers.

- Q1 = 25th percentile
- Q3 = 75th percentile
- IQR = Q3 - Q1
- Lower Cap = Q1 - 1.5 × IQR
- Upper Cap = Q3 + 1.5 × IQR

Instead of removing the outliers, I used the `clip()` function to cap them within the calculated limits.

### Feature Scaling

Feature scaling brings numerical features to a comparable scale.

I practiced two common techniques:

- **Min-Max Scaling:** Scales values between 0 and 1.
- **Standard Scaling:** Transforms values so that the mean is approximately 0 and standard deviation is 1.

I used `MinMaxScaler` and `StandardScaler` from Scikit-learn.

### One-Hot Encoding

One-Hot Encoding converts categorical values into numerical columns containing 0 and 1 so that categorical data can be used by Machine Learning algorithms.

I used `pd.get_dummies()` to encode the `Neighborhood` column.

---

## Topics Covered

- Missing Values and Outlier Handling
- Feature Scaling
- One-Hot Encoding
- Data Preprocessing

---

## Hands-on Practice

## 1. Loading Dataset and Checking Missing Values

```python
df = pd.read_csv("kc_house_filtered.csv")

df

df.isnull().sum()
```

### 📷 Screenshot

![Dataset and Missing Values](Images/Day-13/program1.png)

---

## 2. Visualizing Outliers

```python
sns.boxplot(data=df, y="sqft_living")

plt.grid(True)
```

### 📷 Screenshot

![Outlier Detection](Images/Day-13/program2.png)

---

## 3. Detecting and Capping Outliers Using IQR

```python
def find_caps(column_data):
    Q1 = column_data.quantile(0.25)
    Q3 = column_data.quantile(0.75)
    IQR = Q3 - Q1

    lower_cap = Q1 - 1.5 * IQR
    upper_cap = Q3 + 1.5 * IQR

    return lower_cap, upper_cap


columns = ["price", "sqft_living", "bedrooms"]

for col in columns:
    lower, upper = find_caps(df[col])

    outliers_count = (
        (df[col] < lower) | (df[col] > upper)
    ).sum()

    df[col] = df[col].clip(
        lower=lower,
        upper=upper
    )

    print(f"""Capped {outliers_count} outliers in '{col}'.
New range: {df[col].min()} to {df[col].max()}""")
```

### 📷 Screenshot

![IQR Outlier Capping](Images/Day-13/program3.png)

---

## 4. Checking Outliers After Capping

```python
sns.boxplot(data=df, x="price")

plt.grid(True)
```

### 📷 Screenshot

![Outliers After Capping](Images/Day-13/program4.png)

---

## 5. Visualizing Price Distribution

```python
plt.figure(figsize=(10,5))

sns.histplot(
    data=df,
    x="price",
    kde=True,
    bins=50,
    color="red"
)

plt.title(
    "The Price Mountain: How House Prices are Distributed",
    fontsize=14
)

plt.xlabel(
    "Price($)",
    fontsize=12
)

plt.ylabel(
    "Number Of Houses",
    fontsize=12
)

plt.show()
```

### 📷 Screenshot

![Price Distribution](Images/Day-13/program5.png)

---

## 6. Feature Scaling

```python
from sklearn.preprocessing import StandardScaler, MinMaxScaler

# Min-Max Scaling
minmax_scaler = MinMaxScaler()

df["Scaled_size"] = minmax_scaler.fit_transform(
    df[["sqft_living"]]
)

# Standard Scaling
std_scaler = StandardScaler()

df["Year_Scaled"] = std_scaler.fit_transform(
    df[["yr_built"]]
)

print("Scaled values preview:")

df
```

### 📷 Screenshot

![Feature Scaling](Images/Day-13/program6.png)

---

## 7. Creating a Categorical Feature

```python
np.random.seed(42)

neighborhoods = [
    "Budget",
    "Mid-Range",
    "Premium"
]

df["Neighborhood"] = np.random.choice(
    neighborhoods,
    size=len(df)
)

print("Neighborhood tiers before encoding:")

print(df["Neighborhood"].value_counts())
```

### 📷 Screenshot

![Neighborhood Categories](Images/Day-13/program7.png)

---

## 8. One-Hot Encoding

```python
df_encoded = pd.get_dummies(
    df,
    columns=["Neighborhood"],
    prefix="Loc",
    dtype=int
)

print("\nColumns after One-Hot Encoding:")

df_encoded
```

### 📷 Screenshot

![One-Hot Encoding](Images/Day-13/program8.png)

---

## 9. Selecting Features and Saving Preprocessed Dataset

```python
final_cols = [
    "price",
    "bedrooms",
    "bathrooms",
    "Scaled_size",
    "floors",
    "waterfront",
    "sqft_living",
    "condition",
    "Loc_Budget",
    "Loc_Mid-Range",
    "Loc_Premium"
]

df_final = df_encoded[final_cols]

df_final.to_csv(
    "kc_house_preprocessed.csv",
    index=False
)
```

### 📷 Screenshot

![Final Preprocessed Dataset](Images/Day-13/program9.png)

---

## Summary

Today I practiced important data preprocessing techniques on the House Price dataset. I checked for missing values, detected and capped outliers using the IQR method, and visualized the data using box plots and histograms. I also applied Min-Max and Standard Scaling to numerical features and converted categorical data into numerical form using One-Hot Encoding. Finally, I selected the required features and saved the preprocessed dataset as `kc_house_preprocessed.csv`.
