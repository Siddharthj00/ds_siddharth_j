# 📊 Data Science Project: Bitcoin Trader Behavior vs. Market Sentiment

## 🎯 1. Project Overview

This project investigates the influence of collective investor psychology on actual trading outcomes in the cryptocurrency market. Specifically, we analyze the relationship between the **Bitcoin (BTC) Fear & Greed Index** (market sentiment) and **aggregated trader behavior** (profitability and activity) using a historical dataset of trades.

### Key Research Questions
* How does trader profitability (`Closed PnL`) change across different market sentiments (Fear, Greed, Neutral)?
* Is the Fear & Greed Index a **contrarian or confirming indicator** for the average trader?
* How does the overall **trading volume** correlate with increasing market sentiment?

---

## ✨ 2. Core Findings (Executive Summary)

The analysis confirms the **Contrarian Principle** in crypto markets:

| Sentiment Category | Average Daily Net PnL (USD) | Implication |
| :--- | :--- | :--- |
| **Fear** | **Highest Profitability** | The most lucrative period for opening positions. |
| **Greed / Extreme Greed** | **Significantly Lower Profitability** | A caution or profit-taking signal, as markets become overbought. |
| **Extreme Fear** | **Lowest Profitability** | Highly volatile and unpredictable; profitability is weakest here. |

A statistically significant **negative correlation** was found between the numerical Sentiment Value and both Net PnL and Total Trade Volume.

---

## 🛠️ 3. Methodology and Data Processing

The analysis was performed by integrating and aligning two distinct time-series datasets.

### 3.1. Datasets Used
1.  **Historical Trading Data:** High-granularity transactional data including `Account`, `Coin`, `Execution Price`, `Size USD`, `Closed PnL`, and `Timestamp IST`.
2.  **Fear & Greed Index Data:** Daily sentiment scores including `Date`, `Value` (0-100), and `Classification`.

### 3.2. Step-by-Step Process (Notebook: `notebook1.ipynb`)

| Step | Action Taken | Rationale |
| :--- | :--- | :--- |
| **Data Cleaning** | Converted all time-based columns (`Timestamp IST`, `Date`) to a standard **daily datetime format** to enable accurate joining. | Necessary for comparing fine-grained trades against daily sentiment scores. |
| **Filtering** | Filtered the multi-coin trading data to isolate **only BTC trades** (`Coin == 'BTC'`). | Ensures the trade data is directly relevant to the BTC Fear & Greed Index. |
| **Aggregation** | Grouped individual BTC trades by **`Date`** and calculated **daily metrics** (Sum of `Closed PnL`, Sum of `Size USD` as Total Volume). | Condensed millions of rows into a daily frequency to match the sentiment data. |
| **Merging** | Performed an **inner join** on the common `Date` key to create the final analysis DataFrame. | Final dataset for correlation and group-by analysis. |

---

## 💻 4. Technical Requirements

This project was built using standard Python data science libraries.

* **Platform:** Google Colab / Jupyter Notebook
* **Language:** Python 3.x
* **Key Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`

### Code Execution
The entire analysis is contained within the `notebook1.ipynb` file and can be run sequentially on Google Colab without any local environment setup.

---

## 🚀 5. Next Steps / Potential Future Work

* **Lagged Analysis:** Test for correlation using a time lag (e.g., how does today's sentiment correlate with tomorrow's PnL) to see if the index has predictive power.
* **Account-Level Deep Dive:** Group the data by `Account` to see if **profitable accounts** diverge from market sentiment more strongly than unprofitable accounts.
* **Risk Metric:** Analyze the relationship between sentiment and trade risk (e.g., average `Size USD` to `Closed PnL` ratio) to understand leverage and risk-taking behavior.
