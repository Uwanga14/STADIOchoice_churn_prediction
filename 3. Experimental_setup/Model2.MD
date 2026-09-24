# Model 2: Random Forest

## Objective

Random Forest will be used as the primary ensemble model to improve churn prediction performance.

## Model Details

Algorithm:
- Random Forest Classifier

Hyperparameters:
- n_estimators = 200
- max_depth = 10
- min_samples_split = 5
- random_state = 42

## Reason for Selection

Random Forest can identify complex relationships between customer behaviour and churn while reducing overfitting through ensemble learning.

## Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

## Related Script

model2_random_forest.ipynb

## How to Run

Open model2_random_forest.ipynb and execute all cells.

## Output

The notebook generates churn predictions, feature importance scores and model evaluation metrics.
