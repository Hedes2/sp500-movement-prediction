# Stock Market Movement Predictor

## Overview

This project focuses on predicting the next-day movement of the S&P 500 index using historical price data and a machine learning model. By training a Random Forest classifier on features like Open, High, Low, Close, and Volume, the model predicts whether the market will rise the following day.

## Data Source

The data is retrieved using the `yfinance` API, covering the full historical range of the S&P 500 (`^GSPC`).

## Features Used

- Open
- High
- Low
- Close
- Volume

## Target Variable

A binary target variable was created:
- `1` if the next day’s closing price is higher than today’s
- `0` otherwise

## Model

- Random Forest Classifier from scikit-learn
- Two versions: base model and improved model with probability thresholding
- Custom backtesting framework to simulate realistic performance evaluation

## Key Steps

- Data cleaning and preparation
- Feature creation (`Target`, `Tomorrow`)
- Train-test split using last 100 rows as test set
- Model training and evaluation using precision score
- Implementation of a rolling backtest loop

## Results

- Base model precision: ~0.53–0.63 depending on configuration
- Performance shows some predictive power over random guessing
- Backtesting enabled a more realistic evaluation of model consistency

## Libraries Used

- Python
- pandas
- yfinance
- scikit-learn
- matplotlib

## How to Run

1. Clone this repository.
2. Install dependencies: `pip install yfinance pandas scikit-learn matplotlib`
3. Run the Jupyter Notebook: `Stock_predictor.ipynb`
4. Experiment with hyperparameters and test periods.

## Limitations

- Uses only price-based features — no sentiment, macroeconomic data, or technical indicators.
- Evaluation based on precision alone; could be extended to include other metrics (recall, F1, etc.).
- Predicting stock market movements remains a complex and uncertain task.

## Acknowledgments

Data provided by Yahoo Finance via the `yfinance` API. Model built using scikit-learn.
