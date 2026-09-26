# Model 1: Logistic Regression

## Objective

The objective of this model is to establish a baseline churn prediction model that provides interpretable results and identifies the factors influencing customer churn.

## Model Technique

**Algorithm:** Logistic Regression

Logistic Regression is a supervised machine learning classification algorithm that estimates the probability that a customer will churn.

## Hyperparameters

```python
LogisticRegression(
    random_state=42,
    max_iter=1000
)
```

### Parameter Description

- `random_state=42`
  - Ensures reproducible results.

- `max_iter=1000`
  - Increases the number of optimisation iterations to ensure model convergence.

## Features Used

The model was trained using both original and engineered features.

Key predictors included:

- watch_hours
- last_login_days
- avg_watch_time_per_day
- number_of_profiles
- engagement_score
- watch_intensity
- inactive_customer
- recency_score
- low_engagement
- high_engagement

## Key Findings

The strongest predictors identified by Logistic Regression were:

- Last Login Days
- Low Engagement
- Number of Profiles
- Watch Hours
- High Engagement

Customers who had not logged in recently or displayed low engagement were more likely to churn, while highly engaged customers were less likely to cancel their subscriptions.

## Evaluation Metrics

The following metrics were used:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC Score

## Related Script

**File:** `model1_logistic_regression.py`

## How to Run

```bash
python model1_logistic_regression.py
```

## Expected Benefit

Logistic Regression provides a transparent and interpretable baseline model that can explain how customer engagement influences churn behaviour.
