# Minimum Viable Product
## Browsing or Buying? Predicting Online Shoppers' 🛒  Purchasing Intention

### Goal
The goal of this project is to predict whether an online shopper is likely to make a purchase during their session on an e-commerce website or not. Based on the assumption that a likely customer will make a purchase and bring in $100 revenue if offered a coupon, if the model predicts that a customer is likely to make a purchase (positive case), then the company will offer them a $5 coupon. Below is a confusion matrix illustrating the **dollar consequences** for the e-commerce client of scenarios in which the model predicts correctly and incorrectly.



![Screen Shot 2021-08-31 at 5 44 29 PM](https://user-images.githubusercontent.com/87044440/131579905-7da27fcd-0ccb-443b-9847-fabc77208d34.png)

_Note:_ Since the e-commerce company desires to increase its purchase conversion rate (the percentage of website visitors who purchased something from the online store over a period of time), the **interpretability** of the model, and determining which features influence an online shopper's likelihood to purchase, is a priority. Knowing these features, such as the month and pages associated with purchases, can guide how the company pushes promotions.

### Metric: F2
_Recall:_ TP / (TP + FN)

As shown, it is important for the company that we have a high recall (how many customers we predict are likely to purchase out of all likely customers). This is achieved by having more true positives and fewer false negatives. This will both maximize profit and minimize cost for the company.

_Precision:_ TP / (TP + FP)

While not as important as recall, precision (of all the customers we predict are likely to purchase, how many are likely customers) is still important. The true positive case brings in profit while false positives bring some lost profit to the company.

In order to capture both recall and precision, we will use F2 as our main metric, which places 2x importance on recall than precision.

### Data
The dataset comes from the research of Sakar, C.O., Polat, S.O., Katircioglu, M. et al. It contains clickstream and user information from 12,330 online shopping sessions. Each observation represents a session of a unique user in a 1-year period to avoid any tendency to a specific campaign, special day, user profile, or period.

### Baseline Model
A baseline logistic regression model was created using a handful of features selected from EDA. These features are: 
- the months November and May
- New Visitor
- Average time user spent on Administrative, Informational, and Product Related pages
- Average exit rates of pages visited by the user

The model had the following cross-validated metrics:
- F2: 0.418
- Precision: 0.769
- Recall: 0.376

![Screen Shot 2021-08-31 at 7 56 13 PM](https://user-images.githubusercontent.com/87044440/131590631-4878c775-0054-4fbd-ae6c-8fadca1f66fd.png)

As shown, there were 563 true positives and 934 false negatives. We will improve the model from here.

### Next Steps
- Logistic regression model on all
- Treat class imbalance
- Try other models such as Decision Tree, RandomForest, KNN, XGBoost (while being mindful that interpretability is important)
- Feature engineering
- Pick best model and tune hyperparameters
