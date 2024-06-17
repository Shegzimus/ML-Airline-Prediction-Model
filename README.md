# Airline Prediction Model
This repository contains a Jupyter notebook for training machine learning models to predict if a flight will be delayed or cancelled using historical data. The data needed are available in the repository along with replicas with engineered features. Extreme Gradient Boosting (XGBoost) was used in this project.

## Table of Contents

- [Getting Started](#getting-started)

- [Introduction](#introduction)

- [Data Exploration and Preparation](#data-exploration-and-preparation)

- [Feature Engineering](#feature-engineering)

- [Classifier initialization and training](#classifier-initialization-and-training)

- [Prediction and Evaluation](#prediction-and-evaluation)

- [Acknowledgements](#acknowledgements)

## Getting Started

To run the notebooks, you need the following packages installed in your IDE:
  - Python 3.11.2
  - Jupyter Notebook or JupyterLab
  - Pandas
  - NumPy
  - Scikit-Learn
  - xgboost

## Introduction
Final project for a machine learning course at the [University of Europe for Applied Sciences](https://www.ue-germany.com/de).

The objective was to create a prediction model using a dataset of our choice with an acceptable level of accuracy within a given timeframe.

The dataset was obtained from [Kaggle](https://www.kaggle.com/datasets/d45803bbd62477e068ac4c596444a1e133a7c56f9a2499574f5f297d14f21820). The dataset prominently incorporates fields such as Passenger ID, First Name, Last Name, Gender, Age, Nationality, Airport Name, Airport Country Code, Country Name, Airport Continent, Continents, Departure Date, Arrival Airport, Pilot Name, and Flight Status. These columns collectively provide comprehensive insights into passenger demographics, travel details, flight routes, crew information, and flight statuses. Researchers and industry experts can leverage this dataset to analyze trends in passenger behaviour, optimize travel experiences, evaluate pilot performance, and enhance overall flight operations.

## Data Exploration and Preparation
Relevant libraries are imported and the data in the form of a csv file is read into a Dataframe. Irrelevant columns are dropped to aid the analysis.

## Feature Engineering
New features, such as 'Day_of_Week' and 'Month', are extracted from the 'Departure Date'. Additionally, a unique feature 'Continent_Date' is created by combining encoded continent data with the day of the year. The relevant features for modelling are selected and the target variable 'Flight Status' is encoded into binary values. Categorical variables are label encoded, and the features are standardized using a standard scaler. Finally, the dataset is split into training and testing sets to prepare for model training and evaluation.

## Classifier initialization and training
The XGBoost library is utilized to train a classifier on the preprocessed training dataset. The classifier is initialized with logloss as the evaluation metric to optimize the model's performance on binary classification. The fit method is then called to train the model using the training features and labels.

## Prediction and Evaluation
The performance of the XGBoost classifier is finally evaluated. It first predicts the labels for the test set and then calculates the accuracy of these predictions. Additionally, it prints a classification report that includes detailed metrics such as precision, recall, and F1-score, giving a deeper insight into the model's effectiveness across different classes. This DataFrame is subsequently sorted in descending order based on feature importance values. Finally, it displays the top 10 most important features. This process is crucial for understanding which features the XGBoost model relies on most heavily when making predictions, aiding in feature selection and model interpretation for further improvements.

## Acknowledgements
The dataset provided here is a simulated example and was generated using the online platform found at [Mockaroo](https://www.mockaroo.com/). This web-based tool offers a service that enables the creation of customizable Synthetic datasets that closely resemble real data. It is primarily intended for use by developers, testers, and data experts who require sample data for a range of uses, including testing databases, filling applications with demonstration data, and crafting lifelike illustrations for presentations and tutorials



