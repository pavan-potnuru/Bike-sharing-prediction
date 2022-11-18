# Bike Sharing Demand Prediction




## Abstract
As a convenient, economical, and ecofriendly travel mode, bike-sharing greatly improved urban mobility. However, it is often very difficult to achieve a balanced utilization of shared bikes due to the asymmetric user demand distribution and the insufficient numbers of shared bikes, docks, or parking areas. If we can predict the short-run bike-sharing demand, it will help operating agencies rebalance bike-sharing systems in a timely and efficient way.
## Problem Statement
We are here to explore the bike sharing dataset and build a model to do the following:
* Maximize: The availability of bikes to the customer. 
* Minimize: Minimize the time of waiting to get a bike on rent. 
The main goal of the project is to: Find factors and causes which influence shortages of bikes and time delay of availing bikes on rent. Using the data provided, this paper aims to analyze the data to determine what variables are correlated with bike demand prediction. Hourly count of bikes for rent will also be predicted.

## Introduction
* Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.
* The goal of this project is to build a ML model that is able to predict the demand of rental bikes in the city of Seoul. We are provided with the data of weather conditions, office holidays, and the number of bikes rented each hour for 12 months.
## EDA Summary
* The bike rental count saw an increasing trend in the first half of the year, then there is a slight decreasing trend till the 8th month. Then there is a slightly increasing trend till the 9th month and then there is a decreasing trend till the end of the year. Sudden drop and spikes in the chart may be due to Non-functioning days, weekends and holidays.
* Few of the numerical variables are positively skewed and few of them are negatively skewed.
* Not very strong linear relation with any independent variable.
* The number of bikes rented has seen an increasing trend in the first half of the year then a decreasing trend.
* Day of the month doesn't seem to have much effect on the bike rental count.
* With respect to hours of the day, there is a spike in bike rental in the morning around 9 AM and also in the evening around 7 PM, which are generally the times people commute to their workplaces, colleges etc.
* In correlation analysis we saw high correlation b/w 'Temperature' and 'Dew point temperature are highly correlated. Very High correlation between ‘Temperature’ and ‘Dew point temperature’.‘Humidity is moderately correlated with ‘solar radiation’ and ‘visibility’.Remaining all other variables have minimal or almost no correlation.

## Modelling Summary
* Choice of split: K-fold cross validation, where K = 6 This choice of split was chosen because we had the computational power available to use this split, and thereby reducing overfitting
* Evaluation metrics: R2-score. R2 score is defined as the proportion of the variance in the dependent variable that is predictable from the independent variable(s).
* Hyperparameter tuning: GridsearchCV Grid Search combines a selection of hyperparameters established by the scientist and runs through all of them to evaluate the model’s performance. Through this method, we can establish the set of parameters such that they do not overfit the data.

### Linear Regression
* This can be considered as the baseline model to obtain predictions.
* Linear Regression R2-Score for training dataset : 0.577
* Linear Regression R2-Score for testing dataset : 0.553

### LASSO Regression
* LASSO regression is a regularization technique. It is used over regression methods for a more accurate prediction. Lasso Regression uses L1 regularization technique. It is used when we have more features because it automatically performs feature selection.
* LASSO Regression R2-Score for training dataset : 0.577
* LASSO Regression R2-Score for testing dataset : 0.553

### Ridge Regression
* Ridge regression is a model tuning method that is used to analyse any data that suffers from multicollinearity. This method performs L2 regularization.
* Ridge regression R2-Score for training dataset : 0.577
* Ridge regression R2-Score for testing dataset : 0.553

### Elastic Net Regression
* Elastic net linear regression uses the penalties from both the lasso and ridge techniques to regularize regression models.
* Elastic Net R2-Score for training dataset : 0.577
* Elastic net R2-Score for testing dataset : 0.553

### Decision tree
* Decision trees are easy to explain, and tend to have low bias and high variance (Overfitting).
* Decision Tree R2-Score for training dataset : 0.787
* Decision Tree R2-Score for testing dataset : 0.748

### Random Forest
* Random Forest is an ensemble technique which use multiple decision trees and a technique called Bootstrap and Aggregation, commonly known as bagging. The basic idea behind this is to combine multiple decision trees in determining the final output rather than relying on individual decision trees.
* Random Forest R2-Score for training dataset : 0.937
* Random Forest R2-Score for testing dataset : 0.865

### Extreme Gradient Boosting (XG Boost)
* In XG Boost, decision trees are created in sequential form. Weights are assigned to all the independent variables which are then fed into the decision tree which predicts results. The weight of variables predicted wrong by the tree is increased and the variables are then fed to the second decision tree. These individual classifiers/predictors then ensemble to give a strong and more precise model.
* XG Boost R2-Score for training dataset : 0.962
* XG Boost R2-Score for testing dataset : 0.884
## Results
|S.No|Model|Train R2 score|Test R2 score|
|----|-----|--------------|-------------|
|1|Linear Regression|0.577|0.553|
|2|LASSO Regression|0.577|0.553|
|3|Ridge Regression|0.577|0.553|
|4|Elastic Net Regression|0.577|0.553|
|5|Decision Tree|0.787|0.748|
|6|Random Forest|0.937|0.865|
|7|XG Boost|0.962 |0.884|

## Conclusions
It was found that XG Boost model has the highest R2 score

The final choice of model for deployment depends on:

* If it is absolutely necessary to have a model with the best accuracy, then XG boost will be the best choice, since it has the lowest RMSE and highest R2 score than other models built.
* But we know that, higher the model complexity, lower is the model interpretability. Hence if the predictions must be explained to stakeholders, then XG Boost is not an ideal choice.
* As there is no linear relationship between the dependent and independent variables, we can see that the linear regression based models have performed poor.

## References

* Alma Better
* GeekforGeeks
* Towards data science
* Analytics Vidhya
* ProjectPro
* Kaggle
* W3 school
* Pythonguides
* Stackoverflow
* Python libraries technical documentation
* Krish Naik on Youtube
* Codebasics on Youtube
* 3blue1brown on Youtube
