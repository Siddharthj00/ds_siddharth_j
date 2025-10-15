# Data Science Assignment: Trader Sentiment Analysis


---

## Project Objective

This project analyzes the relationship between the trading behavior of crypto traders and overall market sentiment.Using historical trade data and the Bitcoin Fear & Greed Index, the goal is to identify statistically significant patterns and trends that could inform smarter, data-driven trading strategies.

---

## Datasets Used

* **Bitcoin Market Sentiment:** A daily record of the Fear & Greed Index, which includes a sentiment classification like 'Fear', 'Greed', etc.
* **Historical Trader Data:** A granular dataset of individual trades from Hyperliquid, detailing trade size, direction, and profitability.

---

## Summary of Findings

The analysis concluded that a strong inverse correlation exists between market sentiment and average trader profitability.

* **Contrarian Profitability:** The most profitable trades, on average, were executed during periods of "Extreme Fear," suggesting that buying when the market is pessimistic is a historically effective strategy.
* **High-Volume Greed:** Periods of "Greed" and "Extreme Greed" saw high trading volume but lower average profitability, indicating a riskier, herd-driven market environment.
* **Top Trader Behavior:** Top traders (by volume) demonstrated an even stronger tendency to profit from market fear, suggesting they employ contrarian strategies more effectively than the average participant.

---

## Repository Contents

* **`notebook_1.ipynb`**: The main Google Colab notebook containing all Python code for data cleaning, analysis, and visualization.
* **`ds_report.pdf`**: A detailed report summarizing the final insights, methodology, and strategic recommendations.
* **`README.md`**: This file, providing an overview and setup instructions.
* **`csv_files/`**: A directory containing the raw datasets used in the analysis.
* **`outputs/`**: A directory containing all saved charts and visual outputs generated during the analysis

---

## How to Run

1.  **Environment:** This project is designed to be run in a Google Colab environment.
2.  **Libraries:** The analysis requires the following Python libraries: `pandas`, `matplotlib`, and `seaborn`.
3.  **Execution:** Open `notebook_1.ipynb` in Google Colab. Ensure the file paths for the datasets are correct, then execute the notebook cells sequentially.
