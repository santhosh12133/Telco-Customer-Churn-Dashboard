import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder, StandardScaler
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, roc_auc_score
from imblearn.over_sampling import SMOTE

df = pd.read_csv("C:/Users/teju4/Desktop/WA_Fn-UseC_-Telco-Customer-Churn.csv")
print("imported sucessfully")
print(df.head)

df.info()
# Convert TotalCharges to numeric
df['TotalCharges'] = pd.to_numeric(df['TotalCharges'], errors='coerce')

# Fill missing values (no inplace)
df['TotalCharges'] = df['TotalCharges'].fillna(df['TotalCharges'].median())


sns.countplot(x='Churn', data=df)
sns.boxplot(x='Churn', y='MonthlyCharges', data=df)

le = LabelEncoder()
for col in df.select_dtypes(include='object'):
    df[col] = le.fit_transform(df[col])

X = df.drop(['customerID','Churn'], axis=1)
y = df['Churn']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
print("data splited sucessfull")

sm = SMOTE(random_state=42)
X_train_res, y_train_res = sm.fit_resample(X_train, y_train)

clf = RandomForestClassifier(random_state=42)
clf.fit(X_train_res, y_train_res)
print("model train sucessful")

y_pred = clf.predict(X_test)
print("Accuracy:", accuracy_score(y_test, y_pred))
print("ROC-AUC:", roc_auc_score(y_test, clf.predict_proba(X_test)[:,1]))
sns.heatmap(confusion_matrix(y_test, y_pred), annot=True, fmt='d')

# Save the cleaned and processed dataset to a new CSV file
df.to_csv("C:/Users/teju4/Desktop/cleaned_churn_data.csv", index=False)

print("✅ Cleaned dataset saved successfully to Desktop!")



