# PJME Energy Consumption Forecasting

This project aims to forecast the energy consumption of PJME (PJM Interconnection LLC), an electric power grid operator in the United States, using XGBoost (eXtreme Gradient Boosting), a popular machine learning algorithm.

The dataset used in this project is obtained from Kaggle **(https://www.kaggle.com/robikscube/hourly-energy-consumption)**. The dataset contains hourly energy consumption data from PJME from January 1st, 2002 to December 31st, 2018.

The project involves the following steps:

# Outlier Analysis and Removal

1. Train/Test Split
2. Time Series Cross Validation
3. Feature Engineering
4. Train Using Cross Validation
5. Forecasting

# Outlier Analysis and Removal

The dataset contains a few outliers which need to be removed. The outliers are identified by plotting the histogram of the 'PJME_MW' column and visually inspecting the data. The outliers are removed using a threshold of 19,000 MW.

# Train/Test Split
The dataset is split into a training set and a test set using a date of January 1st, 2015, as the split point. The training set contains data from January 1st, 2002, to December 31st, 2014, and the test set contains data from January 1st, 2015, to December 31st, 2018.

# Time Series Cross Validation
To evaluate the performance of the model, time series cross-validation is used. The dataset is split into five folds using TimeSeriesSplit from scikit-learn. Each fold is a combination of a training set and a test set. The length of the test set is one year, and there is a gap of 24 hours between the training and test set.

# Feature Engineering
Time series features are created based on the time series index. The following features are created:

* hour
* dayofweek
* quarter
* month
* year
* dayofyear
* dayofmonth
* weekofyear

Lag features are also created to capture the trend in the data. The following lag features are created:

* lag1: target (PJME_MW) one year ago
* lag2: target (PJME_MW) two years ago
* lag3: target (PJME_MW) three years ago

# Train Using Cross Validation
The XGBoost algorithm is used to train the model. The following hyperparameters are used:

* n_estimators: 1000
* early_stopping_rounds: 50
* max_depth: 3
* learning_rate: 0.01

The model is trained on each fold of the cross-validation data, and the performance of the model is evaluated using the root mean squared error (RMSE).

# Forecasting

Finally, the trained model is used to make predictions on the test set. The predictions are plotted against the actual values to visualize the performance of the model.