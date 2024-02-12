# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

The purpose of this analysis was to predict if providing a loan would be healthy or high-risk. This was done by using the size of the loan, the interest rate, the income of the borrower, the ratio of their debt to their income, the number of accounts the borrower has, the number of derogatory marks against the borrower, and their total debt. We had 77536 loans to use in the analysis. The first stage of the machine learning process was to preprocess the data. This was done by first obtaining the X and y, which was the data on the borrowers and whether the loan was deemed healthy or high risk respectively. I then split the data into training data and testing data. Initially we fit a Logistic Regression model on the training data and used that model to predict the loan status of the borrowers in the testing data. This model balanced accuracy score was 96.80. This was likely lowered due to the fact that it did not perform as well on the high-risk portion of the loan data as we had very few examples in the training set of these. Precision, recall, and f1-score were near perfect for the healthy loans but significantly lower for the high-risk. The biggest issue here is the recall of .91. This means 9 percent of true high risk loans were missed, which could be catastrophic and lose lenders large amounts of money. Because of this we need to improve the model by providing more high risk loan data. The way we did that is by using a 'RandomOverSampler' model on the dataset to increase the number of high risk loans in the training set. Once this was added and our model fitted on the new training set, the recall increased to .99. The precision didn't change, so our f1-score increased slightly. This can be ignored because we know the sole cause of that was the increase in recall.

note: recall was higher for second model. this is important bc correctly predicting a high risk loan (true positive) is far more important than correctly predicting healthy (predicting healthy as high risk) Youd rather deny healthy loans than accidentally accept high-risk

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
