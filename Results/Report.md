# Module 12 Report

## Overview of the Analysis

* The purpose of the analysis is to find a better model to more accurately predict healthy and unhealthy loans. It is very important to have a high accuracy when prediting health loans to minimize the lost of profit. 

* We need to predict both the `0` (healthy loan) and `1` (high-risk loan) labels. The financial information we have includes loan_size, interest_rate, borrower_income, debt_to_income,num_of_accounts, derogatory_marks, total_debt, loan_status.

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.
```
loan_status
0    75036
1     2500
```


* Machine Learning Model 1: LogisticRegression with original data. 
  * Original data is sampled once. 
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine Learning Model 2: LogisticRegression with Random over-sampling to balance the data set. 
  * Some data is randomly sampled more than once to balance the number of samples between dataset. 
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
