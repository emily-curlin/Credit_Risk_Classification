# Credit_Risk_Classification

**Overview of the Analysis**

This analysis used a credit-risk dataset and logistic regression models to predict how likely a person who takes out a loan is to default on that loan.  The models were trained using predictors such as the size of the loan, the interest rate, the borrower's income, the borrower's debt to income ratio, the number of accounts a borrower has, the number of derogatory marks a borrower has, and the borrower's total debt with a target value of either `0` (healthy loan) or `1` (high-risk loan).

In the data set there were 75036 instances of healthy loans, and 2500 instances of high risk loans on which to base the models.

Steps in the development of the model included:

1. Generating model features and a outcome column (labels)

2. Scaling the X_train and X_test data

2. Fitting a logistic regression model once using the scaled data from previous step, and once using unscaled data (`X_train` and `y_train`).

2. Saving the predictions for the testing data labels by using the testing feature data (`X_test`) and the fitted model.

3. Evaluating the model’s performance using a confusion matric and a classificaton report.


**The results:** 

Accuracy score: how many time the model was correct overall

Precision score: how frequently the model is able to predict a specific category

Recall score: A score that considers both the accuracy and the precision score to measure how well the model is at detecting a particular outcome category, in this case being classified as a high-risk loan compared to the total number of high risk loans.

**A Summary:** 
Out of 18,719 predictions, the first model predicted the correct outcome 18,663 times when not scaled and 18,652 times out of 18,662 when it was scaled in the second model. The accuracy of the first model is 100% and the second model is also 100%- by this measure the two models performed similarly.

When using the balanced_accuracy_score measure which takes into consideration the average accuracy for each class, instead of combining them as is the case with standard accuracy- model 2 performs quite a bit better (98.9% vs 95.2%) given that the model takes into consideration the fact that the data set was not balanced at the outset as one target class ("healthy loans") represented a significantly larger portion of observations.

In predicting the likelihood of a "high-risk" loan, neither model performed quite as well. The number of times the first model correctly identified high-risk loans was 85% (563 / 665). The number of times the second model correctly identified high-risk loans was 84% (609/722).  There were fewer instances of high-risk loans for the model to learn from which is likely the reason for this lower score. The recall-the number of times the model accurately predicted the high-risk loans versus the total number of high-risk loans was 91% (563 / 56 + 563) for the first model and 98% (609/609 + 10)for the second model.  By this measure, the second model performed quite a bit better. 

In this case, model 2 in which the data was scaled before fitting to the model proved to have not only a higher balanced accuracy score which accounted for the limited number of data points representing high risk loans, but also had a higher recall score in predictng high risk loans overall.  Therefore model 2 may be superior overall, particularly if identifying individuals who are most likely to default on their loan is of top priority. 