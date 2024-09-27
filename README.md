# Time-Series-Anomaly-Detection-with-LSTM-Autoencoders

# Credit Card Fraud Detection 

## Overview 
Credit card fraud is a critical issue in the financial sector, leading to significant losses. This project utilizes machine learning techniques to develop a model that can accurately detect fraudulent transactions. The model is designed to handle the imbalanced nature of fraud detection data and is evaluated on various performance metrics to ensure its effectiveness.

## Table of Contents
1. Introduction

2. Problem Statement

3. Dataset

4. Data Pre-processing

5. Feature Engineering

6. Algorithms

7. Evaluation Metrics

8. Results and Discussion

9. How to Use

10. Conclusion

# Introduction
Credit card fraud detection involves identifying fraudulent transactions from a large pool of legitimate transactions. This project focuses on building a machine learning model that can accurately detect fraud while minimizing false positives. The model is trained and evaluated using a dataset containing over 1 million credit card transactions.

# Problem Statement
The main challenge in credit card fraud detection is dealing with the highly imbalanced nature of the data, where fraudulent transactions make up a tiny fraction of the total transactions. The objective is to create a model that can effectively detect fraud without raising too many false alarms.

# Dataset
The Datasets are taken from the Kaggle (https://www.kaggle.com/datasets/kartik2112/fraud-detection) The dataset contains over 1 million transactions, with features such as:

Transaction amount

Merchant details

Customer demographics

Fraud labels

The dataset is divided into training and testing sets. Features were engineered to enhance the model's predictive capabilities.

# Data Pre-processing
### 1. Loading Datasets
The dataset consists of separate CSV files for training and testing. These were combined for analysis and modeling using the Pandas library.

### 2. Handling Class Imbalance
To address class imbalance, Random Under-Sampling was applied to balance the classes by reducing the majority class (non-fraudulent) samples.

### 3. Dropping Unnecessary Columns
Irrelevant columns such as credit card numbers and personal information were dropped to reduce noise and focus on relevant features.

# Feature Engineering
Several features were engineered to improve the model's performance:

### 1. Haversine Distance Calculation
The distance between the customer's location and the merchant's location was calculated. Unusual distances might indicate fraud.

### 2. Age Calculation
Customer age was derived from their date of birth. Age can be a significant factor in fraud detection.

### 3. Fraud Percentage per Merchant
The percentage of fraudulent transactions associated with each merchant was calculated. This helps in identifying merchants with a history of fraud.

# Algorithms
Two ensemble methods were used: Random Forest and XGBoost.

### Random Forest

**Why It’s Important :** Robust against overfitting, provides feature importance ranking, and can handle imbalanced datasets.

**Implementation :** The Random Forest classifier was used as a baseline model.

### XGBoost

**Why It’s Important :** Highly efficient, handles large datasets, includes regularization to reduce overfitting.

**Implementation :** XGBoost was used as the primary model due to its superior performance in handling the complexities of the dataset.

# Evaluation Metrics
To assess the model's performance, the following metrics were used:

### 1. Recall
Measures the proportion of actual frauds correctly identified.

### 2. Precision
Measures the proportion of predicted frauds that were actually frauds.

### 3. F1 Score
The harmonic mean of precision and recall.

### 4. AUC-ROC
Area under the ROC curve, representing the model's ability to distinguish between classes.

### 5. Confusion Matrix
Provides a breakdown of true positives, false positives, true negatives, and false negatives.

# Results and Discussion

### 1. Model Performance Evaluation
### Random Forest:

**Recall :** 92%

**Precision :** 85%

**F1 Score :** 0.88

**AUC-ROC :** 0.96

### XGBoost:

**Recall :** 98%

**Precision :** 82%

**F1 Scor :** 0.90

**AUC-ROC :** 0.98

XGBoost outperformed Random Forest, especially in recall, making it the preferred model for this task.

### 2. Confusion Matrix Analysis
XGBoost had a higher true positive rate, but also a slightly higher false positive rate, which is acceptable in fraud detection.

### 3. Feature Importance and Insights

**Transaction Amount :** Most significant feature.

**Fraud Percentage per Merchant :** Highly influential.

**Haversine Distance :** Critical for fraud detection.

**Customer Age :** Certain age groups are more vulnerable to fraud.

# How to Use

### 1. Clone the repository
```bash
git clone https://github.com/GugulothBhuvan/Credit-Card-Fraud-Detection.git
cd Credit-Card-Fraud-Detection
```

### 2. Install dependencies:
```bash
pip install -r requirements.txt
```
**3.Run the model :** Open the notebook eda-modelling-using-xgboost-recall-98.ipynb in Jupyter or Google Colab and execute the cells to train and evaluate the model.

# Conclusion

This project demonstrates the effectiveness of machine learning in credit card fraud detection. By using advanced algorithms like XGBoost, the model achieved high recall and precision, making it a valuable tool in financial fraud prevention.



