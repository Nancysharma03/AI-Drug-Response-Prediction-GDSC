# AI-Assisted Drug Response Prediction Using GDSC

A machine learning project for predicting cancer drug sensitivity and resistance and estimating drug response values using the Genomics of Drug Sensitivity in Cancer (GDSC) dataset.

The project compares multiple machine learning and neural network models for pharmacogenomic analysis, with a focus on drug response prediction, model evaluation, feature importance, and explainable AI.

## Overview

Drug response prediction is an important research area in precision medicine. Understanding how cancer cell lines respond to different therapeutic compounds can help researchers investigate drug sensitivity, resistance, and potential biomarkers associated with therapeutic outcomes.

This project uses pharmacogenomic data from GDSC to develop predictive models for two tasks:

- **Classification:** Predict whether a drug response is Sensitive or Resistant.
- **Regression:** Predict the continuous drug response measurement, LN_IC50.

The project also explores explainable AI methods to understand which features influence model predictions.

## Objectives

- Analyze pharmacogenomic data for cancer drug response prediction.
- Build and compare multiple machine learning and neural network models.
- Classify drug responses into Sensitive and Resistant categories.
- Predict continuous LN_IC50 values using regression.
- Evaluate models using classification and regression metrics.
- Identify influential features through feature importance, SHAP, and LIME analyses.
- Explore the potential application of AI-assisted predictions in future organ-on-a-chip drug screening research.

## Dataset

**Dataset:** Genomics of Drug Sensitivity in Cancer (GDSC)

**Source:** Kaggle

**Dataset link:** [https://www.kaggle.com/datasets/samiraalipour/genomics-of-drug-sensitivity-in-cancer-gdsc](https://www.kaggle.com/datasets/samiraalipour/genomics-of-drug-sensitivity-in-cancer-gdsc)

GDSC is a pharmacogenomic resource containing information about cancer cell lines, therapeutic compounds, molecular characteristics, and drug sensitivity measurements.

The notebook downloads the dataset using `kagglehub`.

### Important Features

The implementation uses available pharmacogenomic variables, including:

- Drug identifiers and names
- Cancer cell-line information
- Tissue and cancer-type characteristics
- Drug targets and target pathways
- Growth properties
- Genomic and biomarker-related features
- LN_IC50 drug response measurements

### Target Variables

**1. Drug sensitivity classification**

The notebook converts LN_IC50 values into binary classes using a median-based threshold:

- `0` — Resistant
- `1` — Sensitive

**2. LN_IC50 regression**

The regression models predict the continuous LN_IC50 value.

Lower LN_IC50 values generally indicate greater drug sensitivity, while higher values generally indicate lower sensitivity.

## Methodology

### 1. Dataset Acquisition and Inspection

- Download the GDSC dataset using KaggleHub.
- Inspect available files, dataset structure, column types, and missing values.

### 2. Data Preprocessing

- Handle missing values and remove duplicate or non-informative records where applicable.
- Prepare input features and prediction targets.
- Encode categorical variables.
- Scale features for model training.
- Split the data into training and testing subsets using an 80:20 ratio.

### 3. Classification Models

The notebook implements four models:

- Random Forest Classifier
- XGBoost Classifier
- Support Vector Machine (SVM)
- Artificial Neural Network (ANN)

The models are evaluated using accuracy, precision, recall, F1-score, and ROC-AUC.

### 4. Regression Models

The regression task predicts LN_IC50 values using:

- Random Forest Regressor
- XGBoost Regressor

Evaluation metrics include Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and the coefficient of determination (R²).

### 5. Explainable AI

The notebook includes analyses to improve model interpretability:

- XGBoost feature importance
- SHAP summary plots
- LIME local explanations

These methods help explore the contribution of drug-related, cell-line-related, pathway, and other input features to the model's predictions.

### 6. Organ-on-a-Chip Research Context

The associated research manuscript discusses a conceptual framework connecting computational drug response prediction with future organ-on-a-chip drug screening.

The current notebook implements computational prediction using GDSC data. It does not itself perform physical organ-on-a-chip experiments or experimental biological validation.

## Results

The following values are taken from the recorded outputs in the Jupyter notebook.

### Classification Performance

| Model         | Accuracy | Precision | Recall | F1-score | ROC-AUC |
| ------------- | -------: | --------: | -----: | -------: | ------: |
| Random Forest |   82.82% |    82.51% | 83.29% |   82.90% |  91.26% |
| XGBoost       |   85.29% |    85.04% | 85.64% |   85.34% |  93.70% |
| SVM           |   62.36% |    64.40% | 55.29% |   59.50% |  66.75% |
| ANN           |   78.07% |    77.51% | 79.09% |   78.29% |  87.02% |

XGBoost achieved the highest recorded classification accuracy, F1-score, and ROC-AUC among the four evaluated models.

### Regression Performance

| Model                   |    MAE |   RMSE |     R² |
| ----------------------- | -----: | -----: | -----: |
| Random Forest Regressor | 0.9590 | 1.2813 | 0.7848 |
| XGBoost Regressor       | 0.8099 | 1.0842 | 0.8459 |

The XGBoost Regressor achieved a higher R² and lower prediction errors than the Random Forest Regressor in the recorded evaluation.

These results reflect the notebook's reported experiment and should not be interpreted as evidence of clinical effectiveness.

## Visualizations and Analysis

The notebook includes visual analyses such as:

- Dataset and target distribution
- Confusion matrices
- ROC curve comparisons
- Model performance comparisons
- Actual versus predicted LN_IC50 values
- Regression residual analysis
- XGBoost feature importance
- SHAP summary plots
- LIME local explanations

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- TensorFlow / Keras
- SHAP
- LIME
- KaggleHub
- Google Colab / Jupyter Notebook

## Repository Structure

```text
AI-Drug-Response-Prediction-GDSC/
├── AI_Drug_Response_Prediction.ipynb
├── README.md
└── .gitignore
```

## How to Run

1. Open the notebook in Google Colab.
2. Ensure the Kaggle dataset can be downloaded using KaggleHub.
3. Install any missing dependencies required by the notebook.
4. Run the cells in sequence, beginning with dataset acquisition and preprocessing.
5. Execute the classification and regression sections.
6. Review the evaluation metrics and visualization outputs.

Some model training and explainability cells may require substantial memory or processing time, depending on the environment.

## Future Improvements

- Build an interactive drug response prediction dashboard.
- Save trained classification and regression models.
- Save preprocessing and encoding artifacts for consistent inference.
- Develop a deployment-ready prediction pipeline.
- Improve model interpretability and validation on independent datasets.
- Explore integration with experimental organ-on-a-chip data in future research.

## Disclaimer

This project is intended for educational and research purposes. Predictions from the models are computational estimates and are not clinical recommendations for selecting cancer treatments.

## Author

**Nancy Sharma**

B.Tech. Computer Science and Engineering — Artificial Intelligence and Machine Learning

LNCT University, Bhopal
