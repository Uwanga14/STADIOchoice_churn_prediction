# Model 2: Random Forest Classifier

## Objective

The objective of this model is to improve churn prediction performance by capturing more complex relationships between customer engagement, subscription behaviour, and churn.

## Model Technique

**Algorithm:** Random Forest Classifier

Random Forest is an ensemble learning algorithm that combines multiple decision trees to improve predictive accuracy and reduce overfitting.

## Hyperparameters

```python
RandomForestClassifier(
    n_estimators=200,
    max_depth=10,
    min_samples_split=5,
    random_state=42
)
```

### Parameter Description

- `n_estimators=200`
  - Uses 200 decision trees.

- `max_depth=10`
  - Controls tree complexity and reduces overfitting.

- `min_samples_split=5`
  - Prevents unnecessary node splitting.

- `random_state=42`
  - Ensures reproducible results.

## Features Used

The Random Forest model was trained using all engineered and transformed customer features.

## Feature Importance Results

The most important predictors were:

| Feature | Importance |
|----------|-----------:|
| watch_hours | 18.9% |
| last_login_days | 13.5% |
| recency_score | 13.3% |
| low_engagement | 10.0% |
| high_engagement | 7.8% |
| number_of_profiles | 4.9% |
| daily_engagement_ratio | 3.7% |

## Key Findings

Watch Hours, Last Login Days, and Recency Score were the strongest predictors of churn. These findings demonstrate that customer activity and engagement have the greatest influence on subscriber retention.

## Evaluation Metrics

The following metrics were used:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC Score

## Related Script

**File:** `model2_random_forest.py`

## How to Run

```bash
python model2_random_forest.py
```

## Expected Benefit

Random Forest can identify complex behavioural patterns that may not be captured by Logistic Regression, resulting in improved churn prediction performance and stronger business insights for subscriber retention strategies.
