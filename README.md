🛡️ Fraud Detection Using Machine Learning

A complete ML pipeline for detecting financial fraud with advanced preprocessing, feature engineering, imbalanced learning techniques, and model comparison.

📌 Project Overview

Financial fraud often represents less than 0.1% of real-world transactions—making it extremely difficult to detect with traditional machine learning models.
This project builds a robust fraud detection pipeline that:

Cleans and preprocesses raw transactional data

Handles outliers intelligently

Encodes categorical features

Manages class imbalance (with and without SMOTE)

Trains multiple ML models

Compares their performance based on precision, recall, F1-score

Identifies the best model for real-world fraud systems

The project notebook demonstrates step-by-step reasoning, model training, evaluation, and recommendation based on business trade-offs.

📂 Dataset

The dataset consists of anonymized financial transactions with features such as:

step – time step

type – transaction type

amount – transferred amount

oldbalanceOrg / newbalanceOrig

oldbalanceDest / newbalanceDest

isFraud – target variable

⚠️ Highly imbalanced: fraud cases represent a very small portion of total transactions.

🧹 Data Cleaning & Preprocessing
✔ Outlier Handling

First attempted global outlier removal → removed many genuine frauds

Corrected approach: remove outliers only from non-fraud transactions

Fraud rows are kept intact to avoid losing crucial patterns

✔ Feature Engineering

Removed non-useful ID columns: nameOrig, nameDest

Performed OneHotEncoding on type

Selected 11 meaningful features for the model

✔ Train–Test Split

Used stratify=y to maintain fraud ratio in train/test sets

⚖️ Imbalance Handling

This project evaluates models with and without SMOTE:

❌ Without SMOTE

Models trained on natural imbalance.

✔ With SMOTE

Minority class oversampled using:

from imblearn.over_sampling import SMOTE
X_train_res, y_train_res = SMOTE().fit_resample(X_train, y_train)

🤖 Models Trained

The following ML models were trained and tested:

Decision Tree Classifier

Logistic Regression

XGBoost Classifier

LightGBM Classifier

Performance was evaluated using:

Precision

Recall

F1-score

Confusion Matrix

ROC-AUC (for LightGBM)

📊 Model Performance Summary
🔹 Without SMOTE
Model	Precision (Fraud)	Recall (Fraud)	F1-Score
Decision Tree	0.91	0.88	0.89
Logistic Regression	0.97	0.52	0.68
XGBoost	0.91	0.82	0.86
LightGBM	0.66	0.98	0.79
🔹 With SMOTE
Model	Precision (Fraud)	Recall (Fraud)	F1-Score
Decision Tree	0.74	0.96	0.84
Logistic Regression	0.03	0.93	0.06
XGBoost	0.39	0.99	0.56
LightGBM	0.38	0.99	0.55
🏆 Best Model & Recommendation
🔥 Best Balanced Model: Decision Tree (without SMOTE)

It achieves strong precision (0.91) and recall (0.88) with the highest F1-score (0.89).

📈 When to Use LightGBM

If maximum recall is the priority (catching nearly every fraud), use LightGBM without SMOTE (Recall: 0.98).

🚫 Why Not Use SMOTE?

SMOTE caused models to:

Predict too many false frauds

Drop precision drastically (0.38–0.03 range)

Reduce overall F1-score

Therefore, SMOTE is not recommended for this dataset.
