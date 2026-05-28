# AQI Prediction Model Using Python

This repository contains a Jupyter Notebook (`AQI Prediction Model.ipynb`) that implements a machine learning model to predict the Air Quality Index (AQI) based on various air pollutant levels. 

## Overview
Air quality is a critical factor for public health. This project focuses on predicting the AQI using historical air quality data. The dataset includes measurements for various pollutants such as PM2.5, PM10, NO, NO2, NH3 (Ammonia), CO, O3, SO2, Benzene, Toluene, and Xylene.

## Dataset
The data used in this project is sourced from a CSV file named `air quality data.csv`. It contains 29,531 records and 16 columns. 

### Features:
- **City:** The city where the measurements were taken.
- **Date:** The date of the measurement.
- **PM2.5:** Particulate Matter 2.5 micrometers or less in diameter.
- **PM10:** Particulate Matter 10 micrometers or less in diameter.
- **NO:** Nitric Oxide.
- **NO2:** Nitrogen Dioxide.
- **NOx:** Nitrogen Oxides.
- **NH3:** Ammonia.
- **CO:** Carbon Monoxide.
- **SO2:** Sulfur Dioxide.
- **O3:** Ozone.
- **Benzene:** Benzene levels.
- **Toluene:** Toluene levels.
- **Xylene:** Xylene levels.
- **AQI:** The Air Quality Index (Target Variable).
- **AQI_Bucket:** The category of the AQI (e.g., Good, Satisfactory, Poor).

### Data Preprocessing
The dataset underwent preprocessing steps to handle missing values and prepare it for model training:
1. **Handling Missing Values:** Rows where the target variable (`AQI`) was missing were dropped. The dataset was analyzed to determine the percentage of null values in other features. For instance, Xylene had the highest percentage of missing values (61.86%). 
2. **Exploratory Data Analysis (EDA):** Univariate analysis (histograms and boxplots) and bivariate analysis (scatter plots, pairplots) were performed to understand the distribution of variables and their relationships. A correlation matrix (heatmap) was generated to identify features highly correlated with AQI.
3. **Feature Selection:** Features that were highly correlated with AQI (such as PM2.5, PM10, NO2, CO, SO2) were selected for the model. Some features with excessive missing values or low correlation were excluded.
4. **Data Splitting:** The data was split into training and testing sets (70% training, 30% testing) using `train_test_split`.
5. **Scaling:** The features were scaled using `StandardScaler` to ensure all features contribute equally to the model.

## Models Evaluated
Several machine learning models were evaluated to find the best performer for AQI prediction:
1. **Linear Regression:** - A basic baseline model.
2. **K-Nearest Neighbors (KNN) Regressor:**
   - Evaluated for non-linear relationships.
3. **Random Forest Regressor:**
   - An ensemble method using multiple decision trees to improve accuracy and control over-fitting.

## Results
The Random Forest Regressor emerged as the best-performing model. 

### Random Forest Regressor Performance:
- **R-Squared (Train):** 0.978
- **R-Squared (Test):** 0.845
- **RMSE (Train):** 0.148
- **RMSE (Test):** 0.390

The Random Forest model demonstrated strong predictive capabilities, capturing the variance in the AQI effectively while maintaining a reasonable error rate on the test data.

## Getting Started

### Prerequisites
To run this notebook, you will need the following Python libraries installed:
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scikit-learn`

### Running the Notebook
1. Clone this repository.
2. Ensure you have the `air quality data.csv` file in the same directory as the notebook.
3. Open `AQI Prediction Model.ipynb` using Jupyter Notebook or JupyterLab.
4. Run the cells sequentially to reproduce the analysis and model training.

## Conclusion
This project demonstrates the application of machine learning techniques to predict air quality based on pollutant concentrations. The Random Forest model provides a robust solution for this regression task. Future work could involve more advanced imputation techniques for missing values or exploring deep learning architectures.
