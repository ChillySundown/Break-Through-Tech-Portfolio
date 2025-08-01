# 🏡 Airbnb Price Predictor

Accurately predicting the nightly price of Airbnb listings using regression models and data preprocessing techniques.

---

## 📌 Table of Contents

- [Overview](#overview)
- [Pipeline Architecture](#pipeline-architecture)
  - [1. Data Preparation](#1-data-preparation)
  - [2. Linear Regression](#2-linear-regression)
  - [3. Gradient Boosted Trees (GBDT)](#3-gradient-boosted-trees-gbdt)
  - [4. Hyperparameter Tuning](#4-hyperparameter-tuning)
- [📊 Results](#results)
- [🚀 Future Work](#future-work)
- [🎯 Project Purpose](#project-purpose)
- [🛠️ Tech Stack](#tech-stack)

---

## 🧠 Overview

This project explores price prediction for Airbnb listings through a regression modeling pipeline. Three models are evaluated:

- **Linear Regression**
- **Gradient Boosted Regressor**
- **Optimized Gradient Boosted Regressor (via GridSearchCV)**

The end goal is to develop a model that can power an intelligent **Price Estimation Tool** for new Airbnb hosts.

---

## ⚙️ Pipeline Architecture

### 1. Data Preparation

- Feature engineering: added and removed relevant features
- Imputed missing values in `'beds'` using `pandas.isnull()` and `fillna()`
- Winsorized outliers in `'price'` and `'review_scores_rating'`
- Applied log transformation to `'price'` to normalize the distribution
- Converted `has_availability` from boolean to numeric
- One-hot encoded `room_type` and `neighbourhood_group_cleansed`
- Computed a correlation matrix to identify key features
- Dropped redundant columns like `beds_na` and original winsorized columns

---

### 2. Linear Regression

- Split data into training and test sets
- Applied `StandardScaler` for normalization
- Fitted a `LinearRegression` model
- Evaluated with RMSE and R²

---

### 3. Gradient Boosted Trees (GBDT)

- Fitted a `GradientBoostingRegressor` with:
  - `max_depth=10`
  - `n_estimators=300`
- Evaluated with RMSE and R²

---

### 4. Hyperparameter Tuning

- Used `GridSearchCV` to optimize:
  - `max_depth`
  - `n_estimators`
- Trained GBDT with optimal parameters
- Compared performance against baseline models

---

## 📊 Results

| Model                          | R² Score | RMSE   |
|-------------------------------|----------|--------|
| Linear Regression             | 0.42     | 104.9  |
| GBDT (Non-Optimized)          | 0.56     | 91.4   |
| GBDT (Optimized via GridSearchCV) | **0.76** | **89.1**  |

---

## 🚀 Future Work

- Expand to larger, more diverse property datasets
- Perform deeper EDA and feature scaling
- Explore advanced models:
  - Neural Networks
  - Stochastic Gradient Descent Regressor (SGD)
- Target a reduced RMSE of **< 50**

---

## 🎯 Project Purpose

_Affordability_ is a core value of Airbnb. This model contributes to a smart **Price Estimation Tool** to assist new hosts in setting competitive and fair prices.

> "Price too low? Lose revenue. Too high? Lose customers."

This model ensures:
- Hosts get data-driven price estimates
- Travelers benefit from fair pricing
- Airbnb improves marketplace efficiency

---

## 🛠️ Tech Stack

### 📊 Machine Learning Models
- **Linear Regression** — baseline model for price prediction
- **Gradient Boosted Decision Trees (GBDT)** — for improved non-linear performance
- **GridSearchCV** — for hyperparameter tuning and model optimization

### 🧹 Data Processing & Feature Engineering
- **Pandas** — data manipulation and preprocessing
- **NumPy** — numerical computing
- **Scikit-learn** — preprocessing tools (e.g., `StandardScaler`, `OneHotEncoder`)

### 📈 Data Visualization
- **Matplotlib** — basic plotting
- **Seaborn** — statistical visualizations (e.g., correlation heatmaps)

### 🧪 Experimentation & Development
- **Jupyter Notebook** — interactive experimentation environment
- **Python 3.8+** — core programming language

---

📫 **Let’s Connect!**  
If you found this project insightful or want to collaborate, feel free to reach out or check out my GitHub profile.

---



