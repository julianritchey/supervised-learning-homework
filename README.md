# supervised-learning-homework
Module 12 Challenge: Credit Risk Classification

## Overview of the Analysis

The purpose of this analysis is to determine the ability of a machine learning model to identify the creditworthiness of borrowers.

Two models were developed for this analysis. The first model utilized only a logistic regression model; the second model utilized a random oversampler model, followed by a logistic regression model. As the goal of both models is to predict loans that may be considered high-risk, both models were trained and tested on a dataset of historical lending activity from a peer-to-peer lending services company. The target of the dataset was the loan status ('loan_status'); the features of the dataset included
- loan size ('loan_size'),
- interest rate ('interest_rate'),
- borrower income ('borrower_income'),
- debt-to-income ratio ('debt_to_income'),
- number of accounts ('num_of_accounts'),
- derogatory marks ('derogatory_marks'), and
- total debt ('total_debt').

In the original dataset, the value counts for 'loan_status' were
- 75036 healthy loans ('0'), and
- 2500 high-risk loans ('1').

The result of the above value counts is a heavily imbalanced dataset.

Prior to the development of either machine learning model, the dataset was split into groups of training (75%) and testing (25%) data for both the target and the features.

For the first model, the training groups were first fit to a logistic regression model. The features testing group was then used to predict an outcome for the target. Finally, the target testing group was used to determine the accuracy of the predicted target outcome. (See the [*Results*](https://github.com/julianritchey/supervised-learning-homework#results) section of this analysis)

For the second model, the training groups were first resampled using a random oversampler model. The resampled training dataset resulted in the following value counts:
- 56277 healthy loans ('0'), and
- 56277 high-risk loans ('1').

With the value counts balanced, a logistic regression model was then applied to the resampled dataset in the same manner as the first model.

## Results

* Machine Learning Model 1:
  * Balanced accuracy score: **0.9442676901753825**
  * Precision of healthy loans ('0'): **1.00**
  * Precision of high-risk loans ('1'): **0.87**
  * Recall of healthy loans ('0'): **1.00**
  * Recall of high-risk loans ('1'): **0.89**

* Machine Learning Model 2:
  * Balanced accuracy score: **0.9959744975744975**
  * Precision of healthy loans ('0'): **1.00**
  * Precision of high-risk loans ('1'): **0.87**
  * Recall of healthy loans ('0'): **1.00**
  * Recall of high-risk loans ('1'): **1.00**

## Summary

Based on the above model results, the second machine learning model, with its resampled (balanced) dataset, appears to perform better than the first machine learning model. The second model has a balanced accuracy score of 0.99; the first model, 0.94. While both models show perfect precision and perfect recall in the prediction of healthy loans, the second model shows perfect recall in the prediction of high-risk loans; an improvement over the 0.89 of the first model.

Incorrectly predicting a high-risk loan (i.e. false negative) could have devastating effects on a loan company. As such, a predictive model with high recall (low number of false negatives) in predicting high-risk loans ('1') is of the utmost importance. The second machine learning model shows perfect recall in predicting high-risk loans. While the model may only have a precision of 0.87 in predicting high-risk loans, incorrectly predicting a healthy loan (i.e. false positive), in this particular case, is of much less significance. I, therefore, recommend using the second model, with its resampled (balanced) dataset, for predicting high-risk loans.

## Other Information
- All work can be found in the [credit_risk_resampling.ipynb](https://github.com/julianritchey/supervised-learning-homework/blob/main/credit_risk_resampling.ipynb) file.
- All data used in this assignment can be found in the [Resources](https://github.com/julianritchey/supervised-learning-homework/tree/main/Resources) folder.
- Answers to the assignment questions may be found after code blocks 12 and 18 in the [credit_risk_resampling.ipynb](https://github.com/julianritchey/supervised-learning-homework/blob/main/credit_risk_resampling.ipynb) file.