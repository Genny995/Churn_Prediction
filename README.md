# Churn Prediction Project

This project aims to **predict customer churn** for a telecom company using machine learning. Customer churn occurs when clients decide to discontinue their relationship with a company. Understanding the drivers behind churn is highly valuable, as retaining existing customers is generally more cost-effective than constantly acquiring new ones.

---

## Dataset

The dataset used is the **Telco Customer Churn** dataset, which contains demographic, service subscription, contract, and financial information for each customer.  

### Columns

**Demographic Information**
- `customerID` – unique identifier for each customer  
- `gender` – customer's gender (Male/Female)  
- `SeniorCitizen` – whether the customer is a senior (1 = yes; 0 = no)  
- `Partner` – whether the customer has a partner (Yes/No)  
- `Dependents` – whether the customer has dependents (Yes/No)  

**Subscribed Services**
- `tenure` – number of months the customer has stayed with the company  
- `PhoneService` – whether the customer has phone service (Yes/No)  
- `MultipleLines` – whether the customer has multiple lines (No/Yes/No Phone Service)  
- `InternetService` – type of Internet service (DSL/Fiber optic/No)  
- `OnlineSecurity` – whether the customer has online security (Yes/No/No Internet service)  
- `OnlineBackup` – whether the customer has online backup (Yes/No/No Internet service)  
- `DeviceProtection` – whether the customer has device protection (Yes/No/No Internet service)  
- `TechSupport` – whether the customer has tech support (Yes/No/No Internet service)  
- `StreamingTV` – whether the customer has streaming TV (Yes/No/No Internet service)  
- `StreamingMovies` – whether the customer has streaming movies (Yes/No/No Internet service)  

**Contract Information**
- `Contract` – type of contract (Month-to-month, One year, Two Years)  
- `PaperlessBilling` – whether the customer uses paperless billing (Yes/No)  
- `PaymentMethod` – customer's payment method (Electronic check/Mailed check/Bank Transfer/Credit card)  

**Financial Information**
- `MonthlyCharges` – customer's monthly spending  
- `TotalCharges` – total amount spent by the customer during their tenure  

**Target Variable**
- `Churn` – indicates if the customer has left the company (Yes/No)  

---

## Project Overview

The project is divided into two main phases:

### 1. Exploratory Data Analysis (EDA)
- Visualize data distributions and relationships using **graphs** (histograms, countplots, pie charts).  
- Identify correlations between features and churn using **statistical tests**:  
  - **ANOVA F-test** for numerical features  
  - **Chi-squared test** for categorical features  
- Determine the **most relevant features** for predicting churn.  

### 2. Predictive Modeling
Evaluate and tune several machine learning models to predict customer churn:
  
- **Random Forest**  
- **XGBoost**  
- **Gradient Boosting**  
- **AdaBoost**
  
For each model, the optimal hyperparameters were selected using `RandomizedSearchCV`, which allowed for an efficient search over a predefined parameter grid. The evaluation metrics provided insight into which model best balances precision and recall, particularly considering the imbalanced nature of churn data.

### Model Evaluation and Selection

After hyperparameter tuning, all models were evaluated on the test set using **Accuracy** and **Weighted F1 score** to measure their predictive performance.

![Comparison between the four models tested](Models%20Results%20Comparison.png)

