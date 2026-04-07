# 📊 Telecom Customer Churn Prediction

## 🚀 Project Overview
This project predicts customer churn in a telecom company using machine learning. It helps identify customers who are likely to leave so the business can take preventive actions.

---

## 🧠 Problem Statement
Customer churn is a major issue in telecom. The objective of this project is to:
- Analyze customer data
- Identify churn patterns
- Build a predictive model to classify churn

---

## 🛠️ Tech Stack
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- MySQL
- SQLAlchemy

---

## 📂 Project Workflow

### 1. Data Extraction
- Connected to MySQL database
- Loaded data into Pandas DataFrame

```python
engine = create_engine("mysql+pymysql://user:password@host/database")
df = pd.read_sql("SELECT * FROM telecom_churn_data", engine)
```

---

### 2. Data Preprocessing
- Handled missing values
- Converted categorical variables
- Feature transformations

---

### 3. Exploratory Data Analysis (EDA)
- Analyzed churn distribution
- Visualized key relationships
- Created correlation heatmap

---

### 4. Feature Engineering
- Created new features:
  - tenure_days
  - calls_per_gb
  - sms_per_call

---

### 5. Model Building
Models used:
- Logistic Regression
- Random Forest

Steps:
- Train-test split (80/20)
- Model training

---

### 6. Model Evaluation
Metrics:
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

```python
print(classification_report(y_test, y_pred))
print(roc_auc_score(y_test, y_prob))
```

---

### 7. Final Output
- Generated churn probability
- Created churn flag

```python
df['churn_prob'] = model.predict_proba(X)[:,1]
df['CHURN_FLAG'] = (df['churn_prob'] > 0.5).astype(int)
```

- Exported results:

```python
df.to_csv("churn_predictions.csv", index=False)
```

---

## 📈 Results
- Successfully predicted customer churn
- Identified key influencing factors:
  - Customer usage
  - Tenure
  - Engagement

---

## 📦 Deliverables
- Jupyter Notebook (.ipynb)
- Dataset (.csv)
- Model outputs
- Visualizations

---

## 🔑 Key Insights
- Low engagement users are more likely to churn
- Tenure is a strong predictor
- Feature engineering improved model performance

---

## 📌 Future Improvements
- Use XGBoost / LightGBM
- Hyperparameter tuning
- Model deployment (Flask / Streamlit)

---

## 👨‍💻 Author
Rahul Yadav
