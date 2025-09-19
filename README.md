# Predicting-Future-Store-Sales-with-AI
Project Overview

This project is part of Day 6 of the GeeksforGeeks 21 Days 21 Projects challenge. The goal is to apply time series analysis and forecasting techniques on the classic Airline Passengers dataset (1949–1960), which records monthly totals of international airline passengers.

The project demonstrates:

Exploratory Data Analysis (EDA) of the time series.

Stationarity testing using the Augmented Dickey-Fuller (ADF) test.

Transformations and differencing to stabilize variance and remove trends.

Building and comparing non-seasonal ARIMA and seasonal ARIMA (SARIMA) models.

Evaluating model performance using Root Mean Squared Error (RMSE).

📊 Dataset

Source: Airline Passenger Time Series Dataset

Time Period: January 1949 – December 1960

Frequency: Monthly

Features:

Month: Date (monthly intervals)

Passengers: Number of airline passengers

🔍 Exploratory Data Analysis (EDA)

The dataset shows a clear upward trend in passenger numbers.

Strong seasonal pattern with peaks and troughs every 12 months.

Variance increases over time, suggesting the need for a log transformation.

Multiplicative seasonal decomposition highlights trend, seasonality, and residuals.

🧪 Stationarity Testing

Stationarity is crucial for ARIMA-type models, which assume constant mean and variance over time.

The ADF test was applied to different transformations:

Original series: Non-stationary (p-value > 0.05).

Log-transformed series: Reduced variance but still non-stationary.

Log-differenced series: Stationary (p-value < 0.05), suitable for ARIMA modeling.

⚙️ Models Implemented
1. ARIMA (AutoRegressive Integrated Moving Average)

Built a non-seasonal ARIMA(p,0,q) on the log-transformed data (without differencing).

Grid search used to select best (p,q) by AIC.

Performance was limited as the model could not capture strong seasonality.

2. SARIMA (Seasonal ARIMA)

Seasonal order (1,1,1,12) applied to handle yearly seasonality.

Captured both trend and seasonal patterns effectively.

Outperformed non-seasonal ARIMA in terms of forecast accuracy (lower RMSE).

📈 Results

ARIMA (non-seasonal): Reasonable trend capture but poor seasonal fit.

SARIMA: Better overall fit, accurately modeled yearly cycles.

RMSE:

Non-seasonal ARIMA: Higher RMSE (weaker fit).

SARIMA: Lower RMSE, preferred for forecasting.

🛠️ Tech Stack

Python Libraries:

pandas, numpy – Data handling

matplotlib, seaborn – Visualization

statsmodels – ARIMA/SARIMA modeling, stationarity testing, decomposition

scikit-learn – RMSE evaluation

🚀 How to Run

Clone the dataset repository:

git clone https://github.com/GeeksforGeeksDS/21-Days-21-Projects-Dataset


Install dependencies:

pip install pandas numpy matplotlib seaborn statsmodels scikit-learn


Run the notebook/script provided to:

Load and explore the dataset.

Perform stationarity testing.

Build ARIMA and SARIMA models.

Compare forecasts.

📚 Key Learnings

Importance of checking and achieving stationarity before ARIMA modeling.

How log transformation and differencing stabilize variance and remove trends.

Seasonal components in time series require SARIMA for accurate modeling.

RMSE provides a good metric for comparing forecasting models.

📌 Future Improvements

Automate model selection using pmdarima.auto_arima.

Explore advanced models like Prophet, TBATS, or LSTM for long-term forecasting.

Conduct residual diagnostics (Ljung-Box, residual ACF) for deeper validation.
