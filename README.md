# Customer Credit Consumption Prediction (End-to-End ML Project)

## Overview

This project focuses on predicting customer credit card consumption (`cc_cons`) using historical transaction and behavioral data.
The goal was to build a robust machine learning pipeline that can accurately estimate future spending for customers with missing target values.

The project follows a **complete data science lifecycle**, from raw data integration to final model deployment.

---

## Project Structure

project/
│
├── data/
│   ├── raw/
│   │   ├── raw_file_1.csv
│   │   ├── raw_file_2.csv
│   │   └── raw_file_3.csv
│   │
│   ├── processed/
│   │   └── customer_360.csv
│   │
│   └── output/
│       └── new_predictions.csv
│
├── notebooks/
│   └── customer_prediction.ipynb
│
├── visuals/
│   ├── model_comparison.png
│   ├── line_chart.png
│   └── scatter_plot.png
│
├── model/
│   └── model.joblib
│
└── README.md

---

## Problem Statement

A subset of customers does not have recorded credit consumption values.

> Predict the **credit card consumption for the next three months** for these customers using available behavioral and financial features.

---

## Project Workflow

### Raw Data Files

These are the original datasets used in this project:

- <a href="https://github.com/Yashridla27/customer-credit-consumption-regression/blob/main/CreditConsumptionData.xlsx">Credit-Consumption-Data</a>
- <a href="https://github.com/Yashridla27/customer-credit-consumption-regression/blob/main/CustomerBehaviorData.xlsx">Customer-Behavior-Data</a>
- <a href="https://github.com/Yashridla27/customer-credit-consumption-regression/blob/main/CustomerBehaviorData.xlsx">Customer-Demographics</a>

---

### Data Integration (Customer 360 View)

* Combined multiple datasets into a unified Customer 360 dataset
* Ensured consistency across customer IDs
* Created a holistic view of customer behavior

File: data/processed/customer_360.csv

---

### Data Preprocessing

* Handled missing values carefully
* Encoded categorical variables
* Ensured correct data types
* Split data into:

  * Training data (15000 records)
  * Prediction data (5000 records)

---

### Feature Engineering

Created features like:

* Total credit & debit spending
* Average transaction value
* Spending trends
* Credit utilization
* Transaction consistency

---

### Feature Selection

* Applied Recursive Feature Elimination (RFE)
* Reduced multicollinearity

---

### Data Standardization

* Applied StandardScaler
* Ensured uniform scaling

---

### Model Building & Comparison

Models used:

* Linear Regression
* Decision Tree
* Random Forest
* XGBoost
* LightGBM
* CatBoost

---

### Model Evaluation

Metrics:

* R² Score
* RMSPE

Focus:

* Train vs Test performance
* Generalization

---

### Model Selection

Final Model: Linear Regression

Why:

* High R² (~0.86)
* Low RMSPE (~0.26)
* Minimal overfitting

---

### Hyperparameter Tuning

* Used GridSearchCV
* No improvement over Linear Regression

---

### Final Prediction Pipeline

Steps:

1. Feature Selection
2. Scaling
3. Prediction

Output: <a href="https://github.com/Yashridla27/customer-credit-consumption-regression/blob/main/new_predictions.csv">New_Predictions</a>

---

## Visualizations

### Model Comparison (R² Score)

<img width="711" height="480" alt="Screenshot 2026-04-07 013332" src="https://github.com/user-attachments/assets/5548aadc-d442-43f8-a22a-43526cdd0eaf" />


This graph compares different machine learning models based on their **R² Score**, highlighting how well each model explains the variance in the data.
It helped in identifying the most effective model for prediction.

---

### Model Comparison (RMSPE)

<img width="711" height="476" alt="Screenshot 2026-04-07 013251" src="https://github.com/user-attachments/assets/fa4a29f3-b24c-423c-9e11-f2574d32435d" />


This visualization compares models using **RMSPE (Root Mean Square Percentage Error)**, which measures prediction accuracy in percentage terms.
It is especially important for financial data where relative error matters.

---

### Linearity Check (Scatter Plot)

<img width="803" height="674" alt="Screenshot 2026-04-07 013418" src="https://github.com/user-attachments/assets/a904cb97-00bd-41bd-bdd6-080c9594aea0" />


A scatter plot of **actual vs predicted values** was used to analyze the relationship between features and target.
The strong linear pattern observed indicates that the data is highly linear, which supports the effectiveness of **Linear Regression** as the final model.


---

## Jupyter Notebook

<a href="https://github.com/Yashridla27/customer-credit-consumption-regression/blob/main/customer_credit_consumption_regression.ipynb">customer-credit-consumption-pipeline</a>

Contains full workflow:

* Data cleaning
* Feature engineering
* Model building
* Evaluation

---

## Model Saving using Joblib

<a href="https://github.com/Yashridla27/customer-credit-consumption-regression/blob/main/lr_model_pipeline.pkl">Joblib</a>

Example:
joblib.dump({'model': model, 'scaler': scaler}, 'model/model.joblib')

---

## Key Learnings

* Feature engineering is more important than model complexity
* Model comparison is essential
* Avoid overfitting
* Build end-to-end pipelines

---

## Future Improvements

* FastAPI deployment
* Dashboard creation
* Automation

---

## Author

Yash Ridla
