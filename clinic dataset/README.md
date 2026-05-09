# Medical Clinic Dataset Cleaning Project

## Overview

This project focuses on cleaning and preprocessing a messy medical clinic dataset using Python and pandas.

The dataset contains realistic healthcare-related data issues such as:

- Missing values
- Duplicate records
- Invalid numeric values
- Inconsistent categorical labels
- Incorrect date formats
- Mixed datatypes
- Dirty contact information

The goal of this project is to transform raw clinical data into a clean and analysis-ready dataset.

---

# Dataset Columns

- Patient ID
- Patient Name
- Age
- Gender
- Blood Group
- Height
- Weight
- Diagnosis
- Consultation Fee
- Visit Date
- Phone Number
- Payment Method

---

# Problems Found in Dataset

The raw dataset contained several real-world data quality issues.

## Missing Values

Examples:

- `UNKNOWN`
- `ERROR`
- Empty values

---

## Inconsistent Categories

Examples:

- `male`
- `Male`
- ` MALE`

Similar inconsistencies existed in:

- Gender
- Blood Group
- Payment Method
- Diagnosis

---

## Invalid Numeric Values

Numeric columns contained:

- text values
- symbols
- invalid entries

Examples:

- `five`
- `unknown`
- `₹500`
- `ERROR`

---

## Incorrect Date Formats

The `Visit Date` column contained:

- invalid dates
- mixed formats
- corrupted entries

---

## Duplicate Records

Duplicate patient records were present in the dataset.

---

# Cleaning Steps Performed

## 1. Data Inspection

Used:

- `head()`
- `info()`
- `shape`
- `isnull().sum()`
- `unique()`

to inspect the dataset structure and identify issues.

---

## 2. Removed Duplicate Rows

```python
df = df.drop_duplicates()
```

---

## 3. Handled Missing Values

Replaced dirty placeholders such as:

```python
UNKNOWN
ERROR
```

with proper `NaN` values.

---

## 4. Cleaned Categorical Columns

Standardized columns using:

- `.str.strip()`
- `.str.upper()`

to remove:

- extra spaces
- inconsistent capitalization

---

## 5. Converted Numeric Columns

Cleaned and converted:

- Age
- Height
- Weight
- Consultation Fee

using:

```python
pd.to_numeric(errors="coerce")
```

---

## 6. Cleaned Date Column

Converted the `Visit Date` column into proper datetime format using:

```python
pd.to_datetime(errors="coerce")
```

---

## 7. Cleaned Contact Information

Phone numbers were cleaned using regex to remove:

- spaces
- brackets
- symbols
- invalid characters

---

# Skills Demonstrated

- Data Cleaning
- Missing Value Handling
- Datatype Conversion
- Duplicate Removal
- Regex Cleaning
- String Standardization
- Date Cleaning
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
- Healthcare Data Analysis
- Visualization
- Dashboarding
- Machine Learning preprocessing
