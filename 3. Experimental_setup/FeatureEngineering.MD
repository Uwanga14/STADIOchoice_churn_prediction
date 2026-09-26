# Feature Engineering

## Objective

The objective of feature engineering is to create new features that better capture customer engagement, platform usage behaviour, and churn risk. These engineered features are intended to improve the predictive performance of the churn prediction models by providing additional business insights beyond the original dataset attributes.

## Input Dataset

**Input File:** `preprocessed.csv`

The preprocessed dataset contains cleaned numerical features and one-hot encoded categorical variables generated during the preprocessing stage.

## Engineered Features

### 1. Engagement Score

**Formula**

```python
engagement_score = watch_hours * avg_watch_time_per_day
```

**Purpose**

This feature combines total viewing hours and average daily watch time into a single engagement metric. Customers with higher engagement scores are expected to be less likely to churn because they derive more value from the streaming service.

---

### 2. Watch Intensity

**Formula**

```python
watch_intensity = watch_hours / (number_of_profiles + 1)
```

**Purpose**

This feature measures content consumption relative to account sharing. It helps identify whether viewing activity remains high when multiple profiles are present.

---

### 3. Inactive Customer

**Formula**

```python
inactive_customer = (last_login_days > 30)
```

**Purpose**

Customers who have not logged into the platform for more than 30 days are classified as inactive. Such subscribers may have a higher likelihood of cancelling their subscription.

---

### 4. Multiple Profiles

**Formula**

```python
multiple_profiles = (number_of_profiles > 2)
```

**Purpose**

This feature identifies accounts shared by multiple users. Shared accounts may have different retention patterns compared to single-user accounts.

---

## Feature Evaluation

Correlation analysis was performed to assess the relationship between selected features and the target variable (`churned`).

| Feature | Correlation with Churn |
|----------|----------:|
| watch_hours | -0.481 |
| last_login_days | 0.472 |
| inactive_customer | 0.341 |
| avg_watch_time_per_day | -0.218 |
| watch_intensity | -0.217 |
| number_of_profiles | -0.159 |
| engagement_score | -0.102 |
| multiple_profiles | -0.082 |

## Key Findings

Customers who have not logged in recently and are classified as inactive show the highest likelihood of churn, with **last_login_days (0.472)** and **inactive_customer (0.341)** being the strongest positive predictors.

Higher platform engagement reduces churn risk, with **watch_hours (-0.481)**, **avg_watch_time_per_day (-0.218)** and **watch_intensity (-0.217)** showing that more active viewers are less likely to cancel their subscriptions.

## Selected Features for Modelling

Based on correlation analysis and business relevance, the following engineered features will be used in model development:

```python
watch_hours
avg_watch_time_per_day
last_login_days
number_of_profiles
watch_intensity
inactive_customer
engagement_score
```

The `multiple_profiles` feature was evaluated but demonstrated a weak relationship with churn and is therefore expected to contribute limited predictive value.

## Related Script

**File:** `feature_engineering.py`

## How to Run

```bash
python feature_engineering.py
```

## Output

The script generates a feature-engineered dataset that is used for training and evaluating the churn prediction models:

```text
feature_engineered.csv
```

## Expected Benefit

The engineered features enhance the representation of customer engagement, account activity and viewing behaviour. Since customer activity and platform engagement are strongly associated with subscriber retention, these features are expected to improve the performance of both the Logistic Regression and Random Forest churn prediction models.
