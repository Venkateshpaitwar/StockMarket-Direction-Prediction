# Stock Market Direction Prediction using Machine Learning

## Overview

This project predicts whether the **S&P 500 index will move up or down on the next trading day** using machine learning techniques.
Historical financial data is collected using the `yfinance` API and engineered with trend-based features and rolling window statistics.

A **Random Forest classifier** is trained on historical market data and evaluated using **time-series backtesting**, which simulates real-world prediction scenarios.

---

## Dataset

* Data Source: Yahoo Finance (via `yfinance`)
* Asset: S&P 500 Index (`^GSPC`)
* Time Range: Full historical data available from Yahoo Finance

The dataset includes:

* Open
* High
* Low
* Close
* Volume

---

## Feature Engineering

To improve predictive performance, several time-series features were created:

### Trend Features

These capture the number of positive market movements in previous time windows.

* Trend over 2 days
* Trend over 5 days
* Trend over 60 days
* Trend over 250 days
* Trend over 1000 days

### Price Ratio Features

These compare current price to rolling averages:

* Close / 2-day rolling average
* Close / 5-day rolling average
* Close / 60-day rolling average
* Close / 250-day rolling average
* Close / 1000-day rolling average

These features help the model understand **short-term, medium-term, and long-term market trends**.

---

## Model

The project uses a **Random Forest Classifier** from Scikit-learn.

### Model Parameters

* `n_estimators = 200`
* `min_samples_split = 50`
* `random_state = 1`

Random Forest was chosen because it:

* Handles nonlinear relationships well
* Works effectively with tabular financial data
* Reduces overfitting through ensemble learning

---

## Backtesting Strategy

Instead of randomly splitting data, the model uses **time-series backtesting**.

This method:

1. Trains the model on historical data.
2. Predicts future data sequentially.
3. Repeats the process over multiple time windows.

This simulates how the model would perform in **real trading conditions**.

---

## Evaluation Metric

The model is evaluated using **Precision Score**.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* yfinance

---

## Future Improvements

Possible enhancements to this project include:

* Adding **lag features**
* Implementing **LSTM deep learning models**
* Comparing multiple ML models (Logistic Regression, XGBoost)
* Deploying the model as a **web dashboard**
* Creating an **automated prediction pipeline**

---

## Author - Venkatesh Paitwar
