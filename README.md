# Regression---Bike-Sharing-Demand-Prediction-
Capstone Project: Capstone - End to End Machine Learning
## 📖 Introduction

The bike sharing system, much like other transport services like public buses, trains and cabs
caters to a group with fluctuating demands affected by a variety of factors. Predicting this
demand can prove to be efficacious as it allows one to stock bikes in docking stations
according to user demands in advance. This allows bike sharing systems to become not just
an economical and healthy mode of transport, but also a reliable mode of transport.
In this project, the Seoul Bike Share Demand dataset was used to understand bike share use
trends, apply machine learning techniques to predict the number of bikes rented at any given
hour and provide reasonable explanations from the best predicting model to understand
factors affecting bike share demands.
The efficiency of standard machine learning techniques namely Linear Regression, Nearest
Neighbors, Decision Trees, Random Forests, Bagging, Boosting and Stacking were
implemented and their performances were compared.


## 📖 Dataset Information and Preparation

* There are 24 logs(one for each hour of the day) of bike rental data recorded consistently for each day.
* The ‘Date’ attribute has the date of the recording stored as a string. This attribute is converted to
datetime format and features indicating day of the week, weekends, different times of the day and month are collected.
* Features such as hour of the day, day of the week and month are not exclusively continuous. These features are rather cyclic in nature and this
needs to be reflected to capture routines and recurring behaviors in the data we are interested in predicting.
* In order to do so, the trigonometric sine and cosine of their relative values are used.
* The physical data describing the weather in the city of Seoul are temperature, humidity, windspeed, visibility, solar radiation, rainfall and snowfall. 
* The dataset contains features such as Weekend and Holiday that might explain sudden fluctuations in
activity. There are 18 holidays in Seoul where one might notice a demand trend varying from a regular workday trend.


## 📖 EDA Observations and findings

* From Exploratory Data Analysis, we found that the bike rentals follow an hourly trend
where it hits the first peak in the morning and the highest peak next, in the evening.
* It was also found that these trends are prominent only during weekdays and working days, leading us to make a safe assumption that office-goers make a notable contribution in bike sharing demand. 
* In addition, seasons were observed to have a notable effect on bike rentals, seeing high traffic during the summers and a significant
low during the winters.


## 📖 Evaluation Metric
The metrics measured for evaluating performance of bike share prediction models are:
  * RMSE
  * MAE
  * R-SQUARED, and
  * Adjusted R-SQUARED

## 📖 ML Models Evaluated

As the data available is collected only over the period of one year, time-series forecasting is not considered. But instead, traditional regressive Machine Learning Models are trained and evaluated
  * Linear Regression 
  * Lasso Regression 
  * Ridge Regression
  * Decision Tree
  * K Nearest Neighbors
  * Gradient Boosting
  * Cat Boosting 
  * Light Gradient Boosting
  * Bagging
  * Random Forest

The top models are picked to tune hyperparameters in order to further optimize
their results. These models are also stacked and evaluated using Stacking
Ensemble.

## 📖 Results

* Upon evaluation, the Linear models (Linear Regression, Lasso Regression and Ridge Regression)
performed nominally and increased with regularization. This improvement only explained 61.4% of the variance at best.

* As non-linear models like K-NN and CART were implemented, significant improvements in their R squared scores were
observed, explaining 78 % and 79 % of the variances in predictions explained by the dataset respectively.

* The CatBoost, LightGBM and Random Forest produced
the highest R squared results of 0.9234, 0.9093 and 0.8977.

* Hyperparameter tuning increased the R squared scores of these models to 0.9369, 0.9216 and 0.9093 respectively.

* Upon evaluation, the Stacking Regressor’s( CatBoost, LightGBM and Random Forest) score was 0.938, outperforming all the other models.

## 📖 Conclusions

* The top three models were CatBoost, LightGBM and Random Forest.

* Their results were further optimized using hyperparameter tuning. 

* These three tuned models were used in a Stacking Ensemble producing the highest R2 score of 0.9380 and a root mean squared error of 160.59.

  ● It was found that the top performing models made predictions based on the weather
and time of the day as high weightage was given to seasons, temperature recorded
and hour of the day.
