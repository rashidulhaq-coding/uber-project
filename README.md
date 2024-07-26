# Uber Taxi Fares Project
![uber](https://images.unsplash.com/photo-1593950315186-76a92975b60c?q=80&w=1887&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)

## Project Overview
The Uber Taxi Fares project aims to analyze, explore, clean, and structure the data, and then fit a linear model to understand the relationship between features for better business insights.

## Dataset Overview
The dataset contains 200,000 samples, each with 7 characteristics. All of them have a data type of float except the `pickup_datetime` and `id`, which are of type int.

## Preparing Data for EDA
We dropped 1 duplicate column, removed a sample because of missing values, and created the `distance_km` column as it was not provided.

## Exploratory Data Analysis Findings
We created different visualizations to understand data distribution and characteristics. Some of the findings are:
- The majority of trips have a distance of less than 5 km.
- The fare amount for most trips is between 0 to 20 dollars.
- In the majority of trips, the number of passengers was between 1-6.
- Analysis of trips and revenue per month shows that summer months have fewer trips compared to the whole year.
- The number of trips per day is high on Monday and low on Saturday and Sunday.
- Analyzing the revenue per day shows that Monday has the lowest revenue compared to Friday.
- The mean fare amount with respect to the number of passengers shows no relationship, so we conducted a hypothesis test, which revealed a relationship.

## Linear Regression Model
To fit the linear regression model, we first removed outliers and engineered some features.

### Outliers
We removed outliers from the `fare_amount`, `distance_km`, and `passenger_count` columns.

### Feature Engineering
- Created `day` and `month` columns from the `pickup_datetime` column.
- Created a `rush_hour` column indicating 1 for trips between 6 am-10 am and 4 pm-8 pm.
- Scaled all the variables.

### Fitting the LR Model
Before fitting the model, we dropped `latitude`, `longitude`, `pickup_datetime`, `day`, and `month` and used only `passenger_count`, `distance_km`, and `rush_hour`.
- After finding the optimal hyperparameters using the grid search method, the model achieved an R² score of 0.61, indicating it explains 61% of the variance in the data.
- Analyzing the coefficients, we concluded:
  - For every 1.42 km traveled, the fare increases by a mean of 2.95 dollars or for every 1 km traveled, the fare increases by a mean of 2.08 dollars.

## Predictive Model
After fitting the LR model, we fitted other models to find a predictor for real-time prediction. We engineered additional columns like `daytime`, `nighttime`, `am_rush`, `pm_rush`, etc.
- Applied Random Forest and XGBoost to the data and found that XGBoost outperforms the others with a variance of 0.62, which will be used for prediction purposes.

## Libraries Used
- numpy
- pandas
- matplotlib
- seaborn
- scipy
- sklearn
- xgboost

## Note
This is the end of the project. If you liked it or found it useful, please upvote it. If you have any suggestions, please let me know.
