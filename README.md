# Alzheimer's Disease Diagnosis via Machine Learning Models

This project presents a comprehensive exploration of constructing machine learning classifiers to predict (diagnose) Alzheimer’s Disease using clinical and demographic features. The goal was not to create a clinical-grade diagnostic tool, but to develop and solidify a full machine learning workflow (from data cleaning and exploratory analysis to model building and interpretation) for AD diagnosis.

The analysis prioritizes predictive accuracy alongside a thorough understanding of data characteristics, statistical validity of features, and clinical plausibility of the results.

## Project Context: A Note on the Data

The dataset used is a [synthetic collection from Kaggle](https://www.kaggle.com/datasets/rabieelkharoua/alzheimers-disease-dataset). While not real-world patient data, its clean, pre-processed nature provided an environment to focus purely on the analytical and modeling workflow without the extensive overhead of raw data cleaning.

A key part of this analysis involved critically evaluating this synthetic data against real-world clinical intuition.

## Analytical Workflow

The project is broken down into two main phases, detailed in Jupyter notebooks:

1. notebooks/data_exploration.ipynb:
  * Data Integrity Check: Validation of all features against their expected ranges and values, and deduplication.
  * Exploratory Data Analysis (EDA): In-depth visual analysis of feature distributions and their relationships with the diagnosis.
  * Statistical Hypothesis Testing: Rigorous validation of visual findings using Chi-Square and Mann-Whitney U tests to identify statistically significant predictors.
  * Correlation Analysis: Examination of multicollinearity among features using Spearman correlation.
2. notebooks/models.ipynb:
  * Preprocessing: Outlier detection, feature selection, one-hot encoding for nominal features, and feature scaling.
  * Modeling: Training and evaluation of seven different classification models (from Logistic Regression to XGBoost).
  * Feature Set Comparison: A direct comparison of model performance when trained on all features versus a smaller, statistically-validated subset of features.
  * Final Evaluation: In-depth analysis of the top-performing models using classification reports, confusion matrices, and feature importance plots.

Key Findings & Insights

* Model Performance: Random Forest and XGBoost classifiers were the top performers, achieving approximately 96-97% accuracy and F1-scores on the test set.
* Most Predictive Features: The analysis consistently highlighted cognitive and functional metrics as the most powerful predictors. Specifically:
  * FunctionalAssessment
  * ADL (Activities of Daily Living)
  * MMSE (Mini-Mental State Examination)
  * MemoryComplaints & BehavioralProblems
* Clinical Disconnect of Synthetic Data: A crucial finding was the divergence of this dataset from clinical reality. Key risk factors like Age and FamilyHistoryAlzheimers showed no statistical relationship with the diagnosis (p > 0.1). This underscores the importance of domain expertise when interpreting results from any dataset, especially synthetic ones.
* Feature Selection Impact: Models trained on a smaller subset of statistically significant features consistently performed on par with or marginally better than models trained on the full feature set, demonstrating the value of rigorous feature selection.

## How to Run

1. Clone the repository.
2. Set up a virtual environment (recommended).
3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```
4. Launch Jupyter environemnt and navigate to the notebooks/ directory to explore the analysis.