
# 📊 Time Series Analysis & Forecasting of UPI Transactions

## **Overview**

This project analyzes **UPI transaction data** (Volume & Value) from the **Reserve Bank of India (RBI)** to detect trends, seasonality, and patterns, and to forecast future transactions using both **statistical** and **deep learning** models. Models evaluated include **ARIMA**, **SARIMA**, **Vanilla RNN**, **LSTM**, and **GRU**.

---

## **Dataset**

* **Attributes**:

  1. Date of transaction
  2. Volume (in Lakhs)
  3. Value (in INR Crores)
* **Source**: [RBI Official Dataset](https://www.rbi.org.in/Scripts/BS_PressReleaseDisplay.aspx?prid=49901#)

---

## **Key Analysis Steps**

1. **Exploratory Data Analysis (EDA)**

   * Handled missing values & formatted dates
   * Plotted trends by year, month, and week
   * Detected \~30-day seasonality via **Fourier Transform**
   * Decomposed into trend, seasonal, and irregular components

2. **Stationarity & Parameter Selection**

   * **Augmented Dickey-Fuller Test** for stationarity
   * Applied 30-day differencing to stabilize variance
   * Used **ACF/PACF plots** for ARIMA/SARIMA parameter tuning

3. **Modeling**

   * **ARIMA**: Good at trend capture, weak on seasonality
   * **SARIMA**: Explicitly models both seasonal & non-seasonal parts
   * **Deep Learning Models**:

     * **GRU** – Best for Volume forecasting (balanced dependencies)
     * **Vanilla RNN** – Best for Value forecasting (short-term focus)
     * **LSTM** – Good trend capture but over-smoothed

4. **Residual Analysis**

   * Ljung-Box test for independence
   * Residual ACF/PACF, Q-Q plots for normality checks

---

## **Key Findings**

* **SARIMA** outperformed ARIMA in seasonal settings
* **GRU** excelled at volume forecasts
* **Vanilla RNN** surprisingly beat LSTM & GRU for value predictions
* **LSTM** needs careful tuning to avoid over-smoothing
