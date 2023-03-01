# Time Series Forecasting with XGBoost and Prophet

This project aims to forecast the energy consumption of PJME (PJM Interconnection LLC), an electric power grid operator in the United States, using XGBoost (eXtreme Gradient Boosting), a popular machine learning algorithm, and Facebook's Prophet, a popular open-source library for time series forecasting. The dataset used in this project is obtained from Kaggle (**https://www.kaggle.com/robikscube/hourly-energy-consumption**).

# Requirements
The following packages need to be installed to run this project:

* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `xgboost`
* `sklearn`
* `fbprophet`

# Data

The dataset contains hourly power consumption data from PJM from January 1st, 2002 to December 31st, 2018 for the entire east region.

# Usage

The project involves the following steps:

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

# Model Creation

Two models are created in this project. First, an XGBoost regressor is trained and evaluated using the above data splits and features. The following hyperparameters are used:

* n_estimators: 1000
* early_stopping_rounds: 50
* max_depth: 3
* learning_rate: 0.01

The feature importance of this model is also visualized.

Next, Facebook's Prophet package is used to forecast hourly energy consumption. The dataset is resampled to daily frequency before being fed into the Prophet model. The model is trained on the training set and validated on the test set using cross-validation. The performance of the model is evaluated using the root mean squared error (RMSE). Finally, the trained model is used to make predictions on the test set. The predictions are plotted against the actual values to visualize the performance of the model.

# Setup

Clone the repository.
Install the required packages.
Run the `xgboost_time_series_forecasting.py` file for XGBoost and the Prophet libraries.

1. XGBoost Time Series Forecasting:
In this file, you can find an implementation of time series forecasting using XGBoost. The dataset used in this file is the AirPassengers dataset which contains the monthly number of airline passengers from January 1949 to December 1960. The aim is to predict the number of airline passengers for the next few months using historical data.

The code loads the dataset, splits it into training and testing sets, prepares the data for XGBoost, trains an XGBoost model on the training data, and evaluates the model on the testing data. The evaluation metrics used in this file are mean squared error (MSE) and root mean squared error (RMSE).

2. Prophet Time Series Forecasting:
In this file, you can find an implementation of time series forecasting using the Prophet library developed by Facebook. The dataset used in this file is also the AirPassengers dataset. The Prophet library provides a simple and intuitive way to model time series data and generate accurate forecasts.

The code loads the dataset, splits it into training and testing sets, prepares the data for Prophet, fits a Prophet model on the training data, and makes predictions on the testing data. The evaluation metric used in this file is mean absolute percentage error (MAPE).

Both of these files provide a good starting point for anyone interested in time series forecasting using XGBoost or Prophet. They can be used as a reference for implementing time series forecasting on other datasets as well.
