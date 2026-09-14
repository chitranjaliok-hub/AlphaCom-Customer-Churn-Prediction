# AlphaCom-Customer-Churn-Prediction

## 📌 Project Overview

This project focuses on predicting customer churn for AlphaCom Telecommunications using machine learning.

The objective is to identify customers who are likely to discontinue their services so that the company can take proactive retention actions.

This is an end-to-end binary classification project covering:

- Exploratory Data Analysis
- Data preprocessing
- Feature engineering
- Class imbalance handling
- Baseline modelling
- Advanced machine learning models
- Hyperparameter tuning
- Probability threshold optimization
- Model evaluation
- Feature importance analysis
- Business recommendations

---

## 🎯 Business Problem

Customer churn can significantly impact recurring revenue and customer lifetime value.

The key business objective is to identify potential churners early enough for the company to intervene with targeted retention strategies.

Since missing a customer who is actually going to churn can be more costly than contacting a customer who ultimately stays, **Recall was selected as the primary evaluation metric**.

---

## 📊 Dataset

The AlphaCom Customer Dataset contains **12,055 customer records**.

- **Target variable:** Churn
- **Churn rate:** 28.3%
- **Numerical variables:** Tenure, Monthly Charges, Total Charges
- **Categorical variables:** Customer demographics, services, contract and billing information

---

## 🔎 Exploratory Data Analysis

Key observations from the analysis include:

- Month-to-month contract customers showed the highest churn risk.
- Fiber optic customers with month-to-month contracts represented a particularly high-risk group.
- Customers without online security showed higher churn.
- Customers without technical support showed higher churn.
- Electronic-check users showed higher churn.
- Short-tenure customers represented an important churn-risk segment.

These findings were used to guide feature analysis and the business recommendations.

---

## 🛠️ Data Preprocessing

The preprocessing pipeline included:

1. Duplicate and anomaly checks
2. Feature selection
3. Stratified train/validation/test split
4. Missing-value treatment
5. Outlier analysis
6. Feature engineering
7. Class imbalance handling
8. Feature scaling
9. Data leakage checks

Class imbalance was addressed using:

- SMOTE
- Random undersampling

---

## 🤖 Machine Learning Models

A Logistic Regression model was initially developed as the baseline.

Advanced models evaluated included:

- Decision Tree
- Random Forest
- AdaBoost
- Gradient Boosting
- XGBoost

Models were evaluated using:

- Accuracy
- Recall
- Precision
- F1-score
- ROC-AUC

Models were tested using:

- Original data
- SMOTE data
- Undersampled data

---

## ⚙️ Hyperparameter Tuning

Hyperparameter optimization was performed using **GridSearchCV with 5-fold cross-validation**.

Probability threshold tuning was also performed to improve the model's ability to identify churners in line with the business objective.

---

## 📈 Final Model Results

| Model | Threshold | Accuracy | Recall | Precision | F1 | ROC-AUC |
|---|---:|---:|---:|---:|---:|---:|
| **AdaBoost + Undersampling** | 0.51 | 75.79% | **78.00%** | 54.99% | 64.50% | 84.50% |
| XGBoost + Original Data | 0.55 | **77.51%** | 72.30% | **58.14%** | 64.45% | **84.76%** |
| AdaBoost + SMOTE | 0.50 | 76.18% | 74.85% | 55.78% | 63.93% | 84.57% |
| GBM + Undersampling | 0.55 | 76.73% | 73.28% | 56.77% | 63.98% | 84.65% |
| GBM + SMOTE | 0.50 | 76.95% | 72.10% | 57.25% | 63.83% | 84.34% |

### 🏆 Selected Model

**AdaBoost + Random Undersampling**

- Test Recall: **78.00%**
- Test ROC-AUC: **84.50%**
- Test Accuracy: **75.79%**
- Probability Threshold: **0.51**

AdaBoost with undersampling was selected because the project prioritized **churn detection (Recall)**.

XGBoost provided a slightly higher Accuracy and ROC-AUC and was identified as the stronger alternative when a more balanced overall performance is preferred.

---

## 🔑 Key Churn Drivers

Feature importance analysis identified several important churn drivers, including:

- Contract type — Month-to-month
- Customer tenure
- Monthly charges
- Total charges
- Technical support
- Electronic check payment
- Fiber optic service
- Dependents
- One-year contract
- Online security

Month-to-month contracts, tenure and monthly charges were among the most important factors influencing churn. :contentReference[oaicite:1]{index=1}

---

## 💡 Business Recommendations

Based on the analysis, the following retention strategies were proposed:

- Encourage month-to-month customers to move to longer-term contracts.
- Focus onboarding and engagement efforts on newer customers.
- Introduce targeted loyalty incentives for customers with higher monthly charges.
- Investigate service quality and customer experience among fiber optic customers.
- Provide targeted technical support incentives.
- Encourage customers to adopt automatic payment methods.
- Develop targeted retention strategies for high-risk customer segments.
- Promote online security services to customers who currently do not have them.

---

## 🧰 Technologies & Techniques

### Programming & Data Analysis
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

### Machine Learning
- Scikit-learn
- Logistic Regression
- Decision Tree
- Random Forest
- AdaBoost
- Gradient Boosting
- XGBoost

### Techniques
- Exploratory Data Analysis
- Feature Engineering
- Feature Scaling
- SMOTE
- Random Undersampling
- GridSearchCV
- Cross-validation
- Threshold Optimization
- Feature Importance
- Classification Metrics

---

## 📂 Repository Structure

```text
AlphaCom-Customer-Churn-Prediction/
│
├── README.md
├── Alphacom_Capstone_Project.ipynb
│
└── reports/
    └── Alphacom Churn - Capstone Project.pdf
