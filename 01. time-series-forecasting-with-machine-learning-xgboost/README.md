# Time Series Forecasting with XGBoost

This project demonstrates time series forecasting with XGBoost. We will use the PJME Energy Use dataset to predict energy consumption in megawatts.

# About

The objective of this project is to use XGBoost, one of the most popular machine learning algorithms used for time series forecasting, to predict hourly energy consumption for the PJM East region.

# Requirements

The following packages need to be installed to run this project:

* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `xgboost`
* `sklearn`

# Setup

1. Clone the repository.
2. Install the required packages.
3. Run the `time_series_forecasting.py` file.

# Usage

The project performs the following tasks:

1. Data preprocessing:
   * Read the dataset into a pandas DataFrame
   * Convert the Datetime column to a datetime object and set it as the DataFrame's index
2. Train/Test Split:
   * Split the data into training and testing sets based on a specified date range
   * Visualize the split data
3. Feature Creation:
   * Create features based on time series index, such as hour, dayofweek, quarter, month, year, dayofyear, and weekofyear
   * Visualize feature/target relationship
4. Model Creation:
   * Create an instance of the XGBoost regressor with hyperparameters such as n_estimators, early_stopping_rounds, objective, max_depth, and learning_rate
   * Fit the model to the training data and evaluate its performance on the testing data
   * Visualize the feature importance

You can run the code in your preferred Python environment (e.g. Jupyter Notebook, Google Colab) after installing the required packages.