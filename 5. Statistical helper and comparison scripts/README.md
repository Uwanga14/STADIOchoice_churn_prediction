
# Part C: Model Results and Evaluation

## Overview

The purpose of this phase of the project was to evaluate the performance of two machine learning models developed to predict subscriber churn:

1. Logistic Regression (Model 1)
2. Random Forest (Model 2)

Both models were trained using the Netflix Customer Churn Dataset and evaluated using standard classification metrics, including Accuracy, Precision, Recall, F1-Score, ROC-AUC, Confusion Matrices, and Feature Importance analysis.

---

# Model 1: Logistic Regression

## Objective

Logistic Regression was selected as the baseline model because it is simple, interpretable, and widely used for binary classification problems such as customer churn prediction.

## Performance Results

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

## Interpretation

The Logistic Regression model was very effective at identifying churned customers, achieving a Recall score of 99.4%. This means that almost all customers who actually churned were correctly identified by the model.

However, the model incorrectly classified many retained customers as churned, resulting in 350 false positive predictions. This reduced overall accuracy and precision, indicating that the model tends to overpredict churn.

## Key Findings

- Customers who had not logged in recently were more likely to churn.
- Low engagement was strongly linked to churn.
- Customers with higher watch hours were less likely to cancel their subscriptions.
- The model provides useful business insights but limited predictive performance.

---

# Model 2: Random Forest

## Objective

Random Forest was selected because it can capture complex relationships between customer behaviour, engagement, and churn.

## Performance Results

| Metric | Result |
|----------|----------|
| Accuracy | 97.6% |
| Precision | 97.4% |
| Recall | 97.8% |
| F1 Score | 97.6% |
| ROC-AUC | 99.7% |

## Confusion Matrix

| Actual / Predicted | Retained (0) | Churned (1) |
|----------|----------|----------|
| Retained (0) | 484 | 13 |
| Churned (1) | 11 | 492 |

## Interpretation

The Random Forest model achieved excellent performance across all evaluation metrics. The model successfully identified both churned and retained customers while producing very few misclassifications.

Only 24 customers were classified incorrectly out of 1,000 observations, demonstrating a strong ability to distinguish between subscribers who are likely to churn and those who are likely to remain subscribed.

## Feature Importance Results

| Feature | Importance |
|----------|----------|
| Watch Hours | 18.9% |
| Last Login Days | 13.5% |
| Recency Score | 13.3% |
| Low Engagement | 10.0% |
| High Engagement | 7.8% |
| Number of Profiles | 4.9% |
| Daily Engagement Ratio | 3.7% |

## Key Findings

- Watch Hours was the most important predictor of churn.
- Recent platform activity played a significant role in customer retention.
- Customer engagement and viewing behaviour were the strongest indicators of churn risk.
- Highly engaged customers were significantly less likely to cancel their subscriptions.

---

# Model Comparison

## Performance Comparison

| Metric | Logistic Regression | Random Forest |
|----------|----------|----------|
| Accuracy | 64.7% | 97.6% |
| Precision | 58.8% | 97.4% |
| Recall | 99.4% | 97.8% |
| F1 Score | 73.9% | 97.6% |
| ROC-AUC | 71.9% | 99.7% |

## Comparison Discussion

The Random Forest model outperformed the Logistic Regression model across all performance metrics.

While Logistic Regression achieved a higher Recall score, it generated a large number of false positives, resulting in lower Precision and Accuracy. This means the model was too aggressive in predicting churn and incorrectly flagged many loyal customers as potential churn risks.

The Random Forest model provided a much better balance between Precision and Recall while maintaining excellent overall accuracy. The ROC-AUC score of 99.7% indicates an exceptional ability to distinguish between churned and retained customers.

## Conclusion

Both models identified customer engagement and platform activity as the strongest predictors of churn. Features such as Watch Hours, Last Login Days, Recency Score, and Low Engagement consistently emerged as important churn indicators.

The Random Forest model is the preferred model because it achieved significantly better predictive performance and produced fewer classification errors. The results demonstrate that customer engagement is the primary driver of subscriber retention and should remain a key focus area for future retention strategies.
