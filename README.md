# S&P 500 Market Analysis and Stock Segmentation Using RFM

## Project Overview

This project analyses S&P 500 stocks using historical market data from 2021 to 2024. It applies risk–return analysis and an adapted RFM (Recency, Frequency and Monetary) model to identify groups of stocks with similar market behaviour and trading activity.

The main objective is to compare different clustering techniques and understand how stocks can be segmented based on their historical returns, market sensitivity and unusual trading-volume activity.

## Objectives

- Analyse historical stock returns and market beta.
- Identify unusual trading-volume events.
- Calculate Recency, Frequency and Monetary measures.
- Apply hierarchical agglomerative clustering and K-means.
- Compare clustering solutions using silhouette scores and Adjusted Rand Index (ARI).
- Examine cluster characteristics and sector composition.
- Evaluate the contribution of Monetary through sensitivity analysis.

## Dataset

- **Market:** S&P 500 stocks
- **Benchmark:** S&P 500 Index (^GSPC)
- **Study period:** 1 January 2021 – 31 December 2024
- **Final sample:** 488 stocks
- **Frequency:** Daily market data, with weekly return analysis

Data includes stock prices, adjusted closing prices and trading volume. The RFM model uses unusual-volume events to measure trading activity.

*Data source: Yahoo Finance via the yfinance Python library. The ticker list was retrieved from Wikipedia. The exact price-data snapshot date should be added once verified.*

## Tools and Technologies

- Python
- Google colab
- Pandas and NumPy
- Matplotlib and Seaborn
- yfinance
- Scikit-learn
- SciPy

## Methodology

### 1. Data Collection and Preparation
Collected historical stock prices and trading volumes, followed by data validation, missing-value checks and date alignment.

### 2. Risk–Return Analysis
Calculated mean weekly returns and beta using the S&P 500 as the market benchmark.

### 3. RFM Analysis
Developed an adapted RFM model:
- **Recency:** Days since the latest unusual-volume event.
- **Frequency:** Number of unusual-volume events in the latest 60 trading sessions.
- **Monetary:** Approximate traded value over the latest 60 sessions.

### 4. Clustering
Applied two clustering algorithms:
- Ward Agglomerative Clustering
- K-Means Clustering

Both were evaluated using silhouette scores, cluster profiles and ARI.

### 5. Sensitivity Analysis
Removed Monetary and repeated Ward clustering to evaluate how much it contributed to the RFM segmentation.

## Key Findings

- The analysis identified two main clusters in both risk–return and RFM feature spaces.
- K-Means achieved silhouette scores of 0.387 for RR and 0.424 for RFM.
- Ward clustering achieved silhouette scores of 0.340 for RR and 0.369 for RFM.
- Risk–return clusters differed in historical returns and market beta.
- RFM clusters mainly differed in unusual-volume activity.
- Removing Monetary produced an ARI of 0.923 against the full RFM solution, suggesting that Recency and Frequency retained most of the original grouping.

## Visualisations

The project includes:
- Weekly return and beta analysis
- RFM feature distributions
- Correlation heatmaps
- Hierarchical clustering dendrograms
- Silhouette score comparisons
- PCA cluster visualisations
- Sector composition charts

## Repository Structure

```text
sp500-stock-segmentation/
│
├── data/
├── outputs/
├── CRM_CW1_final.ipynb
├── requirements.txt
├── README.md
└── 
```


## Limitations

The analysis uses historical data and a later S&P 500 constituent list, which may introduce survivorship bias. Clustering results show weak-to-moderate separation, and the adapted RFM measures describe trading activity rather than predicting future stock performance.

## Disclaimer

This project is for educational and analytical purposes only. It does not provide investment advice or predict future stock returns.
