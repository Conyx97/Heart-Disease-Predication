# 🫀 Heart Disease Prediction

A machine learning project that predicts the presence of heart disease in patients using clinical data. The project covers end-to-end steps: data exploration, feature engineering, model training, and evaluation.

---

## 📁 Project Structure

```
Heart-Disease-Prediction/
│
├── Heart Disease Prediction.ipynb   # Main notebook
├── heart.csv                        # Dataset
└── README.md
```

---

## 📊 Dataset

The dataset used is the **Cleveland Heart Disease** dataset (`heart.csv`), a widely used benchmark in medical ML tasks.

| Feature     | Description                                      |
|-------------|--------------------------------------------------|
| `age`       | Age of the patient                               |
| `sex`       | Sex (1 = male, 0 = female)                       |
| `cp`        | Chest pain type (0–3)                            |
| `trestbps`  | Resting blood pressure (mm Hg)                   |
| `chol`      | Serum cholesterol (mg/dl)                        |
| `fbs`       | Fasting blood sugar > 120 mg/dl (1 = true)       |
| `restecg`   | Resting ECG results (0–2)                        |
| `thalach`   | Maximum heart rate achieved                      |
| `exang`     | Exercise-induced angina (1 = yes)                |
| `oldpeak`   | ST depression induced by exercise                |
| `slope`     | Slope of peak exercise ST segment                |
| `ca`        | Number of major vessels (0–3)                    |
| `thal`      | Thalassemia type                                 |
| `target`    | Heart disease present (1 = yes, 0 = no)          |

---

## 🔍 Workflow

### 1. Data Preprocessing
- Load dataset from CSV
- Check and confirm no null values
- Remove duplicate rows
- Create a working copy for EDA

### 2. Exploratory Data Analysis (EDA)
- Count plots for all categorical variables (`sex`, `cp`, `fbs`, `restecg`, `exang`, `slope`, `ca`, `thal`, `target`)
- Histogram + KDE plots for continuous variables (`age`, `trestbps`, `chol`, `thalach`, `oldpeak`)
- Correlation heatmap across all features
- Box plots for outlier detection in continuous columns

### 3. Feature Selection
- Computed correlation of each feature with `target`
- Dropped low-correlation features: **`chol`** and **`fbs`**

### 4. Model Training
Data split: **80% train / 20% test** (`random_state=42`)

Three classification models were trained and evaluated:

| Model                 | Notes                            |
|-----------------------|----------------------------------|
| Logistic Regression   | Baseline linear model            |
| Random Forest         | Ensemble of 100 decision trees   |
| XGBoost               | Gradient boosting classifier     |

### 5. Evaluation
- Accuracy score
- Classification report (Precision, Recall, F1)
- Confusion matrix heatmap (Random Forest)

---

## 📈 Results

| Model               | Accuracy  |
|---------------------|-----------|
| Logistic Regression | ~85%      |
| Random Forest       | ~85–88%   |
| XGBoost             | ~85–88%   |

> Exact values depend on the dataset version used.

---

## 🛠️ Technologies Used

- **Python 3.x**
- **Pandas** — data manipulation
- **NumPy** — numerical operations
- **Matplotlib / Seaborn** — data visualization
- **Scikit-learn** — ML models and evaluation
- **XGBoost** — gradient boosting