# 📱 Syriatel Customer Churn Prediction

## 🧠 Overview

This project analyzes customer data from **Syriatel**, a telecommunications provider, to predict **customer churn** — identifying which users are likely to stop using the service. The project includes data exploration, feature engineering, modeling, evaluation, and actionable insights.

---

## 🎯 Problem Statement

Churn poses a major threat to telecom businesses. The goal is to build a machine learning model that accurately predicts whether a customer will churn based on their service usage patterns and account information.

---

## 🗂️ Project Structure

syriatel-customer-churn/
│
├── data/ # Contains raw and cleaned data
│ └── syriatel_churn_data.csv
│
├── notebooks/ # Jupyter notebooks for EDA & Modeling
│ └── churn_modeling.ipynb
│
├── presentation/ # Slide decks or reports
│
├── requirements.txt # Python package dependencies
├── README.md # Project overview and instructions
└── .gitignore

## Business and Data Understanding
SyriaTel wants to reduce churn. The dataset contains customer service, billing, and contract info.
📊 Data Description
The dataset includes:

Customer demographics and usage patterns

3,333 observations, 20+ features

Target: churn (0 = Stayed, 1 = Churned)

Example features:

international plan, total day charge, customer service calls, voice mail plan, etc.

## Modeling
Models used: Logistic Regression, Decision Tree,
🔍 Exploratory Data Analysis (EDA)
Churn rate is ~14.5%

Churn is higher among customers with:

High daytime usage

International plans

Frequent customer service calls

Most customers don’t use voicemail services

🧪 Data Preparation
Removed irrelevant columns (phone number)

Encoded categorical variables using one-hot encoding

Scaled features using StandardScaler

Removed low-variance features

🤖 Modeling
Algorithms Used:
Logistic Regression

Decision Tree Classifier ✅ (Best Model)

Random Forest (optional if added later)

## Evaluation
Used precision, recall, F1-score to assess model effectiveness.
| Metric    | Logistic Regression | Decision Tree |
| --------- | ------------------- | ------------- |
| Accuracy  | 0.86                | **0.91**      |
| Precision | 0.68                | **0.74**      |
| Recall    | 0.52                | **0.77**      |
| F1-Score  | 0.59                | **0.75**      |
🔹 Confusion Matrix - Decision Tree
lua
Copy
Edit
[[573  23]
 [ 30  74]]
📉 Classification Report
markdown
Copy
Edit
              precision    recall  f1-score   support

           0       0.95      0.96      0.96       596
           1       0.76      0.71      0.74       104

    accuracy                           0.92       700
   macro avg       0.86      0.84      0.85       700
weighted avg       0.91      0.92      0.91       700
🧪 Sample Prediction (Best Model)
python
Copy
Edit
sample = {
    'account length': 120,
    'total day minutes': 300,
    'total day charge': 51.0,
    'customer service calls': 4,
    'international plan_Yes': 1,
    'voice mail plan_Yes': 0,
    ...
}

# Preprocess sample and predict
sample_df = pd.DataFrame([sample])
sample_processed = scaler.transform(sample_df[selected_features])
prediction = dt.predict(sample_processed)

print("Churn Prediction:", "Yes" if prediction[0] == 1 else "No")
✅ Output: Churn Prediction: Yes

🔎 Feature Importance
Feature	Importance
total day charge	0.220
customer service calls	0.190
international plan_Yes	0.160
total intl minutes	0.090
number vmail messages	0.070

## Conclusion
Recommendations for reducing churn are based on feature importance and predictions.
" > README.md
