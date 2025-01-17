# Movie Popularity Prediction Using SEMMA Methodology

This project aims to predict the popularity of movies using the SEMMA (Sample, Explore, Modify, Model, and Assess) methodology. The dataset used in this project contains various features related to movies, such as title, release date, budget, revenue, genres, production companies, and more.

This is a submission for WIE3007 Data Mining and Warehousing course group project

## Table of Contents

- [Data Source](#data-source)
- [SEMMA Methodology](#semma-methodology)
  - [1. Sample](#1-sample)
  - [2. Explore](#2-explore)
  - [3. Modify](#3-modify)
  - [4. Model](#4-model)
  - [5. Assess](#5-assess)
- [Results](#results)
- [Conclusion](#conclusion)

## Data Source

The dataset used in this project is sourced from Kaggle and contains detailed information about 52,000 animation movies scraped from the TMDB API. This dataset is a subset of the Full TMDB Movies Dataset 2024. You can find the dataset [here](https://www.kaggle.com/datasets/asaniczka/52000-animation-movie-details-dataset-2024).

## SEMMA Methodology

### 1. Sample

In this step, we load the dataset and perform stratified sampling to ensure that the sample is representative of the entire dataset. The steps involved are:

- Load the dataset from `Animation_Movies.csv`.
- Inspect the dataset to understand its structure and contents.
- Create bins for the `popularity` scores and group the data into these bins.
- Perform stratified sampling based on the `popularity_group` to ensure that the sample is representative.
- Save the sampled data to `stratified_sample.csv`.

### 2. Explore

In this step, we explore the sampled dataset to gain insights and understand the distribution of various features. The steps involved are:

- Load the sampled dataset from `stratified_sample.csv`.
- Generate a profile report using `ydata_profiling` to get an overview of the dataset.
- Visualize the distribution of categorical and numerical features using bar charts, scatter plots, and box plots.
- Analyze the frequency of individual genres and production companies.

### 3. Modify

In this step, we clean and preprocess the data to prepare it for modeling. The steps involved are:

- Load the sampled dataset from `stratified_sample.csv`.
- Drop unnecessary columns and rows with missing values.
- Fill missing values in `spoken_languages` and `production_companies` with appropriate values.
- Perform feature engineering to create new features such as `release_year`, `release_month`, `release_day_of_week`, `title_length`, `profit`, `vote_total`, `genre_combo_score`, and `company_combo_score`.
- Save the modified dataset to `modified_ver4.csv`.

### 4. Model

In this step, we build and train various machine learning models to predict the popularity of movies. The steps involved are:

- Load the modified dataset from `modified_ver4.csv`.
- Split the data into training and testing sets.
- Train and evaluate multiple models, including Decision Tree, Linear Regression, SVR, KNN, Random Forest, and Gradient Boosting.
- Perform hyperparameter tuning for Gradient Boosting and Random Forest models.
- Apply PCA (Principal Component Analysis) to reduce the dimensionality of the dataset and retrain the tuned models on the PCA dataset.

### 5. Assess

In this step, we assess the performance of the trained models and compare their results. The steps involved are:

- Evaluate the models using metrics such as RMSE, MSE, MAE, and R².
- Compare the performance of all models and visualize the results.
- Use SHAP (SHapley Additive exPlanations) to interpret the feature importance and understand the impact of each feature on the predictions.

## Results

The results of the project include the performance metrics of various models and the comparison of their performance. The best model based on RMSE, MAE, and R² is selected and further analyzed using SHAP.

## Conclusion

This project demonstrates the application of the SEMMA methodology to predict movie popularity. By following the SEMMA steps, we were able to preprocess the data, build and evaluate multiple models, and interpret the results to gain insights into the factors influencing movie popularity.