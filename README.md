## Project Overview

This project focuses on predicting customer churn using machine learning techniques. The goal is to identify customers who are likely to leave a bank based on their demographic, financial, and account-related information.

### 1. Data Loading and Exploration

The dataset contains 10,000 customer records and includes features such as credit score, geography, gender, age, tenure, balance, number of products, credit card status, activity status, estimated salary, and the target variable `Exited`.

The dataset was inspected for:

* Data types and dataset structure
* Missing values
* Duplicate records
* Categorical variable distributions

No missing values or duplicate records were found.

### 2. Data Preprocessing

Categorical variables were converted into numerical representations:

* `Gender` was encoded using `LabelEncoder`.
* `Geography` was transformed using one-hot encoding with `drop_first=True`.

The original categorical variables were therefore converted into numerical features suitable for machine learning models.

### 3. Feature Selection and Data Splitting

Relevant customer attributes were selected as input features (`X`), while `Exited` was used as the target variable (`y`).

The dataset was divided into:

* 80% training data
* 20% testing data

A fixed `random_state=42` was used to ensure reproducible results.

### 4. Feature Scaling

`StandardScaler` was applied to standardize the numerical features. The scaler was fitted only on the training data and then used to transform both the training and test sets.

### 5. Machine Learning Models

Several classification algorithms were trained and evaluated:

* Random Forest
* Logistic Regression
* Support Vector Machine (SVM)
* K-Nearest Neighbors (KNN)
* Gradient Boosting

The models were evaluated using:

* Confusion Matrix
* Precision
* Recall
* F1-score
* Accuracy

### 6. Model Comparison

The initial results showed that tree-based models performed best on this dataset.

| Model               | Accuracy |
| ------------------- | -------: |
| Random Forest       |   86.65% |
| Logistic Regression |   81.10% |
| SVM                 |   80.35% |
| KNN                 |   83.00% |
| Gradient Boosting   |   86.75% |

Gradient Boosting achieved the highest accuracy among the tested models, while Random Forest achieved a very similar performance.

### 7. Feature Importance

Feature importance from the Random Forest model was analyzed to understand which customer characteristics contributed most to the model's predictions.

### 8. Feature Engineering

Additional features were created to potentially improve the model:

* `BalanceZero` – indicates whether a customer has a zero balance.
* `AgeGroup` – groups customers into different age ranges.
* `BalanceToSalaryRatio` – compares account balance to estimated salary.
* `ProductUsage` – combines the number of products with customer activity.
* `TenureGroup` – groups customers according to their tenure.

Interaction features such as `Male_Germany` and `Male_Spain` were also created.

Categorical `AgeGroup` and `TenureGroup` variables were converted into dummy variables using one-hot encoding.

### 9. Final Random Forest Model

After feature engineering, the Random Forest model achieved an accuracy of approximately **86%** on the test set.

The final model achieved:

* Precision for churned customers: **0.75**
* Recall for churned customers: **0.47**
* F1-score for churned customers: **0.58**
* Overall accuracy: **86%**

### Conclusion

This project demonstrates an end-to-end machine learning workflow for customer churn prediction, including data exploration, preprocessing, feature engineering, model training, evaluation, and model comparison. The results show that ensemble tree-based models, particularly Random Forest and Gradient Boosting, performed better than the linear and distance-based models tested.
