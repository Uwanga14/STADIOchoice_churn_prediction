Subscriber Churn Prediction Using Random Forest
Project Overview
This project analyses subscriber churn using three related datasets:
subscriber information, subscription billing history, and streaming
viewing activity. The aim is to prepare the data, explore factors
associated with churn, build a Random Forest classification model, and
evaluate its ability to distinguish between churned and non-churned
subscribers.
The analysis was developed in the Jupyter Notebook SS3_PartB.ipynb
using Python and common data analysis and machine learning libraries.
Objectives
- Inspect and clean the subscriber, billing, and viewing datasets.
- Standardise inconsistent text categories and encode categorical
  variables.
- Combine the datasets using subscriber_id.
- Explore churn patterns and relationships between variables.
- Train and evaluate a Random Forest classifier.
- Visualise model performance and identify features that contribute
  most to predictions.
Datasets
The notebook uses the following CSV files from the
Uwanga14/netflix_customer_churn GitHub repository:
1. dataset1_subscriber.csv --- subscriber information, acquisition
   channel, subscription type and status, and churn status.
2. dataset2_subscription_billing_history.csv --- billing and
   subscription variables such as plan name, monthly fee, payment
   status, payment failures, downgrade flag, auto-renewal, retention
   outcome and tenure.
3. dataset3_streaming_viewing_activity.csv --- streaming activity
   variables such as viewing duration, days since last watch, content
   type and device type.
The datasets are merged using subscriber_id. The merge can produce
multiple rows for a subscriber when billing or viewing records contain
repeated entries.
Tools and Libraries
- Python
- pandas --- data loading, cleaning, transformation and merging
- NumPy --- numerical operations
- Matplotlib and Seaborn --- data visualisation
- scikit-learn --- data splitting, preprocessing, Random Forest
  modelling and evaluation
Workflow
1. Data inspection and preparation
The notebook inspects dataset structures, column types and missing
values. Text values and column names are cleaned where necessary, and
category labels are standardised to reduce inconsistencies.
2. Categorical encoding
Categorical variables such as acquisition channel, subscription type,
plan name, payment status, content type and device type are converted
into numerical indicator variables using one-hot encoding. Binary fields
such as downgrade and auto-renewal are mapped to numeric values where
appropriate.
3. Excluding unsuitable predictors
Identifier and date fields are excluded from the modelling features
where they are not directly suitable for prediction or could introduce
target leakage. The retention_outcome variable is excluded from the
predictors because it may directly reflect the outcome of a retention
process. The target is churn_status, where 1 represents churned
and 0 represents not churned.
4. Combining datasets
The cleaned subscriber dataset is merged with the billing and viewing
datasets using subscriber_id. Numeric columns are prepared for
modelling. Because these datasets can contain repeated records per
subscriber, the merged data may include multiple rows for the same
person.
5. Train/test split
The data is split into training and testing sets using an 80/20 split,
random_state=42, and stratification by the churn target.
Stratification preserves approximately the same class proportions in
both sets.
6. Random Forest model
A scikit-learn pipeline is used with:
- Median imputation for missing numeric feature values.
- A Random Forest classifier with 300 trees.
- min_samples_leaf=2.
- class_weight='balanced'.
- random_state=42.
The model is trained to classify records as churned or not churned.
7. Evaluation and visualisation
The notebook evaluates the model using accuracy, precision, recall,
F1-score and ROC-AUC. It also produces a classification report and
confusion matrix.
Visualisations include:
- Churn distribution.
- Churn rate by subscription type.
- Churn rate by acquisition channel.
- Correlation heatmap.
- Confusion matrix.
- ROC curve.
- Precision, recall and F1-score comparison.
- Top 15 Random Forest feature importances.
Reported Model Results
The notebook's reported test results are:
  Metric        Result
  Accuracy       92.6%
  Precision      92.9%
  Recall         91.1%
  F1-score       92.0%
  ROC-AUC        0.981
The confusion matrix reports:
                     Predicted not churned   Predicted churned
  Actual not churned                    25,643               1,654
  Actual churned                         2,131              21,770
These results indicate strong classification performance on the test
rows used in the notebook. They should be treated as preliminary until
the validation checks described below have been completed.
Feature Importance
The feature-importance plot identifies days_since_last_watch and
watch_duration as the most important features in the fitted Random
Forest, followed by tenure and payment_failure_count. This suggests
that viewing engagement and payment behaviour are useful signals for the
model.
Feature importance describes how the fitted model uses variables; it
does not establish that a variable causes churn or indicate the
direction of its relationship with churn.
Limitations and Validation Recommendations
1. Repeated subscribers: The merged dataset contains multiple rows
   for some subscribers. A random row-level split can place records
   from the same subscriber in both training and testing sets,
   potentially inflating performance. Use a subscriber-level split or a
   time-based validation approach for a more realistic assessment.
2. Prediction timing: Confirm that each predictor would be
   available at the time a churn prediction is made. Variables recorded
   after cancellation or after a retention intervention should not be
   used to predict earlier churn.
3. Target leakage: Checking column names for known leakage terms is
   only an initial screening step. Review the meaning and timing of all
   predictors, including subscription-status variables and any fields
   derived from churn outcomes.
4. Duplicate records and merge effects: Check duplicate rows and
   examine whether joins multiply billing or viewing records. Consider
   aggregating data to one row per subscriber using a clearly defined
   observation period.
5. Generalisation: Evaluate the final model on subscribers not seen
   during training and, if possible, on a later time period. Compare
   the resulting metrics with the current row-level split results.
How to Run
1. Open SS3_PartB.ipynb in Jupyter Notebook, JupyterLab or Google
   Colab.
2. Ensure the required libraries are available: pandas, numpy,
   matplotlib, seaborn and scikit-learn.
3. Run the notebook cells in order. The notebook reads CSV files from
   the GitHub repository, so an internet connection is required unless
   the files are downloaded and the paths are updated.
4. Review the data checks, model metrics and visualisations.
5. Before using the model for real retention decisions, complete the
   subscriber-level and target-leakage validation described above.
Conclusion
This project demonstrates a complete initial workflow for subscriber
churn analysis, from data preparation and exploratory visualisation to
Random Forest classification and model evaluation. The preliminary
results are strong, and the feature-importance analysis highlights
viewing engagement and payment behaviour as important predictive
signals. Further validation using subscriber-level or time-based
splitting is necessary before relying on these results for new
subscribers or operational retention decisions.
