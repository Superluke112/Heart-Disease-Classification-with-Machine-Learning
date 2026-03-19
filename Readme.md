# Heart Disease Classification with Machine Learning

A machine learning project comparing Logistic Regression, Random Forest, and Support Vector Machine (SVM) for heart disease classification using preprocessing, hyperparameter tuning, and performance evaluation.

## Overview

This project investigates the application of machine learning methods to heart disease classification using a clinical dataset. Three supervised learning models were implemented and compared:

- Logistic Regression
- Random Forest
- Support Vector Machine (SVM)

The project follows a full machine learning workflow, including data inspection, preprocessing, train/test splitting, cross-validation, hyperparameter tuning, and final evaluation on a held-out test set.

Because this is a medical classification task, **recall** was treated as an especially important metric during model selection, since failing to identify a positive case may be more serious than producing additional false positives. However, the final model decision was based on a broader evaluation of **accuracy, precision, recall, and F1-score** together.

## Objectives

The main objectives of this project were to:

- build classification models for heart disease prediction
- compare the performance of multiple machine learning approaches
- investigate the trade-off between recall and overall model balance
- select a final model based on evidence from unseen test data

## Workflow

### 1. Data Inspection and Preprocessing

The dataset was first inspected to understand its structure, check for missing values, and identify duplicate records. Duplicate rows were removed before model training.

### 2. Train/Test Split

The dataset was split into training and test sets using stratified sampling so that the class distribution was preserved. The test set was held back until the final evaluation stage.

### 3. Cross-Validation

Stratified 5-fold cross-validation was applied to the training set to provide a more reliable comparison between models.

### 4. Model Training

Three machine learning classifiers were trained and evaluated:

- Logistic Regression
- Random Forest
- Support Vector Machine (SVM)

### 5. Hyperparameter Tuning

`GridSearchCV` was used to tune model hyperparameters. At the tuning stage, recall was given particular attention because of the clinical context.

### 6. Final Evaluation

After tuning, all candidate models were evaluated on the held-out test set using:

- Accuracy
- Precision
- Recall
- F1-score

A confusion matrix and comparative metric plots were also used to support interpretation.

## Key Findings

During hyperparameter tuning, **SVM achieved the strongest recall**, making it the initial candidate for a recall-focused medical classification task.

However, evaluation on the held-out test set showed that although SVM maintained strong recall, its **precision and F1-score were weaker** than the alternatives. After comparing all tuned models, **Random Forest** was selected as the final model because it provided the best overall balance across the evaluation metrics while still maintaining high recall.

## Technologies Used

- Python
- pandas
- matplotlib
- scikit-learn
- Jupyter Notebook

## Repository Structure

```text
.
├── heart_disease_classification.ipynb
├── heart_disease_data.csv
└── README.md

```

You can adjust the filenames above to match the actual files in your repository.

## How to Run

- Clone this repository.

- Make sure the dataset file is placed in the correct directory.

- Open the notebook in Jupyter Notebook or JupyterLab.

- Run the cells in order from top to bottom.

## References

- McKinney, W. pandas documentation. Used for data loading, inspection, and preprocessing.

- Pedregosa, F. et al. (2011). Scikit-learn: Machine Learning in Python. Journal of Machine Learning Research, 12, 2825–2830.

- Hunter, J. D. (2007). Matplotlib: A 2D Graphics Environment. Computing in Science & Engineering, 9(3), 90–95.

## Future Improvements

Possible extensions of this project include:

- testing additional models such as XGBoost or LightGBM

- exploring feature importance in more detail

- evaluating class imbalance handling methods

- including ROC-AUC and PR-AUC for further analysis

- improving interpretability for healthcare-related decision support

## Author

Luke
