# Credit Card Fraud Detection: Supervised & Unsupervised Approaches
This repository contains two projects exploring different machine learning techniques to detect fraudulent credit card transactions. Using a common dataset, we investigate both supervised and unsupervised methods to tackle the challenge of identifying rare fraudulent activities within a large volume of transactions.

The primary challenge in this dataset is its severe class imbalance, where fraudulent transactions account for only 0.17% of the data. Both projects address this issue using different strategies.

## Structure at a Glance
This repository is organized into two main projects, each contained within its own Jupyter Notebook.

### 1. Supervised Learning for Fraud Detection
[View Supervised Learning Notebook](https://github.com/MinaGong/fraud_detection/blob/main/fraud_detection_supervised.ipynb)

This project focuses on building a classification model using labeled data. The goal is to train a model that can accurately distinguish between fraudulent and normal transactions, with a strong emphasis on maximizing recall for the fraud class to minimize missed fraud cases.

**Key Steps**:
* **Exploratory Data Analysis (EDA)**: Investigated the distributions of Time, Amount, and the anonymized V features.
* **Data Preprocessing**: Transformed and scaled the Time and Amount features to prepare them for modeling.
* **Handling Class Imbalance**: Used Random Undersampling to create a balanced training dataset.
* **Model Selection**: Evaluated several classifiers (Logistic Regression, Random Forest, SVC, XGBoost) using cross-validation and selected Logistic Regression for its strong recall performance.
* **Hyperparameter Tuning**: Optimized the Logistic Regression model using GridSearchCV.
* **Final Evaluation**: Assessed the tuned model on the original, imbalanced test set to measure its real-world effectiveness.


### 2. Unsupervised Learning for Anomaly Detection
[View Unsupervised Learning Notebook](https://github.com/MinaGong/fraud_detection/blob/main/fraud_detection_unsupervised.ipynb)

This project takes an unsupervised approach, treating fraud detection as an anomaly detection problem. The goal is to identify transactions that are "few and different" without using any pre-existing labels. This method is particularly useful for discovering new or evolving fraud patterns.

**Key Steps**:
* **Algorithm Selection**: Utilized the Isolation Forest algorithm, which is efficient for large datasets and effective at identifying outliers.
* **Anomaly Scoring**: The model assigned an anomaly score to every transaction in the dataset.
* **Pattern Analysis**: Analyzed the characteristics of the transactions flagged as anomalies and discovered key patterns related to:

    * Low transaction amounts.
    * Transactions occurring during off-peak hours.

* **Monitoring Strategy**: Proposed a practical monitoring system by ranking transactions based on their anomaly scores to prioritize review.