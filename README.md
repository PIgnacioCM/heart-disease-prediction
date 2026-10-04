# Heart Disease Prediction

A machine learning project that predicts the likelihood of heart disease using the UCI Heart Disease dataset.

The project includes:

- Exploratory data analysis
- Data cleaning and preprocessing
- Binary classification
- Logistic Regression
- Random Forest
- Model evaluation
- Streamlit web application

---

## Project Overview

The goal of this project is to build a machine learning model that predicts whether a patient is likely to have heart disease based on clinical features.

The original UCI target contains values from 0 to 4.

For this project, the target was converted into a binary classification problem:

- `0` = no heart disease
- `1` = heart disease present

---

## Dataset

The dataset comes from the UCI Machine Learning Repository:

**Heart Disease Dataset**

The dataset contains 303 patient records and 13 input features.

### Features

| Feature | Description |
|---|---|
| `age` | Age |
| `sex` | Sex |
| `cp` | Chest pain type |
| `trestbps` | Resting blood pressure |
| `chol` | Serum cholesterol |
| `fbs` | Fasting blood sugar > 120 mg/dL |
| `restecg` | Resting electrocardiographic results |
| `thalach` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina |
| `oldpeak` | ST depression induced by exercise |
| `slope` | Slope of the peak exercise ST segment |
| `ca` | Number of major vessels |
| `thal` | Thalassemia-related test result |

---

## Data Preprocessing

The preprocessing steps included:

- Inspecting feature distributions
- Checking for missing values
- Filling missing values in `ca` and `thal` using the mode
- Converting the target into binary classes
- Performing an 80/20 train-test split
- Using stratification to preserve the class distribution
- Standardizing features using `StandardScaler`

The class distribution was approximately:

- 54% no heart disease
- 46% heart disease

---

## Exploratory Data Analysis

Some of the patterns observed during EDA included:

- Patients with heart disease tended to be older
- Patients with heart disease tended to have a lower maximum achieved heart rate
- Exercise-induced angina was strongly associated with heart disease
- Chest pain category 4 had a much higher proportion of heart disease cases
- Several features showed moderate correlation with the target, including:
  - `thal`
  - `ca`
  - `exang`
  - `oldpeak`
  - `cp`
  - `thalach`

---

## Models

Two classification models were tested:

### Logistic Regression

Performance on the test set:

- Accuracy: **86.9%**
- Precision: **81.3%**
- Recall: **92.9%**
- F1-score: **86.7%**
- ROC-AUC: **95.1%**

### Random Forest

Performance on the test set:

- Accuracy: **88.5%**
- Precision: **81.8%**
- Recall: **96.4%**
- F1-score: **88.5%**
- ROC-AUC: **95.1%**

Random Forest was selected for the final application because it achieved slightly stronger accuracy, recall, and F1-score.

---

## Web Application

The final model is deployed through a Streamlit interface.

The application allows users to enter patient information and returns:

- A binary prediction
- The model-predicted probability of heart disease

The interface also displays the model evaluation metrics.

---

## Project Structure

```text
heart-disease-prediction/
│
├── app.py
├── heart_disease_analysis.ipynb
├── random_forest_model.pkl
├── scaler.pkl
├── requirements.txt
├── README.md
└── .venv/