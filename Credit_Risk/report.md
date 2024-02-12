## Introduction


The purpose of this analysis was to predict if providing a loan would be healthy or high-risk. This was done by using the size of the loan, the interest rate, the income of the borrower, the ratio of their debt to their income, the number of accounts the borrower has, the number of derogatory marks against the borrower, and their total debt. We had 77536 loans to use in the analysis. The first stage of the machine learning process was to preprocess the data. This was done by first obtaining the X and y, which was the data on the borrowers and whether the loan was deemed healthy or high risk respectively. I then split the data into training data and testing data. Model 1 was a linear regression model, while model 2 was also a linear regression model but with 'RandomOverSampler' applied to the training data


## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Accuracy: 96.80
  * Precision: 1 for loan_status 0, .84 for loan_status 1
  * Recall scores: .99 for loan_status 0, .94 for loan_status 1



* Machine Learning Model 2:
  * Accuracy: 99.36
  * Precision: 1 for loan_status 0, .84 for loan_status 1
  * Recall scores: .99 for loan_status 0, .99 for loan_status 1

## Summary

Initially we fit a Logistic Regression model on the training data and used that model to predict the loan status of the borrowers in the testing data. This model balanced accuracy score was 96.80. This was likely lowered due to the fact that it did not perform as well on the high-risk portion of the loan data as we had very few examples in the training set of these. Precision, recall, and f1-score were near perfect for the healthy loans but significantly lower for the high-risk. The biggest issue here is the recall of .94. This means 6 percent of true high risk loans were missed, which could be catastrophic and lose lenders large amounts of money. Because of this we need to improve the model by providing more high risk loan data. The way we did that is by using a 'RandomOverSampler' model on the dataset to increase the number of high risk loans in the training set. Once this was added and our model fitted on the new training set, the recall increased to .99. The precision didn't change, so our f1-score increased slightly. This can be ignored because we know the sole cause of that was the increase in recall. I would recommend model 2 as it missed only 1 percent of high risk loans, whereas model 1 missed 6 percent. The recall score is the most important score in this case so the model with the better recall score is the best choice. Correctly predicting a high risk loan (true positive) is far more important than correctly predicting healthy (predicting healthy as high risk). You'd rather deny healthy loans than accidentally accept high-risk loans.

