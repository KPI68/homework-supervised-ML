# Module 12 Report

## Overview of the Analysis

* We have a data set containing 77536 data points, each including features of a loan, such as amount. Each data point is labeled with class-0, indicating a healthy loan, or class-1, indicating a high risk loan. In our data set we have 75036 healthy loan samples, 2500 high-risk samples. These are imbalanced samples.
* We are to build machine learning (ML) models to predict high-risk loans. Though high-risk loans have their financial-sense features, such as low-incoming borrower + big loan size + high interest rate, our supervised ML models would not understand. They will focus on classifying data according to the training.
* Since ML uses number as number, we usually should regularize number features to avoid unwarrant meaning, i.e., scale the data and remove the unit. But the basic [LogisticRegression No Need Scaler](https://forecastegy.com/posts/does-logistic-regression-require-feature-scaling/#:~:text=To%20put%20it%20simply%2C%20feature,applied%20uniformly%20across%20all%20features.).
* To prepare for the ML: read file, separate data and label, split train/test sets 
* Train a LogisticRegression model with train set, predict labels of the test set, analyze metrics comparing the prediction with the test labels.
* Considering the imbalacing of our data set, we retry above steps after using RandomOverSampler to add some synthetic class-1 data into the train set.
* We found the over sampling helps a lot to our purpose of identifying high risk loans.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model - basic Logistic Regression
  * Balanced Accuracy Score: 0.9218124642767772
  * Precision of class 0: 0.99
  * Recall of class 0: 1.00
  * Precision of class 1: 0.91
  * Recall of lass 1: 0.85

* Machine Learning Model 2 - random over sampling synthetic class-1
  * Balanced Accuracy Score: 0.9205494133884273
  * Precision of class 0: 0.99
  * Recall of class 0: 1.00
  * Precision of class 1: 0.99
  * Recall of lass 1: 0.84
  
## Summary

The random over-sampling performs better at the prediction of high-risk, having pretty high precision in class-1 (0.99). This is the model we recommend.

Although this high score is at a cost of class-0 performance, which leads to some healthy loans to be falsely identified as high-risk loans, considering the purpose of the model, failing to pick out a high-risk would mean more loss than falsely identifying an ordinary loan, the trade-off is acceptable for the benefit.
