# covid19_MI

## Objective
The goal of this project was to accurately predict the number of daily Covid-19 cases across different counties in Michigan using machine learning models. Accurate predictions would allow public health officials to better allocate resources and plan pandemic response measures.

## Data
For this project, I've used a variety of datasets to predict the number of Covid-19 cases for various counties in the state of Michigan.
The datasets include
 - counties.csv, which contains the list of counties in Michigan, along with locations of their nearby weather stations.
 - michigan.csv, which contains the daily covid-19 cases reported for each county in Michigan, downloaded from https://www.michigan.gov/documents/coronavirus/Cases_and_Deaths_by_County_and_by_Date_of_Symptom_Onset_or_by_Date_of_Death2021-10-20_738873_7.xlsx
 - mobility.csv, which contains Apple mobility trends report downloaded from https://covid19.apple.com/mobility.
 - weather.csv. which contains daily weather data downloaded from https://www.ncdc.noaa.gov/cdo-web/search?datasetid=GHCND

## Preprocessing

The data was preprocessed to handle missing values, smooth noise in case count time series data, align different data sources by date, normalize features, and split into train/validation/test sets.

## Models & Evaluation
### Models
Several models were developed and evaluated:

1. Multi-Linear Regression: to model linear relationships between weather, mobility, and cases
2. MLP Regressor: a neural network to uncover complex non-linear relationships
3. Gaussian Mixture Model Clustering: to cluster counties by case patterns

The models were trained on historical data and tuned using cross-validation.

### Evaluation
The models were evaluated on held-out test data using root mean squared error (RMSE). The best model (MLP Regressor) obtained an average RMSE of 4 cases across all counties.

## Feature Importance
Feature importance analysis revealed that day of the week, 7-day case average, and park visits were the most predictive variables - aligning with domain knowledge.

## Summary
In summary, the machine learning models were able to leverage detailed data to make accurate county-level case predictions to assist public health decision-making for pandemic planning and response.
