# Project4-Home Location Prediction
# Readme: Ontario Housing Search Prediction Model

## Overview

This readme details the development of a the machine learning model built to predict housing location in Ontario, Canada based on affordability. The model focuses on evaluating the location of houses based on buyers' input.

## Data Loading and Preprocessing

1. **Data Source**: The dataset originates from an undisclosed source, comprising Ontario housing data.
2. **Dataframe Creation**: The dataset is loaded into a Pandas DataFrame for manipulation and analysis.
3. **Columns**: The DataFrame includes columns for city, price, address, number of beds and baths, province, population, geographical coordinates, and median family income.

## Feature Engineering

1. **Income Percentages**: New features are created by calculating 9%, 18%, and 27% of the median family income.
2. **Installment Features**: Additional features are derived by dividing the house price by the aforementioned income percentages, representing potential installment amounts.

## Model Selection and Training

1. **Feature Selection**: Selected features include the number of beds, baths, and the newly created income and installment features.
2. **Data Splitting**: The dataset is split into training and testing sets, with a test size of 20%.
3. **Standardization**: Features are standardized using `StandardScaler` for use in SVM and KNN models.

## Model Building

1. **Linear Regression**: Implemented as a baseline model.
2. **Support Vector Regression (SVR)**: An SVR model is trained on the scaled data.
3. **K-Neighbors Regression (KNN)**: A KNN regression model is applied, also on the scaled data.

## Model Evaluation

1. **Evaluation Metric**: R-squared is used as the evaluation metric.
2. **Performance**: The Linear Regression model shows a high R2 score (0.99), but this could indicate overfitting. The SVR model performs poorly with a negative R2 score. The KNN model shows a decent R2 score of 0.77.

## Model Optimization

1. **KNN Optimization**: GridSearchCV is used to find the best parameters for the KNN model.
2. **Best Parameters**: The best parameters are identified as 3 neighbors with a 'distance' weight.
3. **R2 Score Improvement**: The optimized KNN model shows a slightly improved R2 score of 0.783.

## Predictive Function

A function `predict_house_price` is developed to predict house prices based on user input (number of beds, baths, desired installment percentage, and house price). It also searches for houses within a specified price range.

## Why KNN?

KNN was chosen for its simplicity and effectiveness in handling multi-feature datasets. It's a non-parametric method, suitable for a dataset where the relationship between features and the target variable (price) might not be linear. KNN's ability to adapt to new data makes it a good choice for real estate datasets, which are often diverse and dynamic.

## Conclusion

This model, utilizing KNN regression, provides a practical approach to predicting house prices in Ontario, taking into account various financial and physical aspects of the properties. The model is particularly useful for assessing affordability based on family income levels.
