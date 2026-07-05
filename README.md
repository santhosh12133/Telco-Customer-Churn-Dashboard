# Telco Customer Churn Dashboard

An interactive churn analysis project built with Python and Power BI to help understand **which telecom customers are likely to churn** and what factors are associated with churn behavior.

## Project Overview

Customer churn prediction helps telecom businesses reduce revenue loss by identifying at-risk customers early.  
This repository contains:

- Data cleaning and preprocessing code in Python
- A cleaned churn dataset
- Dashboard screenshots for visual insights

## Repository Contents

- `PYTHON CODE FOR CLEAN DATA.txt` — Python workflow for data cleaning, preprocessing, balancing, and model training
- `cleaned_churn_data.csv` — Processed dataset used for reporting/dashboarding
- `Screenshot (24).png` and `Screenshot (25).png` — Dashboard visuals
- `README.md` — Project documentation (this file)

## Dataset

The project is based on the Telco customer churn dataset (CSV format), with fields typically including:

- Customer demographic details
- Subscription/service information
- Billing information (e.g., `MonthlyCharges`, `TotalCharges`)
- Churn label (`Churn`)

## What the Python Pipeline Does

The script performs the following key steps:

1. Imports required libraries (`pandas`, `numpy`, `seaborn`, `sklearn`, `imblearn`)
2. Loads churn data from CSV
3. Converts `TotalCharges` to numeric and handles missing values with median imputation
4. Encodes categorical columns using `LabelEncoder`
5. Splits data into train/test sets
6. Applies **SMOTE** to balance churn classes in training data
7. Trains a **RandomForestClassifier**
8. Evaluates performance using:
   - Accuracy
   - ROC-AUC
   - Confusion matrix heatmap
9. Exports cleaned dataset to CSV

## Dashboard

Dashboard screenshots are included to present churn trends and key metrics:

- `Screenshot (24).png`
- `Screenshot (25).png`

If you are using Power BI/Tableau, load `cleaned_churn_data.csv` and recreate or extend visualizations such as:

- Churn distribution
- Monthly charges vs churn
- Contract type/service usage impact
- Segment-wise churn comparison

## Tech Stack

- **Python**
- **Pandas, NumPy**
- **Seaborn, Matplotlib**
- **Scikit-learn**
- **Imbalanced-learn (SMOTE)**
- **Power BI** (dashboarding)

## How to Run

### 1) Clone the repository

```bash
git clone https://github.com/santhosh12133/Telco-Customer-Churn-Dashboard.git
cd Telco-Customer-Churn-Dashboard
```

### 2) Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
```

### 3) Update file paths in script

The current script uses local absolute Windows paths. Replace them with paths in your local environment before running.

### 4) Run the Python script

You can run the code from `PYTHON CODE FOR CLEAN DATA.txt` after renaming it to `clean_data.py` (recommended), or copy the content into a Python file and execute.

## Suggested Improvements

- Rename `PYTHON CODE FOR CLEAN DATA.txt` to `clean_data.py`
- Use **relative paths** instead of absolute local paths
- Add a `requirements.txt`
- Add the original raw dataset file name and source link in the repository
- Include the Power BI dashboard file (`.pbix`) for reproducibility

## Results Snapshot

Model metrics (Accuracy and ROC-AUC) are printed by the script at runtime.  
Confusion matrix heatmap is plotted using Seaborn.

## Contributing

Contributions are welcome. Feel free to open an issue or submit a pull request for improvements.

## License

No license file is currently included. Consider adding a `LICENSE` (e.g., MIT) for open-source usage clarity.
