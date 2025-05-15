
# 📘 RoboSense Dataset Usage Guide

This document provides detailed, step-by-step instructions for researchers and developers on how to reuse and extend the RoboSense dataset for machine learning applications, hazard prediction, and spatio-temporal sensor fusion analysis.

---

## 🔍 1. Load and Explore the Dataset

```python
import pandas as pd

# Load merged synthetic dataset
df = pd.read_csv('Synthetic_Dataset.csv', parse_dates=[['Date', 'Time']])
df['Timestamp'] = pd.to_datetime(df['Date_Time'])
df.set_index('Timestamp', inplace=True)
```

---

## 🔎 2. Filter Data by Condition or Sensor Suite

```python
# Filter by condition
normal_df = df[df['Condition'] == 'Normal']
hazard_df = df[df['Condition'] == 'Hazard_1']

# Filter by specific suite
amr1_df = df[df['Suite_ID'] == 'AMR_1']
```

---

## 🧪 3. Prepare for Machine Learning

```python
from sklearn.model_selection import train_test_split

X = df.drop(columns=['Condition'])
y = df['Condition'].map({'Normal': 0, 'Hazard_1': 1})

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
```

---

## 🤖 4. Train a Classifier

```python
from sklearn.ensemble import RandomForestClassifier
clf = RandomForestClassifier()
clf.fit(X_train, y_train)
```

---

## 📊 5. Evaluate Model Performance

```python
from sklearn.metrics import classification_report
y_pred = clf.predict(X_test)
print(classification_report(y_test, y_pred))
```

---

## 🔁 6. Cross-Domain Validation

To assess generalizability:
- Train on `Synthetic_Dataset.csv`
- Test on real hazard segments from `Real_Dataset.csv`
- Apply same preprocessing pipeline

---

## 🧩 7. Inject Hazards into Synthetic Normal Data

You may inject additional synthetic hazards using the helper script `Inject_Hazards_and_ML_Model.html`.

```python
# Example pseudo-injection point
injection_point = 50000
normal_df.iloc[injection_point:injection_point+len(hazard_df)] = hazard_df.values
```

---

## 📂 File Descriptions

| File Name                    | Description |
|-----------------------------|-------------|
| `Real_Dataset.csv`          | Contains real sensor data (normal + hazard) |
| `Synthetic_Dataset.csv`     | Synthetic normal and hazard data |
| `Inject_Hazards_and_ML_Model.html` | Notebook for hazard injection and ML testing |

---

## 🛠️ Requirements

- Python 3.7+
- pandas, scikit-learn, matplotlib, numpy

Install with:
```bash
pip install pandas scikit-learn matplotlib numpy
```

---

## 📬 Contact

**Amr Khamis**  
GitHub: [Amr-Khamis-84](https://github.com/Amr-Khamis-84)
