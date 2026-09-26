# Comparison of Logistic Regression and Random Forest

## Objective

The purpose of this comparison is to evaluate the performance of the Logistic Regression and Random Forest models and determine which model is most suitable for predicting customer churn.

## Performance Comparison

| Metric | Logistic Regression | Random Forest |
|----------|----------|----------|
| Accuracy | 64.7% | 97.6% |
| Precision | 58.8% | 97.4% |
| Recall | 99.4% | 97.8% |
| F1 Score | 73.9% | 97.6% |
| ROC-AUC | 71.9% | 99.7% |

## Confusion Matrix Comparison

### Logistic Regression

| Actual / Predicted | Retained (0) | Churned (1) |
|----------|----------|----------|
| Retained (0) | 147 | 350 |
| Churned (1) | 3 | 500 |

### Random Forest

| Actual / Predicted | Retained (0) | Churned (1) |
|----------|----------|----------|
| Retained (0) | 484 | 13 |
| Churned (1) | 11 | 492 |

## Performance Analysis

The Logistic Regression model achieved a high recall score of 99.4%, indicating that it successfully identified almost all churned customers. However, it incorrectly classified 350 retained customers as churned, resulting in low precision and reduced overall accuracy. This suggests that the model was overly sensitive to churn and tended to overpredict customer cancellations.

The Random Forest model produced substantially better results across all evaluation metrics. The model achieved an accuracy of 97.6%, precision of 97.4%, recall of 97.8%, F1-score of 97.6%, and ROC-AUC score of 99.7%. The confusion matrix showed only 24 incorrect predictions out of 1,000 observations, demonstrating excellent predictive performance and balanced classification.

## Feature Importance Results

The Random Forest model identified the following features as the most important predictors of churn:

| Feature | Importance |
|----------|----------|
| Watch Hours | 18.9% |
| Last Login Days | 13.5% |
| Recency Score | 13.3% |
| Low Engagement | 10.0% |
| High Engagement | 7.8% |
| Number of Profiles | 4.9% |
| Daily Engagement Ratio | 3.7% |

The results indicate that customer engagement and platform activity are the strongest indicators of subscriber retention and churn.

## Advantages and Limitations

### Logistic Regression

**Advantages**

- Easy to interpret and explain.
- Provides coefficient values that show the direction of feature influence.
- Computationally efficient.

**Limitations**

- Assumes linear relationships between variables and churn.
- Produced a large number of false positives.
- Lower predictive performance.

### Random Forest

**Advantages**

- Captures complex and non-linear relationships.
- Handles interactions between variables automatically.
- Provides strong predictive performance.
- Produces feature importance rankings.

**Limitations**

- Less interpretable than Logistic Regression.
- Requires greater computational resources.

## Recommendation

The Random Forest model is recommended as the preferred model for deployment because it significantly outperformed the Logistic Regression model across all evaluation metrics. The model achieved an accuracy of 97.6% compared to 64.7% for Logistic Regression and demonstrated a much stronger ability to distinguish between churned and retained subscribers.

Although Logistic Regression was valuable for understanding customer behaviour and identifying key churn drivers, the Random Forest model is better suited for operational use because of its superior predictive accuracy and balanced performance.

## Related Script

**File:** `model_comparison.py`

## How to Run

```bash
python model_comparison.py
```

## Conclusion

Both models identified customer engagement as the primary driver of churn. Variables such as Watch Hours, Last Login Days, Recency Score, High Engagement, and Low Engagement consistently emerged as important predictors. The Random Forest model delivered the strongest overall performance and is therefore the preferred solution for supporting customer retention initiatives and churn prediction within STADIOstream.
