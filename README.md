# Heart Disease Data Analysis and Prediction

**Author:** Anushka  
**Academic Level:** Undergraduate / College Data Analytics Project  

> ⚠️ **Academic Disclaimer:** This project is submitted as a college data-analytics assignment.  
> The machine-learning models here are **NOT** medical diagnostic tools and should **NOT** be used for clinical decision-making of any kind.

---

## Project Overview

This project performs a complete data analytics and machine learning study on the publicly available **Heart Failure Prediction Dataset** (918 patient records, 12 features). It includes exploratory data analysis (EDA), data visualizations, data cleaning, feature engineering, and classification model training and evaluation.

All results, statistics, and findings in this project are derived from the actual dataset — no data has been invented or fabricated.

---

## Problem Statement

Given clinical and demographic attributes of a patient, identify patterns associated with the presence of heart disease and evaluate the predictive capability of standard classification algorithms.

- **Target Variable:** `HeartDisease` — Binary: `1` = Heart Disease present, `0` = No Heart Disease

---

## Objectives

1. Inspect and understand the structure and quality of the heart disease dataset.
2. Perform data cleaning to address invalid zero values.
3. Conduct exploratory data analysis (EDA) to uncover patterns and relationships.
4. Create meaningful visualizations to communicate findings.
5. Train and evaluate three classification models: Logistic Regression, Decision Tree, Random Forest.
6. Compare model performance using standard evaluation metrics.
7. Present all findings in a structured, reproducible academic report.

---

## Dataset Description

| Property | Value |
|---|---|
| File | `heart.csv` |
| Total Rows | 918 |
| Total Columns | 12 |
| Missing Values (NaN) | 0 |
| Duplicate Rows | 0 |
| Zero RestingBP rows | 1 (replaced with median) |
| Zero Cholesterol rows | 172 (replaced with median) |
| Target Column | `HeartDisease` (0 or 1) |
| Heart Disease (1) | 508 patients (55.3%) |
| No Heart Disease (0) | 410 patients (44.7%) |

### Columns

| Feature | Type | Description |
|---|---|---|
| Age | int | Patient age in years |
| Sex | str | M = Male, F = Female |
| ChestPainType | str | ATA / NAP / ASY / TA |
| RestingBP | int | Resting blood pressure (mm Hg) |
| Cholesterol | int | Serum cholesterol (mm/dl) |
| FastingBS | int | Fasting blood sugar > 120 mg/dl (1=Yes, 0=No) |
| RestingECG | str | Normal / ST / LVH |
| MaxHR | int | Maximum heart rate achieved |
| ExerciseAngina | str | Exercise-induced angina: Y / N |
| Oldpeak | float | ST depression (exercise vs rest) |
| ST_Slope | str | Up / Flat / Down |
| **HeartDisease** | **int** | **Target: 1 = Disease, 0 = No Disease** |

---

## Dataset Source

**Kaggle:** [https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)

Creator: **fedesoriano**  
The dataset was created by combining five publicly available heart disease datasets: Cleveland, Hungarian, Switzerland, Long Beach VA, and Stalog.

---

## Technologies Used

| Technology | Purpose |
|---|---|
| Python 3.x | Core language |
| pandas | Data loading, manipulation |
| NumPy | Numerical operations |
| Matplotlib | Visualization |
| seaborn | Statistical visualization |
| scikit-learn | ML models and metrics |
| Jupyter Notebook | Interactive notebook |
| python-docx | Word report generation |
| nbformat | Notebook file creation |

---

## Python Libraries

```
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
nbformat
python-docx
```

---

## Project Structure

```
Heart_Disease_Data_Analysis/
│
├── heart.csv                                      # Original dataset (DO NOT MODIFY)
├── Anushka_Heart_Disease_Data_Analysis.py         # Main Python analysis script
├── Anushka_Heart_Disease_Data_Analysis.ipynb      # Jupyter notebook
├── Anushka_Heart_Disease_ProjectReport.docx       # Word project report
├── README.md                                      # This file
├── requirements.txt                               # Python dependencies
├── create_notebook.py                             # Helper: generates .ipynb
├── create_report.py                               # Helper: generates .docx
│
└── outputs/                                       # Generated charts and results
    ├── 01_target_distribution.png
    ├── 02_age_distribution.png
    ├── 03_sex_distribution.png
    ├── 04_numerical_distributions.png
    ├── 05_categorical_distributions.png
    ├── 06_features_vs_target.png
    ├── 07_correlation_heatmap.png
    ├── 08_exercise_fasting_vs_target.png
    ├── 09_chestpain_vs_target.png
    ├── 10_confusion_matrices.png
    ├── 11_model_comparison.png
    ├── 12_feature_importance.png
    └── model_results.csv
```

---

## Installation

### 1. Clone / Download the project folder

Make sure `heart.csv` is present in the project root directory.

### 2. (Optional) Create a virtual environment

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## Setup Instructions

No additional setup is needed beyond installing the requirements. The script automatically creates an `outputs/` folder for charts.

---

## How to Run the Python Program

```bash
python Anushka_Heart_Disease_Data_Analysis.py
```

This will:
- Load and inspect `heart.csv`
- Perform data cleaning and EDA
- Generate and save 12 charts to `outputs/`
- Train three classification models
- Print evaluation metrics to the console
- Save `outputs/model_results.csv`

---

## How to Run the Jupyter Notebook

```bash
jupyter notebook Anushka_Heart_Disease_Data_Analysis.ipynb
```

Or with JupyterLab:

```bash
jupyter lab Anushka_Heart_Disease_Data_Analysis.ipynb
```

Run all cells from top to bottom. The notebook is self-contained and produces all charts inline.

---

## Data Analysis Performed

1. **Dataset Inspection** — Shape, columns, data types, statistics
2. **Data Quality Check** — Missing values, duplicates, invalid zeros
3. **Data Cleaning** — Replaced 1 zero RestingBP and 172 zero Cholesterol values with medians
4. **Target Analysis** — Distribution of HeartDisease (55.3% vs 44.7%)
5. **Numerical EDA** — Distributions of Age, RestingBP, Cholesterol, MaxHR, Oldpeak
6. **Categorical EDA** — Distributions of Sex, ChestPainType, RestingECG, ExerciseAngina, ST_Slope
7. **Feature vs Target Analysis** — Boxplots and crosstabs showing feature-target relationships
8. **Correlation Analysis** — Full feature correlation heatmap

---

## Machine Learning Models

| Model | Notes |
|---|---|
| **Logistic Regression** | Linear model, features scaled with StandardScaler |
| **Decision Tree** | max_depth=5, no scaling needed |
| **Random Forest** | 100 estimators, no scaling needed |

- **Split:** 80% train (734) / 20% test (184), stratified
- **Random state:** 42 (reproducible)

---

## Evaluation Metrics

- **Accuracy** — Overall correct predictions
- **Precision** — Positive predictive value
- **Recall** — Sensitivity (true positive rate)
- **F1-Score** — Harmonic mean of precision and recall
- **Confusion Matrix** — TP / TN / FP / FN breakdown

---

## Results

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---|---|---|---|
| Logistic Regression | 0.8696 | 0.8482 | 0.9314 | 0.8879 |
| Decision Tree | 0.8098 | 0.8252 | 0.8333 | 0.8293 |
| **Random Forest** | **0.8750** | **0.8762** | **0.9020** | **0.8889** |

**Best Model: Random Forest — Accuracy 87.50%, F1-Score 0.8889**

---

## Key Findings

1. Dataset is slightly imbalanced: 55.3% heart disease vs 44.7% no disease.
2. Patients with heart disease are older on average (~56 years vs ~51 years).
3. Asymptomatic (ASY) chest pain type is the most prevalent and most associated with disease.
4. Flat/Down ST_Slope is a strong indicator of heart disease.
5. Exercise-induced angina (ExerciseAngina = Y) is strongly correlated with disease.
6. Higher Oldpeak (ST depression) is associated with heart disease.
7. 172 zero-cholesterol values required imputation.
8. Top predictors (Random Forest): ST_Slope, Oldpeak, ChestPainType, MaxHR, ExerciseAngina.

---

## Limitations

1. 172 zero-cholesterol values were imputed; this may affect cholesterol-related analysis.
2. Dataset is predominantly male (~79%), limiting female generalizability.
3. No hyperparameter tuning performed (baseline models only).
4. No external validation dataset used.
5. This is an **academic project** — models are NOT clinical decision support tools.

---

## Future Scope

- Hyperparameter tuning with GridSearchCV / RandomizedSearchCV
- Advanced models: XGBoost, LightGBM, SVM, Neural Networks
- SMOTE for class imbalance handling
- k-fold cross-validation
- SHAP explainability analysis
- Streamlit interactive web application
- Recursive Feature Elimination (RFE) for feature selection

---

## Conclusion

This project successfully performed an end-to-end data analytics pipeline on the Heart Failure Prediction Dataset. Random Forest achieved the best accuracy of **87.50%** with an F1-score of **0.8889**. Key clinical predictors identified include ST_Slope, ChestPainType, ExerciseAngina, Oldpeak, and MaxHR.

This is an academic analysis project. The machine-learning models developed here are **not medical diagnostic tools** and should not be used for any clinical or healthcare decision-making.

---

## Author

**Anushka**  
Undergraduate Data Analytics Student  

---

*Project based on the Heart Failure Prediction Dataset from Kaggle (fedesoriano, 2021).*
