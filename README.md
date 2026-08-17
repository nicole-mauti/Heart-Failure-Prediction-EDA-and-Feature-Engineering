#  Heart Disease Prediction — Data Preprocessing

##  Project Overview

This project focuses on preparing the **Heart Disease Prediction Dataset** for machine learning as part of **Week 2 of the Data Science Internship at AnalystLab Africa Consulting**.

The project transforms raw clinical data into a **reliable, machine-learning-ready dataset** through systematic **data inspection, cleaning, visualization, feature engineering, categorical encoding, scaling, outlier assessment, and feature selection**.

---

##  Project Objective

The objective is to prepare the dataset for a future **supervised classification model** capable of predicting whether a patient has heart disease based on their clinical characteristics.

---

##  Dataset

The dataset contains **918 patient records** and **12 original variables**.

### Target Variable

| Variable | Description |
|---|---|
| `HeartDisease` | **0 = No Heart Disease**, **1 = Heart Disease** |

### Key Features

| Feature | Description |
|---|---|
| `Age` | Patient age |
| `Sex` | Patient sex |
| `ChestPainType` | Type of chest pain experienced |
| `RestingBP` | Resting blood pressure |
| `Cholesterol` | Serum cholesterol level |
| `FastingBS` | Fasting blood sugar indicator |
| `RestingECG` | Resting electrocardiogram result |
| `MaxHR` | Maximum heart rate achieved |
| `ExerciseAngina` | Exercise-induced angina |
| `Oldpeak` | ST-segment depression during exercise |
| `ST_Slope` | Slope of the peak ST segment during exercise |

---

##  Data Preprocessing

The following preprocessing steps were performed:

- **Data Inspection** — examined structure, data types, missing values, duplicates, and summary statistics.
- **Invalid Value Treatment** — identified clinically invalid zero values in `RestingBP` and `Cholesterol`.
- **Missing Value Handling** — replaced invalid zeros with `NaN` and applied **median imputation**.
- **Data Type Validation** — confirmed appropriate numerical and categorical data types.
- **Categorical Encoding** — applied binary encoding and **One-Hot Encoding** where appropriate.
- **Feature Scaling** — standardized continuous numerical variables using **StandardScaler**.
- **Outlier Assessment** — used boxplots and the **IQR method** to identify extreme observations.
- **Feature Selection** — assessed correlations, multicollinearity, and Random Forest feature importance.
- **Data Preservation** — retained clinically plausible extreme observations rather than automatically removing them.

---

##  Exploratory Analysis & Visualizations

Visualizations were used to understand the distribution and relationships within the dataset.

The analysis included:

- **Target Variable Distribution**
- **Categorical Feature Distributions**
- **Categorical Features vs Heart Disease**
- **Numerical Feature Distributions**
- **Boxplots for Outlier Assessment**
- **Correlation Heatmap**
- **Oldpeak vs Heart Disease**
- **MaxHR vs Heart Disease**
- **Random Forest Feature Importance**

###  Key Findings

Several features showed notable relationships with the target variable:

- **`ST_Slope`**
- **`ExerciseAngina`**
- **`Oldpeak`**
- **`MaxHR`**
- **`ChestPainType`**

A preliminary **Random Forest feature-importance analysis** also ranked `ST_Slope_Up`, `ST_Slope_Flat`, `MaxHR`, `Oldpeak`, and `Cholesterol` among the more influential predictors.

> **Note:** The Random Forest was used as a preliminary feature-importance tool and not as the final predictive model.

---

##  Feature Engineering & Selection

No original predictor variables were removed because all features were considered potentially useful for prediction.

Categorical variables were encoded according to their nature:

- **Binary variables** → 0/1 encoding
- **Nominal categorical variables** → One-Hot Encoding
- **Continuous numerical variables** → StandardScaler

Correlation analysis showed no problematic multicollinearity requiring removal of independent clinical predictors.

---

## Final Machine-Learning-Ready Dataset

The final processed dataset contains:

| Property | Result |
|---|---:|
| **Records** | 918 |
| **Total Columns** | 16 |
| **Predictors** | 15 |
| **Target** | 1 |
| **Missing Values** | 0 |
| **Duplicate Records** | 0 |
| **Categorical Variables** | Encoded |
| **Numerical Variables** | Standardized |

The resulting dataset provides a suitable foundation for the **next stage of machine learning model development and evaluation**.

---

##  Repository Structure

```text
heart-disease-prediction/
│
├── README.md
├── .gitignore
│
├── notebooks/
│   └── heart_disease_preprocessing.ipynb
│
├── data/
│   ├── heart_disease_cleaned.csv
│   └── heart_disease_ml_ready.csv
│
```
## Tools & Technologies
Python
Jupyter Notebook
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn

 ## Project Status

Week 2 — Feature Engineering & Data Preprocessing: COMPLETED ✅

The dataset has been inspected, cleaned, transformed, encoded, scaled, and assessed for feature relevance, providing a machine-learning-ready foundation for the subsequent model development and evaluation stage.
