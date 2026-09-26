# Preprocessing

## Objective

The purpose of preprocessing is to prepare the Netflix Customer Churn Dataset for machine learning modelling by improving data quality and converting all variables into a format suitable for classification algorithms.

## Input Dataset

**Input File:** Netflix Customer Churn Dataset

## Preprocessing Techniques

The following preprocessing steps were applied:

### 1. Data Quality Assessment
- Checked for missing values.
- Checked for duplicate records.
- Verified data types for all variables.

### 2. Removal of Non-Predictive Features
- Removed the `customer_id` column because it uniquely identifies customers but does not contribute to churn prediction.

### 3. One-Hot Encoding
Categorical variables were converted into numerical variables using one-hot encoding.

The following variables were encoded:

- Gender
- Subscription Type
- Region
- Device
- Payment Method
- Favourite Genre

### 4. Dataset Preparation
The processed dataset contains:

- Numerical features
- Encoded categorical features
- Target variable (`churned`)

### 5. Feature Scaling
Numerical variables were standardised before training the Logistic Regression model to ensure all features operated on a similar scale.

## Output Dataset

**Output File:** `preprocessed.csv`

The output dataset contains 45 machine-learning-ready features, including encoded categorical variables and the churn target.

## Related Script

**File:** `preprocessing.py`

## How to Run

```bash
python preprocessing.py
```

## Expected Benefit

Preprocessing ensures that the dataset is clean, consistent, and suitable for model development while reducing the risk of poor model performance caused by data quality issues.
