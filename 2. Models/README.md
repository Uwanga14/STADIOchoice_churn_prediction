# Models

## Overview

The objective of this project is to develop machine learning models that can accurately predict customer churn on a streaming platform. Two classification models were selected and evaluated using the Netflix Customer Churn Dataset. The selected models were chosen because they provide a balance between interpretability and predictive performance.

---

# Model 1: Logistic Regression

## Purpose

Logistic Regression is used as the baseline model for this project. The model predicts the probability of a customer churning based on customer demographics, subscription information, viewing behaviour, and engineered engagement features.

## Reason for Selection

Logistic Regression was selected because:

- It is one of the most widely used algorithms for binary classification problems.
- It is easy to understand and interpret.
- It identifies whether features increase or decrease the likelihood of churn.
- It provides a useful benchmark against which more advanced models can be compared.
- It allows business stakeholders to understand the relationship between customer behaviour and churn.

## Key Features Used

- Watch Hours
- Last Login Days
- Average Watch Time Per Day
- Number of Profiles
- Engagement Score
- Watch Intensity
- Inactive Customer
- Recency Score
- Low Engagement
- High Engagement

## Expected Outcome

The model is expected to identify the key variables influencing churn and provide a baseline level of predictive performance for comparison purposes.

---

# Model 2: Random Forest Classifier

## Purpose

Random Forest is used as the primary churn prediction model. The model combines multiple decision trees to improve prediction accuracy and identify complex behavioural patterns associated with customer churn.

## Reason for Selection

Random Forest was selected because:

- It can capture non-linear relationships between variables.
- It handles interactions between features automatically.
- It is less prone to overfitting than individual decision trees.
- It performs well on customer churn classification problems.
- It provides feature importance scores that identify the strongest predictors of churn.
- It often achieves higher predictive accuracy than simpler classification models.

## Key Features Used

- Watch Hours
- Last Login Days
- Average Watch Time Per Day
- Number of Profiles
- Engagement Score
- Watch Intensity
- Inactive Customer
- Recency Score
- Low Engagement
- High Engagement
- Shared Account
- Daily Engagement Ratio

## Expected Outcome

The model is expected to achieve higher predictive accuracy than Logistic Regression while identifying the most important factors influencing subscriber churn.

---

# Model Evaluation

The performance of both models will be evaluated using the following metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC Score
- Confusion Matrix

The model with the strongest overall performance will be recommended for deployment and future integration with the STADIOchoice data environment.

## Conclusion

Logistic Regression was selected to provide a simple and interpretable baseline model, while Random Forest was selected as the primary predictive model because of its ability to capture complex customer behaviour patterns. Comparing both models allows the project to evaluate the trade-off between interpretability and predictive performance and identify the most suitable solution for churn prediction.
