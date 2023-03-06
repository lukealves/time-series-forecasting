# Hourly Time Series Forecasting using Facebook's Prophet

This project demonstrates how to use Facebook's Prophet package to forecast hourly energy use. We will use PJM's hourly power consumption data from 2002-2018 for the entire east region.

# Introduction

Time series forecasting has become increasingly important for businesses and organizations to predict future values based on historical patterns. Energy consumption is one of the critical applications of time series forecasting. In this project, we will use Facebook's Prophet, a popular open-source library for time series forecasting, to predict hourly energy consumption.

# Data

We will use hourly power consumption data from PJM, which has some unique characteristics that will be interesting to observe if Prophet can pick them up. The dataset contains hourly power usage from 2002 to 2018 for the entire east region.

# Time Series Features

We will create some time series features to help Prophet understand the patterns in the data better. These features include the hour of the day, day of the week, weekday/weekend indicator, quarter, month, year, day of year, day of month, week of year, and season. Season will be a categorical variable and will be determined based on the date_offset, which is calculated by subtracting 320 from the month and day, and then taking the modulo by 1300. The values of season will be "Spring," "Summer," "Fall," or "Winter."

# Train / Test Split

We will split the data into two parts: training and testing. The training data will be from 2002 to 2014, and the testing data will be from 2015 to 2018. We will plot the data to visualize the split.

# Simple Prophet Model

We will use Prophet to create a simple forecast model on the training data. The Prophet model expects the dataset to have specific column names, which we will rename before feeding it into the model. We will fit the model on the training data and predict on the test data.

# Evaluation Metrics

We will use two evaluation metrics to assess the model's performance: Mean Absolute Error (MAE) and Mean Absolute Percentage Error (MAPE).

# Conclusion

This project provides a hands-on guide to using Facebook's Prophet package for time series forecasting. It is a powerful tool for businesses and organizations that want to forecast future values based on historical patterns. The model's accuracy can be further improved by tuning the hyperparameters, adding more features, or using a more sophisticated model.