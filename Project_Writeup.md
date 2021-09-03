# Browsing or Buying? Predicting Online-Purchasing Behavior 🛒  
Varsha Garla

## Abstract
The goal of this project was to predict the probability that an online shopper visiting an e-commerce website would make a purchase during their session. My e-commerce client wanted to be able to discern which customers had a medium likelihood (probability between 0.3 and 0.7) of buying their product, meaning we are neither confident that they won't purchase nor that they will purchase. The e-commerce client planned to offer these shoppers who are on the border a coupon in order to incentivize purchases. In addition, the client wanted recommendations on how to its purchase conversion rate (the percentage of website visitors who purchased something from the online store over a period of time). Therefore, it was important that the classification model built was interpretable.

## Design
This project consisted of several phases, [1] cleaning and performing exploratory analysis on the client's data, [2] building several baseline models using different classification algorithms, and [3] improving the chosen model. I chose to build a logistic regression model because the e-commerce client wanted the predicted probabilities that an online shopper would make a purchase, so a model that output reliable soft predictions was necessary. In addition, the client was going to offer coupons/improve their promotional strategies and website based off of the model's predictions, so the interpretability of the model's and the feature importance was a priority. I used the area under the ROC curve (ROC AUC) and LogLoss as metrics to evaluate the model's soft predictions.

## Data
The dataset, which can be found comes from the research of Sakar, C.O., Polat, S.O., Katircioglu, M. et al. and it was obtained from the UC Irvine Machine Learning Repository. It contains clickstream and user information from 12,330 online shopping sessions. Each observation represents a session of a unique user in a 1-year period to avoid any tendency to a specific campaign, special day, user profile, or period. To access and view a detailed description of the dataset, click [here](https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset).

## Algorithms
_Feature Engineering_

The features representing the number of different types of pages visited ("Administrative", "Informational", "ProductRelated") and the total time spent on these pages ("Administrative Duration", "Informational Duration", "ProductRelated Duration") were collinear. To handle this, new features for the average time spent on a given page per category were engineered to capture this information while avoiding the risk of the coefficients shrinking and being less interpretable.

_Modelling_

Baseline models using Logistic Regression, KNN, Decision Tree, Random Forest, and XGBoost were created before picking logistic regression as the final model based on the criteria of outputting reliable soft preditions and being interpretable. Features were selected based on EDA and comparing the model's performance using all features and a subset of features. Class imbalance was handled by cross validating possible class weights. The logistic regression hyperparameters, C (regularization) and penalty (lasso or ridge) were tuned with GridSearchCV.

_Model Evaluation and Selection_

The entire dataset was split into 80/20 stratified train/test sets. All scores and predictions were made with 5 KFolds. Predictions on the test (holdout) set were made at the end of model tuning. The metrics chosen to evaluate the model's soft predictions were ROC AUC and LogLoss.

## Tools
- Numpy and Pandas for data cleaning and EDA
- Scikit-learn for modeling and scoring
- Matplotlib and Seaborn for plotting

## Communication
The findings and slide deck accompanying this project's presentation are accessible in this GitHub repository.
