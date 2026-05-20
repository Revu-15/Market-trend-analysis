# Market-trend-analysis

# 🚀  Market Trend Analysis Project

A beginner-friendly machine learning project that predicts stock market trends using technical indicators and advanced ML algorithms.

📄 **Project Report**: [View Report]()  
📊 **Live Dashboard**: [Launch Dashboard](https://market-trend-analysis-revanth-15.streamlit.app/)  
🎥 **Video Demo & Presentation**: [Watch Demo](https://drive.google.com/file/d/19QGGDt-TkzHKs2vPAEZne37RVUcLPhKG/view?usp=sharing)

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Quick Start](#-quick-start)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Model Performance](#-model-performance)
- [Technical Details](#-technical-details)
- [Disclaimer](#-disclaimer)

## 🎯 Overview

This project demonstrates how to build an end-to-end AI system for stock market trend prediction. It's designed for beginners but includes advanced techniques that make it suitable for learning and real-world applications.

**What it does:**
- Collects real-time stock data from Yahoo Finance
- Engineers 40+ technical indicators (RSI, MACD, Bollinger Bands, etc.)
- Trains multiple ML models (Random Forest, XGBoost, Logistic Regression)
- Provides an interactive web dashboard for predictions
- Achieves 60%+ accuracy on market trend prediction

**Target Audience:** Students, beginners in ML/Finance, and anyone interested in algorithmic trading

## ✨ Features

### 🔄 Data Collection
- **Real-time data** from Yahoo Finance API
- **Multiple stocks** support (AAPL, GOOGL, MSFT, AMZN, TSLA)
- **Flexible time periods** (1Y, 2Y, 5Y, Max)
- **Automatic data cleaning** and validation

### 🔧 Feature Engineering
- **40+ Technical Indicators**:
  - Moving Averages (SMA, EMA)
  - Momentum (RSI, ROC, Stochastic)
  - Volatility (Bollinger Bands, ATR)
  - Volume (OBV, VPT, PVT)
  - Price Action patterns

### 🤖 Machine Learning
- **Multiple Models**: Random Forest, XGBoost, Logistic Regression
- **Automatic Model Selection**: Best model chosen by cross-validation
- **Class Balancing**: Handles imbalanced market data
- **Feature Importance**: Understand which indicators matter most

### 📊 Interactive Dashboard
- **Real-time Predictions**: Live market trend forecasting
- **Beautiful Visualizations**: Interactive charts with Plotly
- **Model Insights**: Feature importance and performance metrics
- **User-friendly Interface**: Built with Streamlit

## 🚀 Quick Start

### 1. Clone & Setup
```bash
git clone https://github.com/Revu-15/market-trend-analysis
cd ai-market-trend-analysis
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### 2. Collect Data (Week 1)
```bash
python data_collector.py
```
This downloads 5 years of stock data for major tech companies.

### 3. Engineer Features (Week 2)
```bash
python feature_engineer.py
```
Creates 40+ technical indicators from raw price data.

### 4. Train Models (Week 3)
```bash
python model_trainer.py
```
Trains and evaluates multiple ML models, saves the best one.

### 5. Launch Dashboard (Week 4)
```bash
streamlit run streamlit_app/app.py
```
Opens interactive web dashboard at `http://localhost:8501`

## 📁 Project Structure

```
ai-market-trend-analysis/
│
├── 📂 data/
│   ├── raw/                 # Raw stock data (CSV files)
│   └── features/            # Processed data with technical indicators
│
├── 📂 models/
│   ├── *.pkl               # Trained ML models
│   ├── scaler.pkl          # Feature scaler
│   ├── model_metadata.json # Model performance info
│   └── feature_importance.csv
│
├── 📂 notebooks/           # Jupyter notebooks for exploration
│   └── 01_data_exploration.ipynb
│
├── 📂 streamlit_app/       # Interactive dashboard
│   └── app.py
│
├── 📂 src/                 # Core modules
│   ├── data_collector.py   # Stock data collection
│   ├── feature_engineer.py # Technical indicators
│   └── model_trainer.py    # ML model training
│
├── 📋 requirements.txt     # Python dependencies
├── 📚 README.md           # This file
└── 🚀 setup.py            # Installation script
```

## 🛠 Installation

### Prerequisites
- Python 3.8+ (recommended: 3.9 or 3.10)
- Git
- Internet connection (for data fetching)

### Step-by-Step Installation

1. **Clone the repository**
```bash
git clone https://github.com/23f2000792/ai-market-trend-analysis
cd ai-market-trend-analysis
```

2. **Create virtual environment**
```bash
python -m venv venv
```

3. **Activate virtual environment**
```bash
# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

4. **Install dependencies**
```bash
pip install -r requirements.txt
```

## 📊 Model Performance

### Default Performance (5-year data, 5 stocks)

| Model | Accuracy | F1-Score | Training Time | Notes |
|-------|----------|----------|---------------|-------|
| **Random Forest** | 64.2% | 0.639 | 2.3s | Most balanced performance |
| **XGBoost** | 66.1% | 0.658 | 5.7s | Highest accuracy |
| **Logistic Regression** | 61.8% | 0.612 | 0.8s | Fastest training |

### Key Metrics
- **Precision**: 62-68% across all classes
- **Recall**: 58-71% (varies by market condition)
- **Cross-validation**: 5-fold CV with stratified sampling
- **Class Balance**: Down(35%), Stable(30%), Up(35%)

### Feature Importance (Top 10)
1. RSI_14 (0.124) - Momentum indicator
2. SMA_Ratio_5_20 (0.089) - Trend strength
3. MACD_Histogram (0.076) - Momentum divergence
4. BB_Position (0.071) - Volatility position
5. Volume_Ratio (0.068) - Volume confirmation
6. Price_to_SMA50 (0.063) - Long-term trend
7. ATR (0.059) - Volatility measure
8. Stoch_K (0.057) - Overbought/oversold
9. ROC_10 (0.054) - Price momentum
10. EMA_12 (0.051) - Short-term trend

## 🔬 Technical Details

### Data Pipeline
1. **Collection**: Yahoo Finance API → Raw OHLCV data
2. **Cleaning**: Handle missing values, outliers, stock splits
3. **Feature Engineering**: Create 40+ technical indicators
4. **Preprocessing**: Scale features, encode targets
5. **Training**: Multiple models with cross-validation
6. **Evaluation**: Comprehensive metrics and validation

### Technical Indicators Implemented

#### Trend Indicators
- Simple Moving Average (SMA): 5, 10, 20, 50, 200 periods
- Exponential Moving Average (EMA): 12, 26, 50 periods
- Moving Average Ratios and Cross-overs

#### Momentum Indicators
- Relative Strength Index (RSI): 14-period
- Rate of Change (ROC): 5, 10, 20 periods
- MACD: Standard 12-26-9 configuration
- Stochastic Oscillator: %K and %D

#### Volatility Indicators
- Bollinger Bands: 20-period with 2 standard deviations
- Average True Range (ATR): 14-period
- Historical Volatility: 10 and 30-day annualized

#### Volume Indicators
- On Balance Volume (OBV)
- Volume Price Trend (VPT)
- Price Volume Trend (PVT)
- Volume Moving Averages and Ratios

### Model Architecture

#### Random Forest (Default Best)
```python
RandomForestClassifier(
    n_estimators=100,
    max_depth=10,
    min_samples_split=5,
    min_samples_leaf=2,
    random_state=42
)
```

#### XGBoost (Highest Accuracy)
```python
XGBClassifier(
    n_estimators=100,
    max_depth=6,
    learning_rate=0.1,
    random_state=42
)
```

## 📚 Learning Resources
### APIs and Data Sources
- [Yahoo Finance API](https://pypi.org/project/yfinance/)
- [Alpha Vantage](https://www.alphavantage.co/)
- [Quandl](https://www.quandl.com/)

## 🚨 Disclaimer

**IMPORTANT: This project is for educational purposes only.**

- 📚 **Educational Tool**: Designed for learning ML and financial analysis
- ❌ **Not Financial Advice**: Do not use for actual trading decisions
- 📊 **Historical Performance**: Past results don't guarantee future performance
- 🎯 **Accuracy Limitations**: 60-70% accuracy is good for education, not trading
- 💰 **Risk Warning**: Financial markets involve substantial risk of loss
- 👨‍💼 **Professional Advice**: Consult qualified financial advisors for investment decisions

### Legal Notice
The authors and contributors are not responsible for any financial losses incurred from using this software. Always perform your own research and risk assessment before making investment decisions.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Yahoo Finance** for free financial data API
- **Streamlit** for making beautiful web apps simple
- **scikit-learn** for excellent ML library
- **Plotly** for interactive visualizations
- **pandas-ta** for technical analysis indicators

## 📞 Support

- 📧 **Contact**: polamreddyrevanth.82@gmail.com

---
