# ML-Project-Credit-Risk-Evaluation
Credit Risk Prediction Project
This project focuses on building a machine learning model to assess credit risk and predict the likelihood of loan default based on customer financial and credit history. The project follows a structured pipeline, from data preprocessing and feature engineering to model selection, hyperparameter tuning, and deployment via a Streamlit web app on Streamlit Cloud.

Dataset Overview
We use three datasets and merge them using the cust_id column:

Bureau Dataset

Contains customer credit history, including open/closed accounts, delinquency, total loan months, total DPD (Days Past Due), and credit utilization ratio.
Customer Dataset

Provides demographic details like age, gender, marital status, employment status, income, residence type, and years at current address.
Loan Dataset

Includes loan-related information such as loan purpose, loan type, sanctioned amount, net disbursement, tenure, outstanding principal, and loan defaults.
Project Workflow
1. Data Preprocessing & Exploratory Data Analysis (EDA)
Merged the three datasets using cust_id.
Cleaned the data, handled missing values, and removed irrelevant columns.
Performed visualizations and statistical analysis to understand data distribution and outliers.
Removed outliers to improve model robustness.
2. Feature Engineering
Created new features for better predictive power:
Loan-to-Income Ratio = loan_amount / income
Delinquency Ratio = delinquent_months / total_loan_months
Average DPD per Delinquency = total_dpd / delinquent_months
Removed features with little or no impact on the target variable.
Calculated Variance Inflation Factor (VIF) to remove multicollinearity.
Evaluated feature importance using Information Value (IV) and finalized features with IV > 0.02.
3. Feature Encoding
Applied categorical encoding to transform non-numeric features.
4. Model Training & Evaluation
Trained three models for comparison:

Logistic Regression
Random Forest
XGBoost (XGB)
5. Handling Class Imbalance & Model Selection
Attempt 1: XGB without handling class imbalance.
Attempt 2: Logistic Regression & XGB with Under Sampling.
Attempt 3: Logistic Regression with SMOTE-TOMEK for imbalance handling.
Attempt 4: XGB with SMOTE-TOMEK + Hyperparameter Tuning (Optuna).
Findings:

There was minimal difference between XGB and Logistic Regression.
Logistic Regression was chosen as the final model due to better interpretability.
6. Model Performance & Evaluation
Implemented ROC-AUC Curve to evaluate model discrimination.
Performed K-statistics to validate the model.
Saved the best model for deployment.
Deployment
Built a Streamlit app for real-time credit risk predictions.
Deployed the app on Streamlit Cloud, allowing users to input customer details and get a credit risk assessment dynamically.
Key Technologies Used
Libraries: Pandas, NumPy, Scikit-learn, XGBoost, Optuna, Matplotlib, Seaborn, Joblib.
Machine Learning: Logistic Regression, Random Forest, XGBoost.
Imbalance Handling: Under Sampling, SMOTE-TOMEK.
Hyperparameter Tuning: Optuna.
Deployment: Streamlit, Streamlit Cloud.
