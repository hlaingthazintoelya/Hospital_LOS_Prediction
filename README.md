# 🏥 Hospital Length of Stay Prediction

A machine learning project to predict how long a patient will stay 
in hospital after surgery, using clinical and perioperative data.

---

## 📋 Project Overview

Accurate prediction of hospital length of stay (LOS) helps hospitals 
manage beds, allocate staff, and improve patient care planning. 
This project builds and evaluates four regression models on a dataset 
of 10,000 surgical patients.

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `hospital_los_prediction.py` | Full ML pipeline — EDA, preprocessing, training, evaluation |
| `Hospital_LOS_Report.docx` | Written report covering all analysis steps and conclusions |
| `HospitalLengthofStay_SelectedFeatures_ESC113_10k.csv` | Dataset (10,000 patients, 51 features) |
| `fig1_eda.png` | EDA plots — distribution, missing values, correlations |
| `fig2_model_eval.png` | Model comparison, actual vs predicted, residuals |
| `fig3_feature_importance.png` | Top 20 feature importances |

---

## 🔬 Dataset

- **10,000** surgical patient records
- **51 features** spanning pre-operative, intra-operative, and demographic data
- **Target variable:** `hospital_los` (length of stay in minutes, converted to days)

Key features include age, ASA score, operating room duration, 
blood pressure variability, lab results (albumin, haemoglobin), 
and diagnosis groups.

---

## ⚙️ Methodology

### 1. Exploratory Data Analysis
- Summary statistics and data types
- Missing value analysis per feature
- Correlation heatmap of top predictors

### 2. Preprocessing
- Converted LOS from minutes to days
- Removed outliers above the 99th percentile (~58 days)
- Dropped 4 columns with >70% missing values
- Median imputation for remaining missing values
- Standard scaling for linear models

### 3. Models Trained
- Linear Regression
- Ridge Regression (L2 regularisation)
- Random Forest (200 trees)
- Gradient Boosting (200 estimators)

---

## 📊 Results

| Model | R² | MAE (days) | RMSE (days) |
|---|---|---|---|
| **Ridge Regression** ✅ | **0.515** | **2.87** | **4.94** |
| Linear Regression | 0.515 | 2.88 | 4.94 |
| Gradient Boosting | 0.495 | 2.84 | 5.04 |
| Random Forest | 0.493 | 2.80 | 5.04 |

**Best model: Ridge Regression** — explains 51.5% of variance in LOS 
with a mean error of ~2.87 days.

---

## 🔑 Key Findings

- **OR duration** (surgery length) is the strongest predictor of LOS
- **Age** and **ASA score** are the top patient-level predictors
- Intra-operative **blood pressure variability** significantly impacts recovery
- Cancer and musculoskeletal diagnoses are associated with longer stays

---

## 📈 Visualisations

### EDA
![EDA](fig1_eda.png)

### Model Evaluation
![Model Evaluation](fig2_model_eval.png)

### Feature Importance
![Feature Importance](fig3_feature_importance.png)

---

## 🛠️ How to Run

1. Clone the repository:
```bash
   git clone https://github.com/hlaingthazintoelya/Hospital_LOS_Prediction.git
```

2. Install dependencies:
```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
```

3. Run the pipeline:
```bash
   python hospital_los_prediction.py
```

---

## 📦 Requirements

- Python 3.8+
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

---

*Project by Hlaing Thazin Toe — Hospital LOS Prediction using Machine Learning*
