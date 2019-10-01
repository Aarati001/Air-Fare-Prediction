# Air-Fare-Prediction
# Building predictive models to predict air fares
Analysis of flight prices across destinations based on flight routes and market shares of airlines – to help businesses and customers with revenue management 

# Why this project?
Flight prices rapidly changes over time,destinations,stoppages and airlines.Some airlines may provide cheaper fares to travel to certain destinations during offseasons.Holiday seasons tend to increase the air fare significantly.Airlines with huge market shares generally charge high ticket prices irrespective of the seasons.So for a customer to decide the best options with best flight prices to travel, analyzing the prices ahead of time is preferred.  

# Market Research

# Dataset
The Air fare dataset contains 1000 records of air fares of market leading airlines and low price airlines between different routes.It also additionaly contains data regarding average passengers travelling in each route every week and the distance between the source and the destination.On the whole, it contains 11 features or dimensions to describe the air fares.

Following are the features used in the dataset:
#
City1 (source)
City2 (destination)
Average Fare
Distance
Average weekly passengers
market leading airline
market share
Average fare1
Low price airline
market share1
price

# Preprocessing
The features ('City1','City2','market leading airline','Low price airline') are categorical and contain labels.Since there are more than 20 unique values in these columns, encoding these categorical values using dummification or one hot encoding will result in more number of columns.The approach used here to convert these labels into numbers is label encoding(each unique value is encoded with a unique number).The data was also found to have some outliers with the help of box plot.But these outliers seemed to be legitimate in cases of distance, flight prices and average fares.So these extreme outliers are also used for building our model.There was no need to handle missing values as the data was very clean without any null or improbable values.

# Analysis and Insights

# Modelling
The dataset was split into training data and testing data on the basis of 70:30 ratio.A base Optimal Least Squares Method is generated to understand the data and verify linear assumptions.
Verifying linear assumptions: 
  Durbin watson test proved absence of auto correlation
  Heat map,VIF values and p values(OLS) showed no signs of multicollinearity.
  Goldfeld Quandt test proved absence of heteroscedasticity
  Rainbow test and residual plots showed that data is linear.
  Shapiro Wilk test for normality failed.
Since most of the assumptions are satisfied, we go ahead and build a linear regression model.
From the plots generated , the data seems to be a little scattered.So polynomial function is applied to the features and then linear model is then trained on it.

Following are the metrics comparison of the 2 models built.

In addition to these, ensemble methods were also used to improve the rmse scores.
Following are the metrics comparisons of the ensemble methods

# Inference
From all the modelling techniques used, we can see that polynomial regression model has been built with the best r2 score and rmse.The high R2 score indicates that 98% variance of prices is explained by all the features.The lower mse indicates that the the model's fitness of the line is very precise and accurate with very less error.
