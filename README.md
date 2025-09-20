# fraud-detection
Summary

This repository contains an exploratory data analysis and machine learning notebook for detecting fraud. The notebook performs data loading, preprocessing, feature engineering, model training, evaluation, and visualization.

Notebook structure

The notebook fraud detection.ipynb contains a mix of Markdown and code cells. Top-level headings and some initial markdown excerpts:

Uploading file to Colab

Importing the dataset

Importing the CSV file

Checking shape of Data

Checking for the null values in the data

Checking the data distribution (balanced or unbalanced)

Highly unbalanced dataset (fraud cases very few compared to normal)

Checking for the outliers in the data

Removing the outliers

Checking the class distribution of isFraud again

Observing that many fraud cases were removed, so handling outliers per-class

Removing unused columns (nameOrig, nameDest)

Encoding the type column using One-Hot-Encoding

What is included
Major Python packages

numpy

pandas

matplotlib

seaborn

scikit-learn

xgboost (if installed in your environment)

Dataset

The notebook loads a CSV dataset (likely a fraud transaction dataset).

Make sure to place the dataset in the same folder or update the path in the notebook.

Models used

Logistic Regression

Random Forest Classifier

XGBoost Classifier

Decision Tree Classifier

Support Vector Machine (SVC)

KNN Classifier

Evaluation metrics

Accuracy Score

Precision, Recall, F1-score

ROC-AUC

Confusion Matrix

Classification Report

Target column

Likely isFraud (binary classification target).

Typical workflow

Load dataset into Pandas.

Perform exploratory data analysis (EDA).

Clean and preprocess data (null values, outliers, encoding categorical variables, scaling features).

Train/test split.

Train multiple ML models.

Evaluate using classification metrics and visualizations.

Compare results of different models.

How to run locally

Clone this repository.

Ensure Python 3.8+ is installed.
