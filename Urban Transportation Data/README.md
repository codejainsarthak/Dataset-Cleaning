# Urban Transportation Data Cleaning Project

## Project Overview

This project focuses on cleaning and preprocessing a messy urban transportation dataset using Python and Pandas.

The dataset contains real-world data quality problems such as:

- Missing values
- Duplicate records
- Mixed datetime formats
- Invalid numeric values
- Inconsistent text formatting
- Incorrect categorical entries

The goal of this project is to convert raw messy data into a clean and analysis-ready dataset.

---

# Dataset Information

### File Name

`messy_urban_transport_dataset.csv`

### Dataset Size

- Rows: 8300
- Columns: 12

### Columns

- trip_id
- passenger_name
- age
- city
- transport_mode
- distance_km
- fare
- trip_start
- trip_end
- rating
- weather_condition
- payment_method

---

# Problems Found in Dataset

## Missing Values

Several columns contained null values:

- passenger_name
- age
- fare
- payment_method
- trip_end

## Duplicate Records

The dataset contained duplicate trip entries.

## Inconsistent Text Formatting

Examples:

- `"BUS "` vs `"Bus"`
- `"Delhi"` vs `"delhi"`
- Extra spaces in text columns

## Invalid Numeric Values

Examples:

- `"unknown"` inside distance column
- `"₹500"` inside fare column
- `"five"` inside rating column
- Invalid ratings like `-1` and `6`

## Mixed Datetime Formats

Examples:

```text
2025-08-04 01:31:48
19/01/2026 11:50 AM
10-26-2025 21:35
```

---

# Technologies Used

- Python
- Pandas
- NumPy
- Jupyter Notebook

---

# Data Cleaning Steps

## 1. Loaded Dataset

```python
df = pd.read_csv("messy_urban_transport_dataset.csv")
```

## 2. Removed Duplicate Records

```python
df = df.drop_duplicates()
```

## 3. Standardized Text Columns

- Removed extra spaces
- Fixed inconsistent casing
- Standardized category names

Example:

```python
df["city"] = df["city"].str.strip().str.upper()
```

## 4. Cleaned Numeric Columns

Used:

```python
pd.to_numeric(errors="coerce")
```

to convert invalid numeric values into NaN.

## 5. Fixed Datetime Columns

Used:

```python
pd.to_datetime(errors="coerce")
```

to handle mixed datetime formats.

## 6. Handled Missing Values

- Median used for numerical columns
- Mode used for categorical columns

Example:

```python
df["age"].fillna(df["age"].median(), inplace=True)
```

## 7. Cleaned Rating Column

- Converted text ratings into numeric values
- Removed invalid ratings outside valid range

---

# Final Outcome

After cleaning:

- Missing values were handled
- Duplicate rows were removed
- Datatypes were corrected
- Invalid entries were cleaned
- Dataset became analysis-ready

---

# Future Analysis Ideas

This cleaned dataset can be used for:

- City-wise transportation analysis
- Fare trend analysis
- Payment method analysis
- Weather impact analysis
- Peak travel hour analysis

---

# Project Structure

```text
project/
│
├── raw_data/
│   └── messy_urban_transport_dataset.csv
│
├── cleaned_data/
│   └── cleaned_transport_data.csv
│
├── notebooks/
│   └── Urban_Travel_Cleaning.ipynb
│
└── README.md
```

---

# Author

Sarthak Jain
