# Time Series Forecasting: Household Appliance Energy Prediction

## Project Overview

This project aims to predict the energy consumption of household appliances using a combination of historical energy usage data, indoor environment conditions, and outdoor weather data. Accurately forecasting residential energy demand allows for optimising smart grid management and reducing carbon footprints.

The dataset is based on a low-energy passive house located in Stambruges, Belgium, combined with weather station data from the nearby Chièvres Airport. It contains 10-minute interval readings over a 4-month period.

## Experiment

This project involves an end-to-end time series forecasting pipeline, which includes thorough data exploration and the implementation of deep learning models.

-   Exploratory data analysis: Extracted time-based features (month, day, hour, weekday) and performed time series decomposition (trend, seasonality, and residuals).
-   Data preprocessing: Handled continuous data streams with no missing values. Performed Principal Component Analysis (PCA) to reduce the data's complexity and optimised the model training process.
-   Model training: I implemented 10 different forecasting approaches across various categories to establish a robust performance benchmark.
    -   Naive baselines: Made prediction based on the last observed value, the trailing 24-hour seasonal observation, and the trailing 7-day seasonal observation.
    -   Statistical time series: ARIMA and multivariate VARMAX.
    -   Machine learning ensembles: Linear regression, random forest, support vector machine (SVM), and gradient boosting (XGBoost).
    -   Deep learning: A custom Long Short-Term Memory (LSTM) neural network.

All models were evaluated chronologically using a train/test split of 80:20 to prevent data leakage. Three metrics are selected for the evaluation: Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and Mean Absolute Percentage Error (MAPE).

## Results

-   The LSTM model outperformed the others with the best scores across all metrics on the unseen test set (RSME: 78.10, MAE: 40.83, MAPE: 0.41).
-   Pattern recognition: While traditional models like ARIMA and linear regression established solid baseline results, they failed to capture the sharp and volatile spike patterns of the energy consumption. The LSTM, however, successfully captured these complex fluctuations.
-   Traditional machine learning models like random forest and SVM produced relatively good and stable results, but also failed to capture the spike patterns and were less precise than the deep learning architectures.
