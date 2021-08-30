## Classification Project Proposal

### Browsing or Buying? Predicting Online Shoppers' Purchasing Intention

#### Question/need:
Thanks to the Internet, retailers across the world have set up online stores and e-commerce is on the rise. According to [UN trade and development experts](https://news.un.org/en/story/2021/05/1091182), global retail sales rose dramatically during the pandemic, from 16 per cent to 19 per cent in 2020. For these online retailers, while their sites may be getting a lot of traffic, not all visits result in purchases. Therefore, it can be useful to be able to predict whether an online shopper will make a purchase or not during their session. Additionally, it can be useful to understand what about an online shopper or their session makes them more likely to purchase in order to improve website abandonment and purchase conversion rates.

#### Data Description:
The dataset comes from the [research](https://link.springer.com/article/10.1007%2Fs00521-018-3523-0) of Sakar, C.O., Polat, S.O., Katircioglu, M. et al. It contains clickstream and user information from 12,330 online shopping sessions. The dataset was formed so that each session would belong to a different user in a 1-year period to avoidany tendency to a specific campaign, special day, user profile, or period. 

The dataset consists of 10 numerical and 8 categorical **features**:
- types of pages visited: Administrative, Informational, Product Related
- total time spent on page categories: Administrative Duration, Informational Duration, Product Related Duration
- "Google Analytics" metrics: Bounce Rate, Exit Rate, Page Value
- Date of Session: Special Day, Month, Weekend
- Vistor characteristics: operating system, browser, region, traffic type, visitor type as returning or new visitor

The **label** will be the boolean feature Revenue, meaning whether a session was finalized with transaction.

#### Tools:
I will use Python packages such as pandas and numpy for exploratory data analysis and feature engineering. To build the classification model, I will use python packages such as sklearn, and xgboost. For EDA and diagnostic visualizations, I will use matplotlib and seaborn. 

#### MVP Goal:
A minimum viable product for this project would be a baseline model using a simple algorithm such as KNN along with error metrics (such as accuracy and logloss) and an evaluation of the model's performance.
