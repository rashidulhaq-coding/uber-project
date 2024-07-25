# Uber Taxi Fares Analysis

## Overview
This repository contains a Jupyter Notebook that analyzes the Uber Taxi Fares dataset. The analysis includes data loading, preprocessing, exploratory data analysis, data cleaning, and building a linear regression model to predict taxi fares.

## Dataset
The dataset contains 200,000 entries with the following features:
- `Unnamed: 0`: Index
- `key`: Unique identifier for each trip
- `fare_amount`: Fare amount in dollars
- `pickup_datetime`: Timestamp of the pickup
- `pickup_longitude`: Longitude of the pickup location
- `pickup_latitude`: Latitude of the pickup location
- `dropoff_longitude`: Longitude of the dropoff location
- `dropoff_latitude`: Latitude of the dropoff location
- `passenger_count`: Number of passengers

## Analysis Steps
1. **Data Loading and Preprocessing**: Load the dataset and display the first few rows.
2. **Exploratory Data Analysis (EDA)**: Generate descriptive statistics and visualize the data.
3. **Data Cleaning**: Remove outliers and add a distance feature using the Haversine formula.
4. **Model Building**: Train a linear regression model to predict fare amounts.
5. **Model Evaluation**: Evaluate the model's performance using mean squared error and R-squared metrics.

## How to Run
1. Clone this repository.
2. Ensure you have the necessary libraries installed:
   ```bash
   pip install pandas numpy matplotlib geopy scikit-learn
