# Predicting Fantasy Premier League scores
Creating a model to predict Fantasy Premier League player scores and a dashboard for users to identify high scoring players for their team

This project aims to augment user’s ability to select the best possible FPL team by developing:
1.	A model that predicts number of points scored for each FPL player in each of their upcoming games
2.	A dashboard that allows users to interact with the prediction data and identify players that would fit in to their team given a set of constraints

Below shows an overview of each script and its purpose.

---

## PROJECT: 1. CREATING MODEL HISTORY FILE.IPYNB

### Purpose
Combine data to create the dataset for exploratory analysis and feature engineering

### Input
Fantasy Premier League API: https://fantasy.premierleague.com/api

Historic dataset available at: https://github.com/vaastav/Fantasy-Premier-League

### Output
Dataset downloaded and saved to:
https://raw.githubusercontent.com/robert-shepherd/fpl/main/fpl_combined_data.csv

---

## PROJECT: 2. EXPLORATORY ANALYSIS AND FEATURE ENGINEERING.IPYNB

### Purpose
Clean the combined data and develop features to use for model production

### Input
Combined data produced in script 1

### Output
Dataset downloaded and saved to:
https://raw.githubusercontent.com/robert-shepherd/fpl/main/fpl_features.csv

---

## PROJECT: 3.1 MODEL BUILD SETUP.IPYNB

### Purpose
Select features, partition data into train/test datasets, and split out X (feature variables) and Y (response variable)

### Input
Feature data produced in script 2

### Output
Datasets downloaded and saved to:

X train: https://raw.githubusercontent.com/robert-shepherd/fpl/main/X_train.csv

X test: https://raw.githubusercontent.com/robert-shepherd/fpl/main/X_test.csv

Y train: https://raw.githubusercontent.com/robert-shepherd/fpl/main/Y_train.csv

Y test: https://raw.githubusercontent.com/robert-shepherd/fpl/main/Y_test.csv

---

## PROJECT: 3.2 LINEAR REGRESSION MODEL.IPYNB

### Purpose
Develop the Linear Regression model

### Input
Split data produced in script 3.1

### Output
No output

---

## PROJECT: 3.3 PRINCIPAL COMPONENT REGRESSION.IPYNB

### Purpose
Develop the Principal Component Regression model

### Input
Split data produced in script 3.1

### Output
No output

---

## PROJECT: 3.4 RIDGE REGRESSION MODEL.IPYNB

### Purpose
Develop the Ridge Regression model

### Input
Split data produced in script 3.1

### Output
No output

---

## PROJECT: 3.5 LASSO REGRESSION MODEL.IPYNB

### Purpose
Develop the Lasso Regression model

### Input
Split data produced in script 3.1

### Output
No output

---

## PROJECT: 3.6 ELASTIC NET MODEL.IPYNB

### Purpose
Develop the Elastic Net model

### Input
Split data produced in script 3.1

### Output
No output

---

## PROJECT: 3.7 DECISION TREE MODEL.IPYNB

### Purpose
Develop the Decision Tree (C&R) model

### Input
Split data produced in script 3.1

### Output
No output

---

## PROJECT: 3.8 RANDOM FOREST MODEL.IPYNB

### Purpose
Develop the Random Forest model

### Input
Split data produced in script 3.1

### Output
No output

---

## PROJECT: 3.9 XGBOOST MODEL.IPYNB

### Purpose
Develop the XGBoost model

### Input
Split data produced in script 3.1

### Output
Model saved to Google Cloud Storage (project_id: 'fpl-scoring'):
gs://fpl-scoring/fpl_xgb_model.dat

List of variables used to build the model saved to Google Cloud Storage (project_id: 'fpl-scoring'):
gs://fpl-scoring/fpl_xgb_model_variables.csv

---

## PROJECT: 4. SCORING NEW DATA.IPYNB

### Purpose
Score new data and refresh the data available for the dashboard

### Input
Model data produced in script 3.9 and Fantasy Premier League API

### Output
Data saved as parquet files to Google Cloud Storage (project_id: 'fpl-scoring'):

Player data: player_data.parquet

History data: history_data.parquet

Fixture (prediction) data: fixture_data.parquet

Team data: team_data.parquet

---
