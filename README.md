# Heart Disease Prediction with Machine Learning

This project applies machine learning techniques to predict heart disease using the Cleveland Heart Disease dataset.

## Overview

The notebook demonstrates a full machine learning workflow:

- exploratory data analysis
- data preparation
- Logistic Regression
- Random Forest
- model evaluation
- feature importance
- ROC analysis

## Dataset

The dataset contains patient-level clinical variables used to predict the presence of heart disease.

Target variable:

- `0` = No heart disease
- `1` = Heart disease present

## Models Used

- Logistic Regression
- Random Forest Classifier

## Results

- Logistic Regression Accuracy: **0.885**
- Random Forest Accuracy: **0.869**
- Random Forest ROC AUC: **0.93**

## Exploratory Data Analysis

### Heart Disease Distribution
![Heart Disease Distribution](images/heart_disease_distribution.png)

### Age Distribution
![Age Distribution](images/age_distribution.png)

### Heart Disease vs Age
![Heart Disease vs Age](images/heart_disease_vs_age.png)

### Correlation Matrix
![Correlation Matrix](images/correlation_matrix.png)

## Model Evaluation

### Confusion Matrix
![Confusion Matrix](images/confusion_matrix.png)

### Random Forest Feature Importance
![Feature Importance](images/feature_importance.png)

### ROC Curve
![ROC Curve](images/roc_curve.png)

### Model Accuracy Comparison
![Model Accuracy Comparison](images/model_accuracy_comparison.png)

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Structure

```text
heart-disease-ml-prediction/
├── data/
├── images/
├── notebook/
├── requirements.txt
└── README.md
```
