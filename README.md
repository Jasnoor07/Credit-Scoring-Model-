# Credit Scoring Model

## Project Overview

This project develops a machine learning model to predict whether a credit applicant is likely to have Good or Bad credit risk.

The project uses the UCI German Credit dataset and compares Logistic Regression, Decision Tree, and Random Forest classification algorithms.

The models are evaluated using Accuracy, Precision, Recall, F1 Score, and ROC-AUC. Feature engineering, hyperparameter tuning, feature importance analysis, and decision-threshold optimization are also performed.

## Project Workflow

1. Load and inspect the German Credit dataset.
2. Explore the data and understand credit-risk distribution.
3. Clean and prepare the features.
4. Create the `credit_per_month` feature.
5. Encode categorical features and scale numerical features.
6. Split the data into training and testing sets.
7. Train Logistic Regression, Decision Tree, and Random Forest models.
8. Compare model performance using Accuracy, Precision, Recall, F1 Score, and ROC-AUC.
9. Tune Random Forest hyperparameters using cross-validation.
10. Analyze important features.
11. Tune the Logistic Regression decision threshold.
12. Save the final model and threshold.
13. Test the final model on a sample customer.

## Final Model Performance

The final Logistic Regression model uses a decision threshold of 0.40.

| Metric | Score |
|---|---:|
| Accuracy | 79.0% |
| Precision | 63.2% |
| Recall | 71.7% |
| F1 Score | 67.2% |
| ROC-AUC | 80.6% |

The threshold was changed from 0.50 to 0.40 after testing several thresholds. This improved recall from 55.0% to 71.7% and F1 Score from 60.6% to 67.2%.

## Dataset

The project uses the UCI Statlog (German Credit) dataset.

- 1,000 records
- 20 original input features
- Categorical and numerical attributes
- Target: Good Credit / Bad Credit

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
- ucimlrepo

## Models Compared

- Logistic Regression
- Decision Tree
- Random Forest

Logistic Regression was selected as the final model because it provided the strongest overall balance of recall, F1 Score, and ROC-AUC for this project.

## Feature Engineering

A new feature, `credit_per_month`, was created:

`credit_per_month = credit_amount / duration_months`

Categorical variables were one-hot encoded and numerical variables were standardized before model training.

## Limitations and Ethical Considerations

This project is developed for educational purposes using the UCI German Credit dataset.

The dataset contains only 1,000 records, so the model may not generalize to real-world credit applications.

The decision threshold was adjusted from 0.50 to 0.40 to improve recall for potentially bad-credit cases. This increases the number of cases identified as risky, but also increases false positives.

The threshold experiment was performed on the evaluation split, so a production-level system should select the threshold using a separate validation set and evaluate the final model once on an untouched test set.

Some input attributes may raise fairness and privacy concerns in real-world lending systems. Additional fairness testing, bias analysis, privacy safeguards, and domain-specific validation would be required before actual use.

This model should not be used as an automated real-world credit approval system.
