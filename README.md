Telco Customer Churn Prediction (End-to-End ML Project)

Dataset: https://www.kaggle.com/datasets/blastchar/telco-customer-churn

Project Overview

This is an end-to-end machine learning classification project focused on predicting whether a telecom customer will churn (Churn = Yes) or stay (Churn = No).

The goal of this project is not only model building but also performing deep exploratory data analysis (EDA) to understand what actually drives customer churn in telecom services.

Workflow:
Data Loading ✅
Data Understanding ✅
Data Cleaning ✅
Exploratory Data Analysis (EDA) ✅
Feature Engineering ✅
Model Training ✅
Model Saving (joblib) ✅

Dataset Information
Source: Kaggle Telco Customer Churn Dataset
Rows: ~7,000+ customers
Target Variable: Churn
Yes → Customer left the service
No → Customer stayed

Exploratory Data Analysis (EDA)

The dataset was analyzed feature by feature against the target variable (Churn) using:

groupby().mean()
barplots for categorical variables
boxplots and violinplots for numerical distributions
KDE plots for density comparison
correlation heatmap for numeric features
Key Insights

Strong Churn Drivers

Contract Type: Month-to-month customers churn significantly more than one-year or two-year contracts
InternetService: Fiber optic users churn more than DSL users
PaymentMethod: Electronic check users show higher churn rates
Tenure: Short-term customers are much more likely to churn

Engagement Features

Customers with no OnlineSecurity / TechSupport / DeviceProtection are more likely to churn
Customers without Partner or Dependents show higher churn

Financial Signals

Higher MonthlyCharges slightly correlate with churn
TotalCharges is strongly influenced by tenure, making tenure more important
❌ Weak / No Signal Features
Gender (almost no impact)
PhoneService
MultipleLines (weak separation)
SeniorCitizen (moderate but not strong alone)
🛠 Feature Engineering
Dropped irrelevant column:
customerID
Handled categorical variables using encoding:
Binary encoding: Yes/No → 1/0
One-hot encoding: InternetService, Contract, PaymentMethod
Converted TotalCharges to numeric and handled missing/blank values
Scaled numerical features where needed
Model Training

Multiple classification models were tested:

Logistic Regression
Decision Tree
Random Forest
K-Nearest Neighbors

Best model selected based on evaluation metrics such as accuracy and recall.

Model Saving

Final trained model saved using joblib:

import joblib

joblib.dump(model, "telco_churn_model.pkl")
Conclusion

Customer churn in telecom is mostly driven by:

Contract type (short-term vs long-term)
Service quality features (TechSupport, Security, etc.)
Billing behavior (Payment method, monthly charges)
Customer tenure (strongest predictor)

Financial features alone are not enough — customer engagement and service experience matter more.

Tech Stack
Python 
Pandas
NumPy
Scikit-learn
Matplotlib
Seaborn
Joblib

Author:
Asadbek Xamidov
