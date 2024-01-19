# Module 12 Report

## Overview of the Analysis

The purpose of the analysis is to find a better model to more accurately predict healthy and unhealthy loans. It is very important to have a high accuracy when prediting health loans to minimize the lost of profit. 

We need to predict both the `0` (healthy loan) and `1` (high-risk loan) labels. The financial information we have includes loan_size, interest_rate, borrower_income, debt_to_income,num_of_accounts, derogatory_marks, total_debt, loan_status.

In order to predict both labels, we first created a LogisticRegression model with original data. First we loaded raw data into a dataframe. Then we seperated the labels and features. Third, we splited the data into training and testing datasets. Lastly, we fitted training data to create the model.
Acording to the balanced accuracy score, our model can predict at accuracy of 95%. 
Looking at the classification report:
```
              precision    recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.85      0.91      0.88       619

    accuracy                           0.99     19384
   macro avg       0.92      0.95      0.94     19384
weighted avg       0.99      0.99      0.99     19384
```
It shows that the model is very good at predicting `0` (healthy loan) at 100% precision and 99% recall. While it only predicted `1` (high-risk loan) at 85% precision and 91% recall.

Looking at the value_counts, the majority of data are healthy loans (0), while only 3.3% percent of data are non-healthy loans (1).
```
y.value_counts()
loan_status
0    75036
1     2500
```
In order to more balanced dataset to imporve prediction accuracy, we used RandomOverSampler. Our resampled value_counts are:

```
y_res.value_counts()
loan_status
0    56271
1    56271
```
The we created another LogisticRegression model with random over sampled data. The second model's balanced accuracy score is 99% which is a 4% improvment. Next we look at the classification report:
```
              precision    recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.84      0.99      0.91       619

    accuracy                           0.99     19384
   macro avg       0.92      0.99      0.95     19384
weighted avg       0.99      0.99      0.99     19384
```
It predicts the `0` (healthy loan) label very well at 100% precision and 99% recall, while `1` (high-risk loan) labels predction are at 84% precision and 99% recall.

Model 2 with random oversampled data is overall better than model 1.


## Results

* Machine Learning Model 1: LogisticRegression with original data. 
  * Original data is sampled once. 
  * Model 1 Accuracy is 95%. `0` (healthy loan) labellabels predction are 100% precision and 99% recall, while `1` (high-risk loan) labels predction are at 85% precision and 91% recall.


* Machine Learning Model 2: LogisticRegression with Random over-sampling to balance the data set. 
  * Some data is randomly sampled more than once to balance the number of samples between dataset. 
  * Model 2 Accuracy is 99%.  `0` (healthy loan) labels predction are 100% precision and 99% recall, while `1` (high-risk loan) labels predction are at 84% precision and 99% recall.

## Summary
From a lose prevention perspective, it is more important to catch all high-risk loan. 
The Logistic Regression model with RandomOverSampler has more balanced data and performed better overall. This model generated a higher accuracy score and a higher recall, meaning it will catch more high-risk loan. I would recommend using this model.
