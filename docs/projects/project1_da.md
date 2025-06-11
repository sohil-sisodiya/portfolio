# Customer Churn Prediction

## Overview

This project aimed to develop a predictive model that identifies telecom customers who are likely to cancel their service (i.e., churn). By proactively identifying high-risk customers, the company can design targeted retention strategies, reduce churn rates, and increase customer lifetime value.

## Business Context

Customer churn is a critical issue for subscription-based businesses. Retaining existing customers is often more cost-effective than acquiring new ones. Understanding why customers leave—and predicting who is likely to leave—can help businesses reduce churn and improve customer satisfaction.

The dataset used in this project was a public telecom dataset, simulating real-world customer behavior, including demographics, account information, and service usage.

## Dataset

- **Source:** Public dataset simulating telecom customer data  
- **Size:** ~7,000 rows × 20 features  
- **Target Variable:** `Churn` (binary: Yes/No)  
- **Features Included:**  
  - Customer demographics (gender, senior citizen, partner, dependents)  
  - Service details (phone service, internet service, contract type)  
  - Usage metrics (monthly charges, total charges, tenure)  
  - Payment methods and billing information

## Methodology

### 1. Exploratory Data Analysis (EDA)

- Analyzed churn rates across demographic groups and contract types  
- Identified missing or inconsistent values in `TotalCharges`, and handled them using imputation  
- Created visualizations (histograms, bar plots, box plots) to explore relationships between features and churn  
- Observed higher churn rates among:
  - Month-to-month contract customers  
  - Customers with fiber optic internet  
  - Customers with higher monthly charges but shorter tenure

### 2. Feature Engineering

- Converted categorical variables to numerical using one-hot encoding  
- Created a new feature: `AvgMonthlySpend = TotalCharges / Tenure`  
- Binned tenure into categories (e.g., 0–6 months, 6–12 months, etc.) to capture customer lifecycle segments  
- Standardized numerical features for use in distance-based models

### 3. Model Building

Trained multiple classification models:

- **Logistic Regression** – Used as a baseline  
- **Random Forest Classifier** – Captured non-linear relationships and feature interactions  
- **XGBoost Classifier** – Delivered strong performance with regularization and early stopping

Used `StratifiedKFold` cross-validation to ensure balanced class distribution across folds.

### 4. Evaluation

Used a held-out test set (20%) to evaluate performance. Metrics included:

- Accuracy: 0.81  
- Precision: 0.72  
- Recall: 0.76  
- F1-Score: 0.74  
- **ROC AUC:** 0.87  

The confusion matrix and ROC curve indicated strong classification performance, especially in correctly identifying churners.

### 5. Interpretability

- **Feature Importance (Random Forest & XGBoost):**
  - Contract type
  - Tenure
  - Monthly charges
  - Internet service type
- **SHAP Values:** Used SHAP (SHapley Additive exPlanations) to interpret model predictions and explain individual outcomes

## Deployment

- Packaged the trained model using `joblib`  
- Developed a Flask-based web app with a form to input customer details  
- Deployed the application on **Heroku**  
- Provided a user-friendly dashboard that shows the churn probability and key factors influencing the prediction

## Key Learnings

- Model interpretability is critical for stakeholder trust and actionable insights  
- Data quality and preprocessing (especially feature engineering) had a major impact on model performance  
- Deployment, even in a minimal form, is a valuable exercise in bridging data science and product usability

## Repository

[🔗 GitHub Repository](https://github.com/yourusername/customer-churn-prediction)

---

This project highlights my end-to-end data science skills—from problem understanding and data preparation to model building, evaluation, and deployment. It also reflects my focus on making results interpretable and useful for real business decisions.
