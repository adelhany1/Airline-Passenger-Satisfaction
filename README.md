# Airline-Passenger-Satisfaction

### What factors lead to customer satisfaction for an Airline?

https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction

#### About Dataset:
Context:

This dataset contains an airline passenger satisfaction survey. What factors are highly correlated to a satisfied (or dissatisfied) passenger? Can you predict passenger satisfaction?

Content
Gender: Gender of the passengers (Female, Male)

Customer Type: The customer type (Loyal customer, disloyal customer)

Age: The actual age of the passengers

Type of Travel: Purpose of the flight of the passengers (Personal Travel, Business Travel)

Class: Travel class in the plane of the passengers (Business, Eco, Eco Plus)

Flight distance: The flight distance of this journey

Inflight wifi service: Satisfaction level of the inflight wifi service (0:Not Applicable;1-5)

Departure/Arrival time convenient: Satisfaction level of Departure/Arrival time convenient

Ease of Online booking: Satisfaction level of online booking

Gate location: Satisfaction level of Gate location

Food and drink: Satisfaction level of Food and drink

Online boarding: Satisfaction level of online boarding

Seat comfort: Satisfaction level of Seat comfort

Inflight entertainment: Satisfaction level of inflight entertainment

On-board service: Satisfaction level of On-board service

Leg room service: Satisfaction level of Leg room service

Baggage handling: Satisfaction level of baggage handling

Check-in service: Satisfaction level of Check-in service

Inflight service: Satisfaction level of inflight service

Cleanliness: Satisfaction level of Cleanliness

Departure Delay in Minutes: Minutes delayed when departure

Arrival Delay in Minutes: Minutes delayed when Arrival

Satisfaction: Airline satisfaction level(Satisfaction, neutral or dissatisfaction)

## Results: 

First I understand the data and did some EDA on it. Univariate and Bivariate analysis, Cleaned the data and did a Feature Engineering on it, Label Encoding, Upsamping, Removing Outliers. Then select the features that matter the most for the Machine Learning cycle.

It is binary classification problem so I decided to use K-Nearest Neigbors Classifier at first and after choosing the best value of K, auc = 0.9692
Then I used Decision Tree classifier, auc = 0.9795

Decided to use Ensemble Learning and start with Bagging, used Random Forest which gives an auc = 0.9923

Reduce number of features using Feature Importance on Decision Tree, I removed some features that is not that important according to Decision Tree and continue Ensemble Learning with boosting Techniues.
Used XGboost classifier with certain hyperparameters and it gives auc = 0.9903

Then I tried Hyperparameter Tuning and used XGboost with Grid Search and cross validation to choose the best hperparameter and train the model on them .. then it gives auc = 0.9894 !
I also used stacking technique (Stacking Classifer) which works by splitting the data into training and validation sets. The base classifers (KNN-Random Forest-XGboost) are then trained on the training set and their predictions are made on the validation set. These predictions are used as input to the meta-classifer (LogisticRegression), which is trained on the validation set labels. Gives an auc = 0.9883

Also I used some Automated Machine Learning techniques like Hyperopt, Optuna, AutoML(AutoGluon).
