# Data Preprocessing for House Prices Dataset

## Overview
This project focuses on preparing the House Prices dataset for machine learning modeling.

The preprocessing includes data cleaning, transformation, exploratory data analysis (EDA), feature engineering, and encoding.

---

## Dataset
- train.csv → contains SalePrice (target)
- test.csv → without SalePrice

Place them inside:
data/train.csv

data/test.csv



---

## Steps Performed

### 1. Data Inspection
- Checked dataset shape
- Displayed sample rows
- Identified data types
- Optimized memory usage

### 2. Data Cleaning
- Handled missing values using:
  - "None" for categorical features
  - 0 for structural numeric features
  - Median and mode for remaining values

### 3. Outlier Removal
- Removed extreme values based on:
  GrLivArea > 4000 and low SalePrice

### 4. Log Transformation
- Applied:
```python
np.log1p(SalePrice)
```
To reduce skewness and improve modeling
### 5. Exploratory Data Analysis (EDA)

Correlation analysis

Heatmap visualization

Scatter plot (GrLivArea vs SalePrice)

Neighborhood price analysis

### 6. Feature Engineering

Created:
TotalSF = TotalBsmtSF + 1stFlrSF + 2ndFlrSF
### 7. Encoding

Ordinal encoding for quality features

One-hot encoding using pd.get_dummies()

### 8. Data Alignment

train_processed, test_processed = train_processed.align(
    test_processed,
    join='left',
    axis=1,
    fill_value=0
)
### 9. Preprocessing Function

Built reusable function:
preprocess_data(df)
Applied on reloaded raw data

### Final Result

No missing values

All features numeric

Log transformation applied

Train and test aligned

#### → Dataset is ready for regression modeling

### How to Run
Put dataset in:
data/train.csv
data/test.csv
Run notebook from top to bottom
### Author
##### Shatha Abu Jazar
