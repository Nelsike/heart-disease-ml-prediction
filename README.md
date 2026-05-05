# heart-disease-ml-prediction

Supervised machine learning for heart disease prediction on the Cleveland Heart Disease dataset. End-to-end workflow from exploratory analysis through model evaluation, with feature importance and ROC analysis.

## Why this matters

Cardiovascular disease is the leading cause of death globally. Even on small, well-studied datasets, the modeling choices that surround a classifier — feature handling, model selection, threshold reasoning, evaluation metrics — drive whether a result is useful or misleading. This project demonstrates those choices on a tractable public dataset, with the modeling pipeline documented end to end.

This repo is a learning and portfolio project. It is not a clinical tool and the results should not be interpreted as medical recommendations.

## Results

Test-set performance:

| Model | Accuracy | ROC AUC |
| --- | --- | --- |
| Logistic Regression | 0.885 | — |
| Random Forest | 0.869 | 0.93 |

Logistic regression edges out random forest on accuracy. Random forest produces a strong AUROC of 0.93, indicating good probability ranking across patients. On a dataset this small, accuracy differences between the two models are within the margin a single train/test split can produce. The honest read is that both models are reasonable on this dataset and the choice between them depends on what matters more for a given use case: interpretability and calibration favor logistic regression, non-linear feature interactions favor random forest.

## Dataset

The Cleveland Heart Disease dataset, 303 patient records with 13 clinical features and a binary target.

Target variable:

- `0` = No heart disease
- `1` = Heart disease present

Features include age, sex, chest pain type, resting blood pressure, serum cholesterol, fasting blood sugar, resting ECG, maximum heart rate, exercise-induced angina, ST depression, slope of peak exercise ST segment, number of major vessels, and thalassemia type.

## Approach

Two models are trained and compared on the same train/test split:

1. **Logistic Regression.** Linear baseline. Interpretable coefficients, well-calibrated probabilities, fast to train.
2. **Random Forest Classifier.** Non-linear ensemble. Captures feature interactions and provides feature importance scores.

Both models share identical preprocessing and the same evaluation pipeline. Performance is reported on a held-out test set using accuracy, ROC AUC, confusion matrices, and feature importance for the random forest.

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

## Tech stack

- **Python 3.11**
- **scikit-learn** for models, preprocessing, and metrics
- **pandas** and **NumPy** for data handling
- **matplotlib** and **seaborn** for visualization
- **Jupyter Notebook** for the analysis workflow

## Repository structure

```text
heart-disease-ml-prediction/
├── data/                  # Cleveland dataset
├── images/                # Generated plots and figures
├── notebook/              # Jupyter notebook with full workflow
├── requirements.txt
├── LICENSE
└── README.md
```

## Reproducing results

```bash
# Clone the repo
git clone https://github.com/Nelsike/heart-disease-ml-prediction.git
cd heart-disease-ml-prediction

# Create and activate a virtual environment (Python 3.11)
python -m venv .venv
source .venv/bin/activate          # macOS/Linux
.\.venv\Scripts\Activate.ps1       # Windows PowerShell

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook notebook/
```

## Limitations

The Cleveland Heart Disease dataset is small (303 records) and well-studied, which makes it useful for demonstrating workflow but unsuitable for drawing generalizable clinical conclusions. Results characterize model behavior on this specific dataset and should not be extrapolated to other populations or clinical settings.

Single train/test split results are reported here. Cross-validation or multi-seed evaluation would produce more stable performance estimates and is a planned extension. The default classification threshold of 0.5 is used; threshold calibration for clinical decision support would require explicit cost-sensitive tuning.

## Related work

For a more rigorous treatment of cardiovascular disease prediction under privacy-preserving constraints, see [fed-dp-cardio](https://github.com/Nelsike/fed-dp-cardio), which compares centralized, federated, and differentially private federated learning on the same problem domain with multi-seed evaluation and confidence intervals.

## Author

**Joshua Sanchez**
Doctor of Computer Science (in progress), Colorado Technical University
[GitHub](https://github.com/Nelsike) · [LinkedIn](https://www.linkedin.com/in/sanchezgutierrez/)

## License

MIT. See [LICENSE](LICENSE) for details.
