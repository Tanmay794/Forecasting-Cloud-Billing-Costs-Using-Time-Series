# Forecasting Cloud Billing Costs Using Time Series & Extreme Value Theory

A hybrid cloud cost forecasting framework that combines **SARIMA, STL decomposition, and Extreme Value Theory (EVT)** to model both predictable cloud usage patterns and unpredictable cost spikes. The project analyzes multi-cloud billing data and introduces a spike-aware forecasting architecture for improved cloud cost visibility and planning.

## Overview

Cloud billing data exhibits strong daily seasonality but is frequently disrupted by sudden cost spikes caused by events such as auto-scaling, batch workloads, policy changes, and resource provisioning. Traditional forecasting models struggle to capture these anomalies.

This project develops a **Decomposition-Based Hybrid Anomaly-Forecasting Framework (DHAFF)** that:

- Separates trend, seasonality, and residual components using STL decomposition
- Models regular spending patterns with SARIMA
- Characterizes extreme billing spikes using EVT and Generalized Pareto Distributions (GPD)
- Benchmarks statistical, machine learning, and deep learning forecasting approaches

## Key Findings

- Improved forecasting accuracy by **9.7%** compared to seasonal-naïve baselines
- Identified that **44.2% of cloud cost variance** originated from anomaly-driven spike events
- Demonstrated that cloud billing spikes behave as exogenous events rather than volatility clustering
- Established EVT as a more suitable framework than GARCH for cloud cost anomaly modeling

## Dataset

- **Source:** FinOps Foundation FOCUS 1.0 Sample Dataset
- **Records:** 100,000+ cloud billing transactions
- **Providers:** AWS, Azure, Google Cloud, Oracle Cloud
- **Coverage:** September 2024
- **Frequency:** Hourly aggregated cloud spend (720 observations)

## Methodology

### Data Processing
- Billing aggregation and cleaning
- Log transformation
- Stationarity testing (ADF, KPSS)
- Exploratory time series analysis

### Forecasting Models
- Seasonal Naïve
- Simple Exponential Smoothing
- SARIMA
- Facebook Prophet
- XGBoost
- LightGBM
- LSTM

### Anomaly Modeling
- STL decomposition
- Extreme Value Theory (EVT)
- Generalized Pareto Distribution (GPD)
- Poisson spike arrival modeling

## Tech Stack

- Python
- Pandas
- NumPy
- Statsmodels
- Scikit-Learn
- XGBoost
- LightGBM
- TensorFlow / Keras
- Matplotlib
- Seaborn

## Results

| Model | Performance |
|---------|------------|
| Seasonal Naïve | Baseline |
| Prophet | +2.7% improvement |
| LSTM | +6.1% improvement |
| SARIMA | **+9.7% improvement** |

SARIMA(1,0,1) × (0,1,1)[24] emerged as the most reliable and statistically robust forecasting model for the dataset.

## Repository Structure

```
├── data/
├── notebooks/
├── src/
├── results/
├── figures/
├── Cloud_billing_Forecasting.ipynb
└── README.md
```

## Future Work

- Incorporate real-time cloud monitoring metrics
- Extend forecasting horizon beyond 30 days
- Integrate workload-level metadata
- Develop automated FinOps anomaly alerting system
- Deploy as an end-to-end cloud cost monitoring dashboard

## Author

- Tanmay Chowdhary

---

Built to explore how advanced forecasting and anomaly detection techniques can improve cloud cost predictability and FinOps decision-making.
