# Customer-churn-Analysis-and-Prediction

## Overview

Predicting customer churn is a pivotal task for any business. This project focuses on using existing customer data to forecast whether customers will leave the service. Here's a brief description of the input and output of this project:

- Input: Customer data comprising 19 attributes, including customer demographics and call data (such as cost, frequency, international calls, day or night calls, etc.).
- Output: The output is binary, where 0 indicates the customer will churn and 1 indicates the customer will not churn.

## EDA

Visual numeric features.

<p align="center">
    <image src="https://github.com/nguyendv02/Customer-churn-Analysis-and-Prediction/assets/137906492/cd394911-7bd4-42d9-bdc0-c81a6eb9141b" width="600">
</p>
        
We'll visualize the correlation matrix to identify highly correlated attributes.
        
<p align="center">
    <image src="https://github.com/nguyendv02/Customer-churn-Analysis-and-Prediction/assets/137906492/4d081204-8c47-456f-b867-d035e8abb545" width="600">
</p>
        
Columns 'Total day charge', 'Total eve charge', 'Total night charge', and 'Total intl charge' are removed as they are linearly related to their respective minute columns.

## 
### Preprocessing
Normalization techniques applied:
- Categorical columns: One-hot encoding
- Numerical columns:
    - Min-max scaling for most numerical columns.
    - Both Min-Max scaling and Standard scaling for columns exhibiting a bell-shaped distribution.

### Metric
The target variable Churn is imbalanced:
- False (No churn): 2278-
- True (Churn): 388
Given the imbalance, F1-score are used as the evaluation metric instead of accuracy, as it balances precision and recall.

### Modeling
Models Explored:
- Logistic Regression: {'C': [0.001, 0.01, 0.1, 1, 10, 100]}
- Decision Tree: {'max_depth': [3, 5, 7, 10], 'min_samples_split': [2, 5, 7, 10]}
- Random Forest: Parameter grid: {'n_estimators': [50, 100, 200], 'max_depth': [3, 5, 7, 10]}

### Result
Best Model:
- Random Forest with MinMaxScaler and {'max_depth': 10, 'n_estimators': 200}.
- F1-score: 76.64% (validation) - 72.62% (test).
- Accuracy (addditional): 93.75% (validation) - 93.1% (test).

Here is confusion matrix for test set.

<p align="center">
    <image src="https://github.com/nguyendv02/Customer-churn-Analysis-and-Prediction/assets/137906492/342485d2-54ae-42d2-9c49-4be688e66323" width="600">
</p>
        
Additional Considerations for Future Work:
Addressing the balance between minimizing false negatives (missed churn predictions) and managing false positives is essential for enhancing the predictive accuracy of the model.


### Contact:
Email: nguyendv02@gmail.com or 20520657@gm.uit.edu.vn
