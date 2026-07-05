Telco Customer Churn Dashboard

This project analyzes telecom customer churn using Python for preprocessing/modeling and Power BI for interactive visualization.

========================================
DATASET
========================================

- Source: Kaggle - Telco Customer Churn Dataset
  https://www.kaggle.com/blastchar/telco-customer-churn
- Records: 7,043 customers
- Target variable: Churn (Yes/No)

========================================
DATA CLEANING & PREPROCESSING (PYTHON)
========================================

- Converted TotalCharges from object to numeric
- Handled missing values using median imputation
- Dropped irrelevant columns such as customerID
- Encoded categorical features using LabelEncoder
- Applied SMOTE to balance churn classes

========================================
MODELING
========================================

- Model: RandomForestClassifier
- Trained on SMOTE-balanced training data
- Evaluated with:
  - accuracy_score
  - roc_auc_score
  - confusion_matrix

Expected performance range:
- Accuracy: ~82% to 84%
- ROC-AUC: ~0.84 to 0.86

========================================
POWER BI DASHBOARD FEATURES
========================================

- Donut chart: overall churn rate
- Stacked bar chart: churn by contract type
- Histogram: tenure distribution among churned customers
- Boxplots: MonthlyCharges and TotalCharges by churn
- Interactive slicers:
  - service types
  - payment method
  - demographics

Dashboard file:
- Telco_Churn_Dashboard.pbix

========================================
KEY INSIGHTS
========================================

- Month-to-month contract customers churn the most
- Customers with tenure below 6 months are at high churn risk
- Churn is higher among customers without Online Security or Tech Support
- Paperless billing appears associated with higher churn rates

========================================
TOOLS & TECHNOLOGIES
========================================

- Python
  - pandas
  - seaborn
  - scikit-learn
  - imbalanced-learn (SMOTE)
- Power BI
- Jupyter Notebook / VS Code

========================================
HOW TO USE
========================================

1. Clone the repository
2. Run the churn modeling script (for example: churn_model.py)
3. Open Telco_Churn_Dashboard.pbix in Power BI Desktop
4. Connect/refresh using cleaned_churn_data.csv

========================================
ACKNOWLEDGEMENTS
========================================

- Kaggle Telco Customer Churn Dataset
- Open-source community resources
