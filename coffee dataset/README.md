# Cafe Sales Dataset Cleaning Project

## Overview

This project focuses on cleaning and preprocessing a messy cafe sales dataset using Python and pandas.

The dataset contained:

- Missing values
- Duplicate rows
- Invalid datatypes
- Inconsistent categories
- Dirty numeric values
- Incorrect date formats

The goal was to transform the raw dataset into a clean and analysis-ready dataset.

---

# Dataset Columns

- Transaction ID
- Item
- Quantity
- Price Per Unit
- Total Spent
- Payment Method
- Location
- Transaction Date

---

# Cleaning Steps

## 1. Data Inspection

Used:

- `head()`
- `info()`
- `shape`
- `isnull().sum()`
- `unique()`

to understand the dataset structure and identify issues.

---

## 2. Removed Duplicate Rows

```python
df = df.drop_duplicates()
```

---

## 3. Handled Missing Values

Replaced dirty placeholder values such as:

```python
UNKNOWN
ERROR
```

with proper `NaN` values.

---

## 4. Cleaned Categorical Columns

Standardized text columns using:

```python
df["Location"] = df["Location"].str.strip().str.upper()
```

This helped remove:

- extra spaces
- inconsistent capitalization

---

## 5. Converted Numeric Columns

Converted columns such as:

- Quantity
- Price Per Unit
- Total Spent

using:

```python
pd.to_numeric(errors="coerce")
```

to handle invalid numeric values safely.

---

## 6. Cleaned Date Column

Used:

```python
pd.to_datetime(errors="coerce")
```

to convert transaction dates into proper datetime format.

---

## 7. Recalculated Total Spent

Instead of filling missing values with median values, `Total Spent` was recalculated using:

```python
df["Total Spent"] = (
    df["Quantity"] *
    df["Price Per Unit"]
)
```

This preserved business logic consistency.

---

# Skills Demonstrated

- Data Cleaning
- Missing Value Handling
- Datatype Conversion
- Duplicate Removal
- String Standardization
- Data Validation
- pandas Preprocessing

---

# Technologies Used

- Python
- pandas
- numpy
- Jupyter Notebook
- VS Code

---

# Final Outcome

The dataset was successfully cleaned and prepared for:

- Exploratory Data Analysis (EDA)
- Visualization
- Dashboarding
- Machine Learning
- Business Analysis
