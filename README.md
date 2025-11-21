# 📈 Automated Forex Trend & Volatility Analyzer

## 🚀 Project Overview

This project implements a **Machine Learning-driven approach** to automate key components of technical analysis in the Forex market. By applying **Linear Regression** and statistical metrics, the tool objectively quantifies market conditions—specifically **Trend Strength** and **Trend Reliability**—to move beyond subjective manual charting.

It provides a highly efficient way to scan a portfolio of currency pairs and instantly prioritize trade opportunities based on objective, data-backed metrics.

## 💡 Key Features & Business Value

* **Quantitative Trend Detection:** Replaced subjective manual trendlines with the **Slope coefficient** from a Linear Regression model. This provides an objective, mathematical measure of trend strength (Bullish/Bearish).
* **Statistical Reliability Scoring:** Implemented the **R-Squared ($\boldsymbol{R^2}$) Score** to measure the "goodness of fit" for the trendline. This is critical for filtering out noisy, unreliable markets ($R^2$ close to 0) and focusing on smooth, high-conviction trends ($R^2$ close to 1).
* **Risk Quantification:** Calculates the **Standard Deviation** of daily returns to provide an immediate measure of market volatility and risk exposure.
* **Automated Pipeline:** Developed an efficient workflow using **Pandas** and the **`yfinance` API** to scan, model, and rank an entire portfolio of currency pairs in seconds.

## 🛠 Technical Architecture & Tech Stack

| Component | Library/Tool | Purpose |
| :--- | :--- | :--- |
| **Data Source** | `yfinance` | Retrieves historical OHLCV data for currency pairs (e.g., `EURUSD=X`). |
| **Data Manipulation** | `pandas` & `numpy` | Essential for time-series cleaning, slicing (60-day window), and array reshaping for Scikit-Learn. |
| **Machine Learning** | `scikit-learn` | Used for the `LinearRegression` model, slope calculation, and R-Squared scoring. |
| **Visualization** | `matplotlib` | Creates the comparative grid plots, showcasing actual price points vs. the derived trendline. |
| **Environment** | Jupyter Notebook | Interactive environment for development and presenting the final ranked DataFrame output. |

## 📊 Key Results & Insights

The analysis systematically ranks market opportunities based on the $R^2$ score, prioritizing statistical reliability:

### Summary Table (Last 60 Days - Ranked by Reliability)

| Currency Pair | Observed Trend | R² Score | Conclusion |
| :--- | :--- | :--- | :--- |
| **USD/JPY** | Strong Positive Slope | **0.87** | Highly reliable and sustained bullish trend (High-Conviction). |
| **GBP/USD** | Strong Negative Slope | **0.78** | Reliable bearish trend; price points are tight to the regression line. |
| **AUD/USD** | Flat/Weak Slope | **0.36** | Low reliability, indicating consolidation or high noise. **Avoid trend-following.** |

### Visualization Example

The visualization clearly shows how the $R^2$ score corresponds to visual noise. High $R^2$ (USD/JPY) means data points closely hug the red regression line, while low $R^2$ (AUD/USD) shows chaotic scatter.

![Visualization of Forex Trend and Volatility Analyzer output showing R-squared values on charts](http://googleusercontent.com/image_collection/image_retrieval/some_id_string)

*(The image above shows the visual output: **USD/JPY** has a strong linear fit ($R^2: 0.87$), while **AUD/USD** shows a noisy, poor fit ($R^2: 0.36$), confirming the need to filter poor data quality.)*

## 🛠️ Installation & Usage

### Prerequisites
Install the required libraries:

```bash
pip install yfinance pandas matplotlib scikit-learn numpy


