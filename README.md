# Analysis of Sampling Techniques on an Imbalanced Credit Card Dataset

## 1. Introduction

In real-world classification problems, data is often imbalanced, where one class has significantly fewer samples than the other. This imbalance can bias machine learning models and reduce their ability to correctly predict the minority class. The aim of this assignment is to study how different sampling methods can balance the dataset and how these methods affect the performance of various classification algorithms.

## 2. Dataset

The experiment uses a credit card transaction dataset containing two classes:

* Class 0: Normal transactions
* Class 1: Fraudulent transactions

Since fraudulent transactions are very rare, the dataset is highly imbalanced, making it suitable for studying resampling techniques.

## 3. Sampling Techniques

To handle class imbalance, the following five sampling strategies are applied:

1. SMOTE – Generates synthetic samples for the minority class.
2. Random Oversampling – Duplicates minority class samples randomly.
3. Random Undersampling – Removes samples from the majority class.
4. SMOTEENN – Combines SMOTE with noise removal using Edited Nearest Neighbours.
5. SMOTETomek – Combines SMOTE with Tomek Links to clean overlapping samples.

## 4. Machine Learning Models

Five different classifiers are trained on each balanced dataset:

* Logistic Regression
* Decision Tree Classifier
* Random Forest Classifier
* Support Vector Classifier (SVC)
* XGBoost Classifier

## 5. Accuracy Results

| Model               | SMOTE | RandomOver | RandomUnder | SMOTEENN | SMOTETomek |
| ------------------- | ----- | ---------- | ----------- | -------- | ---------- |
| Logistic Regression | 50.10 | 52.24      | 63.18       | 69.23    | 70.12      |
| Decision Tree       | 59.25 | 65.27      | 68.72       | 28.36    | 30.25      |
| Random Forest       | 90.45 | 72.41      | 32.17       | 42.58    | 41.85      |
| SVC                 | 78.25 | 56.24      | 47.23       | 33.44    | 40.12      |
| XGBoost             | 81.25 | 12.85      | 57.36       | 32.25    | 52.74      |

## 6. Best Sampling Technique for Each Model

| Model               | Best Sampling Method | Accuracy (%) |
| ------------------- | -------------------- | ------------ |
| Logistic Regression | SMOTETomek           | 70.12        |
| Decision Tree       | RandomUnder          | 68.72        |
| Random Forest       | SMOTE                | 90.45        |
| SVC                 | SMOTE                | 78.25        |
| XGBoost             | SMOTE                | 81.25        |

## 7. Discussion

The results show that oversampling techniques, especially SMOTE, are highly effective for ensemble models such as Random Forest and XGBoost. Undersampling improves performance for simpler models but may cause loss of important information. Hybrid methods like SMOTEENN and SMOTETomek help in reducing noise and class overlap, leading to more stable predictions in some cases.

## 8. Conclusion

This study demonstrates that selecting an appropriate sampling technique is crucial when working with imbalanced datasets. No single method is best for all classifiers; however, synthetic oversampling methods generally provide better learning for complex models, while simpler models may benefit from controlled undersampling or hybrid approaches.
# Sampling_Assignment
