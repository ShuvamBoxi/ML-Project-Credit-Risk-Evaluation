<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Credit Risk Prediction</title>
</head>
<body>
    <h1>Credit Risk Prediction Project</h1>
    <p>This project focuses on building a machine learning model to assess <strong>credit risk</strong> and predict the likelihood of <strong>loan default</strong> based on customer financial and credit history. The solution integrates <strong>data preprocessing, feature engineering, model training, hyperparameter tuning, and deployment</strong> via a <strong>Streamlit app</strong> on <strong>Streamlit Cloud</strong>.</p>
    
    <h2>Dataset Overview</h2>
    <p>We use three datasets and merge them using the <code>cust_id</code> column:</p>
    <ul>
        <li><strong>Bureau Dataset</strong>: Contains customer credit history (open/closed accounts, delinquency, total loan months, DPD, credit utilization ratio).</li>
        <li><strong>Customer Dataset</strong>: Demographic details (age, gender, marital status, employment status, income, residence type, etc.).</li>
        <li><strong>Loan Dataset</strong>: Loan-related information (loan purpose, type, sanctioned amount, tenure, outstanding principal, loan defaults).</li>
    </ul>
    
    <h2>Project Workflow</h2>
    <h3>1. Data Preprocessing & Exploratory Data Analysis (EDA)</h3>
    <ul>
        <li>Merged datasets using <code>cust_id</code>.</li>
        <li>Performed cleaning, handled missing values, and removed irrelevant columns.</li>
        <li>Used visualizations to analyze data distribution and outliers.</li>
    </ul>
    
    <h3>2. Feature Engineering</h3>
    <ul>
        <li>Generated new features:
            <ul>
                <li><strong>Loan-to-Income Ratio</strong>: <code>loan_amount / income</code></li>
                <li><strong>Delinquency Ratio</strong>: <code>delinquent_months / total_loan_months</code></li>
                <li><strong>Average DPD per Delinquency</strong>: <code>total_dpd / delinquent_months</code></li>
            </ul>
        </li>
        <li>Removed low-impact features.</li>
        <li>Calculated <strong>Variance Inflation Factor (VIF)</strong> to reduce multicollinearity.</li>
        <li>Selected features with Information Value (IV) > 0.02.</li>
    </ul>
    
    <h3>3. Feature Encoding</h3>
    <p>Applied categorical encoding to transform non-numeric features.</p>
    
    <h3>4. Model Training & Evaluation</h3>
    <p>Trained three models for comparison:</p>
    <ul>
        <li><strong>Logistic Regression</strong></li>
        <li><strong>Random Forest</strong></li>
        <li><strong>XGBoost (XGB)</strong></li>
    </ul>
    
    <h3>5. Handling Class Imbalance & Model Selection</h3>
    <ul>
        <li>Attempt 1: XGB without handling class imbalance.</li>
        <li>Attempt 2: Logistic Regression & XGB with <strong>Under Sampling</strong>.</li>
        <li>Attempt 3: Logistic Regression with <strong>SMOTE-TOMEK</strong>.</li>
        <li>Attempt 4: XGB with <strong>SMOTE-TOMEK + Hyperparameter Tuning (Optuna)</strong>.</li>
    </ul>
    <p><strong>Final Decision:</strong> Minimal difference between XGB and Logistic Regression, so we chose <strong>Logistic Regression</strong> for its interpretability.</p>
    
    <h3>6. Model Performance & Evaluation</h3>
    <ul>
        <li>Implemented <strong>ROC-AUC Curve</strong> for model evaluation.</li>
        <li>Performed <strong>K-statistics</strong> for validation.</li>
        <li>Saved the best model for deployment.</li>
    </ul>
    
    <h2>Deployment</h2>
    <ul>
        <li>Built a <strong>Streamlit app</strong> for real-time credit risk predictions.</li>
        <li>Deployed the app on <strong>Streamlit Cloud</strong>.</li>
    </ul>
    
    <h2>Key Technologies Used</h2>
    <ul>
        <li><strong>Libraries</strong>: Pandas, NumPy, Scikit-learn, XGBoost, Optuna, Matplotlib, Seaborn, Joblib.</li>
        <li><strong>Machine Learning</strong>: Logistic Regression, Random Forest, XGBoost.</li>
        <li><strong>Imbalance Handling</strong>: Under Sampling, SMOTE-TOMEK.</li>
        <li><strong>Hyperparameter Tuning</strong>: Optuna.</li>
        <li><strong>Deployment</strong>: Streamlit, Streamlit Cloud.</li>
    </ul>
    
    <h2>How to Use the App</h2>
    <ol>
        <li>Input customer details (loan amount, income, credit history, etc.).</li>
        <li>Click <strong>"Predict"</strong> to get the <strong>credit risk score</strong> (default probability).</li>
        <li>View <strong>visualizations</strong> explaining key risk factors.</li>
    </ol>
    
    <h2>Conclusion</h2>
    <p>This project effectively predicts <strong>loan default risk</strong>, aiding financial institutions in <strong>risk assessment</strong> and better <strong>loan decision-making</strong>. By leveraging <strong>feature engineering, model tuning, and deployment</strong>, the solution provides a practical tool for <strong>credit risk analysis</strong>.</p>
</body>
</html>
