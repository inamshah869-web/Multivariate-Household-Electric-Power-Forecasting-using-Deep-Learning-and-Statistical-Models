# Multivariate-Household-Electric-Power-Forecasting-using-Deep-Learning-and-Statistical-Models

## 1. Objective

The goal of this project was to perform **multivariate time series forecasting** using the **UCI Individual Household Electric Power Consumption** dataset. The primary objective was to predict **`Global_active_power`** by comparing classical statistical forecasting methods with modern deep learning architectures.

---

## 2. Methodology

### Data Processing

* Aggregated raw **minute-by-minute electricity consumption data into hourly averages** to reduce noise and capture meaningful temporal patterns.
* Handled multiple electricity consumption variables for multivariate forecasting.

### Feature Engineering

The forecasting framework incorporated multiple variables, including:

* `Global_active_power`
* `Global_reactive_power`
* `Voltage`
* `Global_intensity`
* `Sub_metering_1`
* `Sub_metering_2`
* `Sub_metering_3`

### Stationarity Analysis

The **Augmented Dickey-Fuller (ADF) test** was used to assess stationarity and determine the suitability of the data for time series modelling.

### Forecasting Models

Four forecasting approaches were evaluated:

1. **ARIMA** — Classical statistical baseline for non-seasonal time series forecasting.
2. **SARIMA** — Extension of ARIMA incorporating seasonal patterns, particularly the observed **24-hour daily cycle**.
3. **LSTM** — Recurrent Neural Network architecture designed to capture long-term temporal dependencies.
4. **TCN (Temporal Convolutional Network)** — Deep learning architecture using **causal and dilated convolutions** for sequence modelling.

---

## 3. Experimental Setup

The dataset was divided into training and testing portions, with the **final 15% of observations reserved as the held-out test set**.

Model performance was evaluated using:

* **Mean Absolute Error (MAE)**
* **Root Mean Squared Error (RMSE)**
* **Mean Absolute Percentage Error (MAPE)**

This enabled comparison between classical statistical approaches and deep learning-based forecasting models.

---

## 4. Results Summary

### Classical vs. Deep Learning

The **LSTM and TCN models generally outperformed ARIMA and SARIMA**, demonstrating the ability of deep learning approaches to leverage the multivariate structure of the dataset and capture nonlinear temporal relationships.

### Effect of Seasonality

**SARIMA improved upon ARIMA** by explicitly modelling the daily seasonal pattern observed during exploratory data analysis.

### Overall Observation

For this dataset, the **TCN provided the most robust forecasting performance** among the evaluated approaches.

> **Note:** The numerical MAE, RMSE, and MAPE values are stored in the project's `results/` directory.

---

## 5. Project Structure

```text
Multivariate-Household-Electric-Power-Forecasting/
│
├── models/
│   └── *.pth
│
├── plots/
│   ├── actual_vs_forecast.png
│   └── ...
│
├── results/
│   ├── metrics.csv
│   └── ...
│
├── notebooks/
│   └── ...
│
├── src/
│   └── ...
│
├── README.md
└── requirements.txt
```

---

## 6. Key Artefacts

### Models

Trained deep learning models are saved as `.pth` files in the `models/` directory.

### Visualisations

Forecasting results and comparisons between predicted and actual electricity consumption are available in the `plots/` directory.

### Results

Model evaluation metrics and configuration details are stored in the `results/` directory.

---

## 7. Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Statsmodels
* PyTorch
* LSTM
* Temporal Convolutional Networks (TCN)
* ARIMA
* SARIMA

---

## 8. Conclusion

This project demonstrates the application of both **classical statistical forecasting and deep learning techniques** to multivariate household electricity consumption data.

The experiments showed that deep learning models, particularly the **Temporal Convolutional Network (TCN)**, provided robust forecasting performance by capturing nonlinear relationships and temporal dependencies across multiple electricity consumption variables.

### Future Work

Potential improvements include:

* Hyperparameter optimisation
* Longer forecasting horizons
* Advanced TCN and LSTM architectures
* Incorporation of external variables such as **weather data**
* Evaluation across different seasonal periods
* Development of real-time electricity demand forecasting systems

---

## 9. Research Relevance

This project demonstrates practical experience in:

* **Multivariate time series analysis**
* **Deep learning for forecasting**
* **Temporal sequence modelling**
* **Feature engineering**
* **Statistical stationarity testing**
* **Model comparison and evaluation**
* **Energy consumption forecasting**

It provides a foundation for further research into **time series forecasting, deep learning, energy analytics, and intelligent energy management systems**.

