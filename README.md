# water-demand-forecasting
Simple Python project for analysing and forecasting daily water demand using linear regression. 
This project uses Python to analyse a small dataset of daily water demand and build a simple linear regression model to predict future values. It demonstrates basic skills in data cleaning, modelling, and visualisation using Pandas, NumPy, Matplotlib, and Scikit‑learn.

The project reflects my background in water resources engineering and shows how I apply data science tools to real‑world problems.
# Water Demand Forecasting (Simple Linear Model)

This is a small Python project where I analyse a sample dataset of daily water demand and build a simple linear regression model to predict future demand. The goal is to show basic skills in Python, data analysis, and modelling.

## What the project does
- Loads a CSV file with daily water demand
- Cleans the data
- Creates a simple trend model using linear regression
- Plots the results
- Predicts future demand for the next 7 days

## Tools used
- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

## How to run
1. Install the required libraries:
2. Run the script:

## Why I built this
I have worked with water demand data for many years. This small project shows how I can use Python to analyse and model data in a simple and clear way.
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression

# Sample dataset (you can replace this with a real CSV later)
data = {
    "day": np.arange(1, 31),
    "demand": [120, 118, 121, 123, 119, 122, 124, 125, 126, 128,
               127, 129, 130, 131, 132, 134, 133, 135, 136, 138,
               137, 139, 140, 142, 141, 143, 144, 145, 147, 148]
}

df = pd.DataFrame(data)

# Prepare data
X = df["day"].values.reshape(-1, 1)
y = df["demand"].values

# Train model
model = LinearRegression()
model.fit(X, y)

# Predict next 7 days
future_days = np.arange(31, 38).reshape(-1, 1)
future_pred = model.predict(future_days)

# Plot
plt.figure(figsize=(10, 5))
plt.plot(df["day"], df["demand"], label="Actual Demand")
plt.plot(future_days, future_pred, label="Predicted Demand", linestyle="--")
plt.xlabel("Day")
plt.ylabel("Water Demand (ML/day)")
plt.title("Simple Water Demand Forecast")
plt.legend()
plt.grid(True)
plt.show()
