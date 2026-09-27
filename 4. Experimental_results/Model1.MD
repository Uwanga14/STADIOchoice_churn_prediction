# Model 1: Logistic Regression Performance

## Objective

The purpose of the Logistic Regression model was to establish a baseline churn prediction model and identify the factors most strongly associated with customer churn.

## Performance Metrics

| Metric | Result |
|----------|----------|
| Accuracy | 64.7% |
| Precision | 58.8% |
| Recall | 99.4% |
| F1 Score | 73.9% |
| ROC-AUC | 71.9% |

## Confusion Matrix

| Actual / Predicted | Retained (0) | Churned (1) |
|----------|----------|----------|
| Retained (0) | 147 | 350 |
| Churned (1) | 3 | 500 |

## Classification Report

| Class | Precision | Recall | F1 Score |
|----------|----------|----------|----------|
| Retained (0) | 0.98 | 0.30 | 0.45 |
| Churned (1) | 0.59 | 0.99 | 0.74 |

## Model Interpretation

The Logistic Regression model achieved a high recall score of 99.4%, meaning it successfully identified almost all churned customers. However, the model incorrectly classified a large number of retained customers as churned, resulting in 350 false positive predictions and reducing overall accuracy.

Feature coefficient analysis indicated that the strongest positive predictors of churn were:

- Last Login Days
- Low Engagement
- Subscription Type (Basic)

The strongest negative predictors of churn were:

- Watch Hours
- High Engagement
- Number of Profiles

These findings suggest that customers who engage less frequently with the platform and have not logged in recently are significantly more likely to churn. Customers with higher viewing activity and stronger engagement are more likely to remain subscribed.

## Key Findings

- The model correctly identified most churned customers.
- The model overpredicted churn, resulting in many false positives.
- Customer activity and engagement were the strongest drivers of churn.
- The model provides valuable business insights but limited predictive performance compared to more advanced machine learning techniques.

## Related Script

**File:** `model1_logistic_regression.py`

## How to Run

```bash
python model1_logistic_regression.py
```

## Conclusion

The Logistic Regression model provided a useful baseline and helped explain the factors influencing customer churn. However, the relatively low accuracy and large number of false positive predictions indicate that more sophisticated models may be better suited to this prediction task.
