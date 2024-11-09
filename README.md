# Algorithmic Trading Strategies

This project explores multiple algorithmic trading strategies across various asset classes and timeframes, leveraging machine learning techniques and quantitative analysis. The primary goal is to develop robust and profitable trading strategies by combining financial data with technical indicators, portfolio optimization techniques, and social sentiment analysis.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Trading Strategies](#trading-strategies)
    - [Unsupervised Learning Trading Strategy](#unsupervised-learning-trading-strategy)
    - [Twitter Sentiment Trading Strategy](#twitter-sentiment-trading-strategy)
    - [Intraday GARCH Trading Strategy](#intraday-garch-trading-strategy)
3. [Requirements](#requirements)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Contributing](#contributing)
7. [License](#license)

---

## Project Overview

The project includes the development and testing of three distinct trading strategies:
1. **Unsupervised Learning Strategy** - Applying clustering and portfolio optimization on S&P 500 stocks.
2. **Twitter Sentiment Strategy** - Analyzing Twitter sentiment data for NASDAQ stocks.
3. **Intraday GARCH Strategy** - Using GARCH modeling combined with technical indicators to inform intraday positions.

## Trading Strategies

### 1. Unsupervised Learning Trading Strategy

The goal of this strategy is to use unsupervised learning techniques to cluster S&P 500 stocks, focusing on volatility, sentiment, and technical indicators. Based on our hypothesis, we select specific clusters of stocks each month, then create a portfolio optimized to maximize the Sharpe ratio.

#### Key Components
- **Features and Technical Indicators:**
  - **Garman-Klass Volatility** - An estimator of stock price volatility.
  - **Relative Strength Index (RSI)** - A momentum indicator.
  - **Bollinger Bands** - Volatility bands to gauge price action.
  - **Average True Range (ATR)** - Measures market volatility.
  - **Moving Average Convergence Divergence (MACD)** - Trend-following indicator.
  - **Dollar Volume** - Calculated as volume multiplied by price.
  
- **Cluster Selection and Portfolio Construction:**
  - Each month, we select stocks from clusters that align with our strategy hypothesis.
  - For example, stocks with RSI clustered around a 70 centroid may continue to outperform the following month. Thus, stocks in **Cluster 3** (RSI ~70) are prioritized.
  - Portfolio weights are optimized using the **Efficient Frontier** to maximize the Sharpe ratio, with diversification via weight constraints.

### 2. Twitter Sentiment Trading Strategy

This strategy leverages social media sentiment by analyzing Twitter data for NASDAQ stocks. Stocks are ranked based on engagement metrics and sentiment score, then selected for investment based on positive sentiment performance against the **QQQ** benchmark.

#### Key Components
- **Data Collection** - Gather sentiment data and engagement metrics for NASDAQ stocks from Twitter.
- **Sentiment Analysis** - Rank stocks based on sentiment scores and engagement.
- **Benchmark Comparison** - Compare performance of selected stocks against the **QQQ** ETF.

### 3. Intraday GARCH Trading Strategy

The **Intraday GARCH Strategy** incorporates a GARCH model to analyze and predict price volatility intraday. Combined with technical indicators, this model helps capture both daily and intraday signals to identify potential high-return positions.

#### Key Components
- **GARCH Model** - Generalized Autoregressive Conditional Heteroskedasticity model, used to estimate and predict volatility.
- **Intraday Technical Indicators** - Additional indicators to inform short-term decisions, enhancing position-taking based on volatility insights.

## Requirements

- Python 3.8+
- Libraries: 
  - `numpy`, `pandas`, `scikit-learn`, `yfinance`, `arch`, `matplotlib`, `seaborn`
  - For Twitter Sentiment Strategy: `tweepy`, `vaderSentiment`

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/algorithmic-trading-strategies.git
    cd algorithmic-trading-strategies
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

To run each strategy, you can execute the respective scripts in the repository. Detailed instructions are available in the strategy-specific directories. Here’s a quick start guide:

```bash
# Example command for the Unsupervised Learning Trading Strategy
python unsupervised_learning_strategy.py --date '2024-10-01'

# Example command for Twitter Sentiment Trading Strategy
python twitter_sentiment_strategy.py --date '2024-10-01'

# Example command for Intraday GARCH Trading Strategy
python intraday_garch_strategy.py --date '2024-10-01'
```

## Contributing

Contributions are welcome! Please open an issue to discuss potential changes or improvements.

## License

This project is licensed under the MIT License.
