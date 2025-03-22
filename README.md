# Quantitative Financial Analytics: Decoding Stock Returns Through Earnings, Macro, and Sentiment Analysis

### 📋 Project Brief

This project conducted an in-depth analysis of stock market behaviour for major tech companies (Apple, Google, and NVIDIA) to identify opportunities for trading strategies around earnings announcements. Using Python, advanced statistical methods, and machine learning, our team delivered actionable insights that can drive enhanced trading decision-making by understanding the relationships between stock price movements, earnings announcements, macroeconomic conditions, and news sentiment.

### 🎯 Business Objectives

The analysis addressed key business needs:

- Understanding stock price movements before and after earnings announcements
- Identifying the impact of key financial metrics on stock performance
- Analysing macroeconomic influences on earnings outcomes and stock prices
- Determining the role of news sentiment in market reactions

### Project Overview:
<div>
  <table>
    <tr align="center">
      <th align="center">⏱️ Duration</th>      
      <th align="center">🏆 Grade</th>
      <th align="center">🛠️ Tools</th>
      <th align="center">📊 Datasets</th>
    </tr>
    <tr>
      <td align="center"><b>6 Weeks</b></td>
      <td align="center">
        <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
        <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
        <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
        <img src="https://img.shields.io/badge/finBERT-4169E1?style=for-the-badge&logo=python&logoColor=white">
      </td>
      <td><b>80% (Distinction)<b></td>  
      <td align="center">
         <b>20+ years of stock data<br>
         <b>5 macroeconomic indicators<br>
         <b>1,423</b> news articles
      </td>
    </tr>
  </table>
</div>


### 🔍 Analytical Methodology

#### Data Sources and Collection

| Data Category | Source | Time Period | Key Metrics |
|---------------|--------|-------------|------------|
| <b>Stock Price Data</b> | Yahoo Finance API | 2000-2024 | OHLCV (Open, High, Low, Close, Volume) |
| <b>Financial Metrics</b> | Financial Modeling Prep (FMP API) | 2000-2024 | Earnings, Revenue, Key Financial Ratios |
| <b>Macroeconomic Indicators</b> | Federal Reserve Economic Data (FRED API) | 2000-2024 | GDP, Inflation, Unemployment, Federal Debt, Treasury Yields |
| <b>News Sentiment</b> | NY Times Articles (Client provided Data) | 2019-2024 | 1,423 articles after cleanup |

<div align="center">
  <img src="https://github.com/user-attachments/assets/22065cf7-93c4-424f-8bd0-fd7c733a1e73" width="100%"/>
  <p><em>Data Ingestion from Different Opensource APIs</em></p>
</div>

#### Feature Engineering

We created 90+ derived features across the following categories:

| Feature Category | Examples |
|------------------|----------|
| <b>Stock Metrics</b> | Daily Returns, Balance of Power (BOP), Pre/Post Announcement Returns, Price Coefficient of Variation |
| <b>Financial Indicators</b> | EPS Surprise, Revenue Surprise, Standardized Surprise Scores, Profit Margins, ROE, ROA |
| <b>Macro Indicators</b> | GDP Growth Rates (QoQ/YoY), Federal Debt Change, CPI Changes, Treasury Yield Movements |
| <b>Temporal Features</b> | TTM Metrics, QoQ Changes, YoY Growth Rates |
| <b>Sentiment Scores</b> | FinBERT Composite Scores, Company/Macro Sentiment Classification |

#### Analysis Components

| Analysis Type | Key Methodologies | Analytical Techniques | Outcomes |
|---------------|-------------------|------------------------|----------|
| **Earnings Event Analysis** | • Event study framework<br>• Multiple return windows (1-5 days)<br>• Cross-sectional surprise analysis | • Winsorization of extreme values<br>• Segmentation by surprise direction<br>• Temporal decomposition (2000-2024) | • **2-3 day** optimal reaction window<br>• **~0.3** correlation between EPS surprise and returns<br>• Surprise threshold identification |
| **Macroeconomic Factor Analysis** | • Correlation heatmaps<br>• Time-series decomposition<br>• Multi-factor regression<br>• Company-specific correlations | • Rate-of-change calculations (QoQ, YoY)<br>• Rolling window correlations<br>• Comparative macro sensitivity analysis | • Unique company-macro sensitivity maps<br>• Identified key indicators by company<br>• Quantified revenue vs. macro impact |
| **News Sentiment Analysis** | • NLP-based sentiment extraction<br>• Rule-based article classification<br>• **5-day** pre/post-publication windows | • **FinBERT** financial sentiment scoring<br>• Publishing date Event-study • Sentiment-return correlation analysis | • Company-specific sentiment responses<br>• Negative news recovery patterns<br>• **Pre/post-earnings** sentiment **drift detection** |
| **Trading Strategy Development** | • Signal classification (Buy/Sell/Hold)<br>• Random Forest ensemble modeling<br>• Multi-factor integration<br>• Backtesting framework | • Company-specific thresholds<br>• Hyperparameter optimization<br>• Feature importance ranking<br>• Performance metrics calculation | • **6.5-12.7% average return** per trade<br>• **83-95%** signal precision<br>• Realized cumulative returns **>20x**<br>• Feature importance hierarchies |


### 🗝️ Key Insights and Results

#### Earnings Analysis

- EPS Surprise positively correlates with post-announcement returns (correlation ~0.3)
- Market reaction to surprises **strongest within 2-3 days** after announcement
- **Pre-announcement momentum** (BOP) shows positive correlation with post-announcement returns

<div align="center">
  <img src="https://github.com/user-attachments/assets/2895f387-580a-4b58-862e-1cfa8cdfe2ac" width="100%"/>
  <p><em>EPS Surprise vs Post announcement 2-day returns</em></p>
</div>

#### Macroeconomic Analysis

Each company showed unique macro sensitivity profiles:

| Company | Primary Macro Correlations |
|---------|----------------------------|
| **Apple**   | Federal Debt, Real GDP     |
| **Google**  | Real GDP, CPI, Treasury Yields |
| **Nvidia**  | Real GDP, Treasury Yields, Unemployment |

**Revenue growth** consistently showed **stronger impact** on returns *than* **macroeconomic factors** for these high-growth tech companies.

<div align="center">
  <img src="https://github.com/user-attachments/assets/e39cf5b8-40bc-4a7e-8eeb-88b00dc79f0f" width="100%"/>
  <p><em>Combined Correlation Heatmap - Returns vs Revenue and Macro factors</em></p>
</div>

#### Sentiment Analysis

News sentiment analysis revealed distinct patterns:

| Company | Sentiment Response Pattern |
|---------|----------------------------|
| **Apple**   | Recovers from negative news within 3 days; positive drift otherwise (~1% in 5 days) |
| **Google**  | Most stable to sentiment (returns within 1% window); acts as safe-haven during macro uncertainty |
| **Nvidia**  | Highest sentiment sensitivity (±2-3% fluctuations); strong positive reaction to macro negativity |

Pre-earnings sentiment shows consistent optimistic bias with post-announcement sentiment typically declining.

<div align="center">
  <img src="https://github.com/user-attachments/assets/e07f3ac3-7384-4015-8b07-8a0c00556073" width="100%"/>
  <p><em>Example of Event Study Analysis chart - Apple for Stock sentiment</em></p>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/6e251f3f-b42d-4d4f-a010-e45109d17e88" width="100%"/>
  <p><em>Sentiment and Stock-price Trend around Earnings Announcements</em></p>
</div>

#### Trading Strategy Performance

| Company | Avg. Return per Deal | Max Drawdown | Cumulative Return | Precision |
|---------|---------------------|--------------|-------------------|-----------|
| AAPL    | 6.5%                | -14.8%       | >20x (51 periods) | 83.3%     |
| GOOGL   | 8.0%                | 0.0%         | >20x (39 periods) | 95.0%     |
| NVDA    | 12.7%               | -6.9%        | ~700% (39 periods)| 88.9%     |


### 🛠️ Technical Implementation

The analysis was implemented using:

- **Data Processing**: Pandas, NumPy
- **Machine Learning**: Scikit-learn,StatsModels,
- **ML Models**: RandomForest, OLS, Binary and Multinomial Logistic Regression
- **NLP**: FinBERT, TextBlob
- **Visualization**: Matplotlib, Seaborn

### 📊 Recommendations

#### Trading Strategy Recommendations

1. **Implement Stock-Specific Models**: Different threshold parameters for each stock (±2% for AAPL, ±5% for GOOGL/NVDA)
2. **Focus on Key Indicators**: 
   - EPS and Revenue Surprises (all stocks)
   - Pre-announcement BOP momentum
   - Company-specific financial metrics (profitability metrics for B2B stocks)
3. **Time-Window Optimization**: 2-day trading window for GOOGL/NVDA, 5-day for AAPL
4. **Risk Management**: Set tighter stop-loss for NVDA due to higher volatility
5. **Sentiment Integration**: Use as supplementary signal, particularly for NVDA

#### Technical Recommendations

1. **Model Validation**: Implement out-of-sample testing across diverse market conditions
2. **Ensemble Approaches**: Test combining multiple models for signal generation
3. **Feature Refinement**: Further customize feature importance by stock
4. **Continuous Learning**: Establish monitoring system to adapt to evolving market dynamics

### 👥 Team

Project by Insight Alchemists Team:
- Hemalatha Nagaraj
- Manasa Chilakapati
- Sagar Varma
- Sujith Kumaar K C
- Yuliya Pauzunova
