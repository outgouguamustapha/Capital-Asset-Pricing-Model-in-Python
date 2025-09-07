# Capital Asset Pricing Model (CAPM) Analysis in Python 📈

A comprehensive financial analysis project that demonstrates the calculation of **CAPM, Beta, Expected Return, and Sharpe Ratio** for **Procter & Gamble (PG)** using Python. This project uses the **S&P 500 index (^GSPC)** as the market benchmark and covers the period **2012–2016**.

![Python](https://img.shields.io/badge/python-v3.7+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Status](https://img.shields.io/badge/status-active-success.svg)

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Theoretical Background](#-theoretical-background)
- [Key Features](#-key-features)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Workflow](#-project-workflow)
- [Results & Interpretation](#-results--interpretation)
- [Project Structure](#-project-structure)
- [Assumptions & Limitations](#-assumptions--limitations)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

The Capital Asset Pricing Model (CAPM) is a fundamental financial model that describes the relationship between systematic risk and expected return for assets. This project implements CAPM analysis from scratch using Python, providing insights into:

- **Risk Assessment**: How volatile is PG compared to the overall market?
- **Expected Returns**: What return should investors expect based on risk?
- **Risk-Adjusted Performance**: How well does PG perform relative to its risk?

---

## 📚 Theoretical Background

### Capital Asset Pricing Model (CAPM)
The CAPM formula calculates the expected return of an asset based on its risk relative to the market:

```
E(Ri) = Rf + βi × (E(Rm) - Rf)
```

Where:
- **E(Ri)** = Expected return of asset i
- **Rf** = Risk-free rate
- **βi** = Beta of asset i (systematic risk)
- **E(Rm)** = Expected market return

### Beta (β)
Beta measures an asset's volatility relative to the overall market:
- **β = 1**: Asset moves with the market
- **β > 1**: Asset is more volatile than the market
- **β < 1**: Asset is less volatile than the market

### Sharpe Ratio
The Sharpe ratio measures risk-adjusted returns:
```
Sharpe Ratio = (E(R) - Rf) / σ
```

---

## ✨ Key Features

- **Real-time Data Fetching**: Automatically downloads historical stock data from Yahoo Finance
- **Comprehensive Risk Analysis**: Calculates multiple risk metrics including beta and volatility
- **Statistical Computations**: Implements covariance matrix and variance calculations
- **CAPM Implementation**: Full implementation of the Capital Asset Pricing Model
- **Performance Metrics**: Calculates Sharpe ratio for risk-adjusted performance evaluation
- **Clean Code Structure**: Well-documented and modular Python code

---

## 🛠️ Installation

### Prerequisites
- Python 3.7 or higher
- pip package manager

### Clone the Repository
```bash
git clone https://github.com/yourusername/Capital-Asset-Pricing-Model-in-Python.git
cd Capital-Asset-Pricing-Model-in-Python
```

### Install Dependencies
```bash
pip install -r requirements.txt
```

### Required Packages
```txt
numpy>=1.19.0
pandas>=1.2.0
pandas-datareader>=0.9.0
yfinance>=0.1.63
jupyter>=1.0.0
matplotlib>=3.3.0
seaborn>=0.11.0
scipy>=1.6.0
```

---

## 🚀 Usage

### Quick Start
1. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook CAPM.ipynb
   ```

2. **Run All Cells**: Execute the notebook cells sequentially to perform the complete analysis

3. **Customize Analysis**: Modify the following parameters in the notebook:
   ```python
   # Time period
   start = dt(2012, 1, 1)
   end = dt(2016, 12, 31)
   
   # Stock ticker (change to analyze different stocks)
   tickers = ['PG', '^GSPC']
   
   # Risk-free rate and market risk premium
   rf = 0.025      # 2.5% annual risk-free rate
   rm_rf = 0.05    # 5% market risk premium
   ```

### Analyzing Different Stocks
To analyze a different stock, simply change the ticker symbol:
```python
tickers = ['AAPL', '^GSPC']  # For Apple Inc.
tickers = ['MSFT', '^GSPC']  # For Microsoft Corp.
```

---

## 🔄 Project Workflow

### 1. **Data Collection**
- **Source**: Yahoo Finance via `yfinance` and `pandas_datareader`
- **Assets**: PG (Procter & Gamble) and ^GSPC (S&P 500 as market proxy)
- **Period**: January 2012 – December 2016 (5 years of daily data)

### 2. **Return Calculation**
- **Method**: Daily logarithmic returns
- **Formula**: 
  ```
  rt = ln(Pt / Pt-1)
  ```
- **Advantage**: Log returns are time-additive and normally distributed

### 3. **Risk Metrics Computation**
- **Covariance Matrix**: Measures how PG returns move with market returns
- **Variance**: Measures market volatility
- **Annualization**: Multiply by 250 trading days per year

### 4. **Beta Estimation**
- **Formula**: 
  ```
  β = Cov(RPG, RM) / Var(RM)
  ```
- **Interpretation**: Measures PG's systematic risk relative to the market

### 5. **Expected Return (CAPM)**
- **Application**: Uses CAPM formula with estimated beta
- **Components**: Risk-free rate + Beta × Market risk premium

### 6. **Risk-Adjusted Performance**
- **Sharpe Ratio**: Measures return per unit of risk
- **Comparison**: Enables comparison with other investments

---

## 📊 Results & Interpretation

### Key Findings (2012–2016 Analysis)

| Metric | Value | Interpretation |
|--------|-------|----------------|
| **Beta (β)** | 0.616 | PG is **38% less volatile** than the market. It's a defensive stock. |
| **Expected Return** | 5.58% | Based on CAPM, investors should expect 5.58% annual return from PG. |
| **Sharpe Ratio** | 0.216 | Positive but moderate risk-adjusted performance. |
| **Market Variance** | 0.0164 | S&P 500 annual variance during the period. |
| **Covariance** | 0.0101 | Positive correlation between PG and market returns. |

### Investment Insights
- **Low Risk Profile**: PG's beta of 0.616 indicates it's a defensive stock suitable for risk-averse investors
- **Stable Returns**: Lower volatility suggests more predictable returns
- **Market Correlation**: Positive covariance shows PG generally moves in the same direction as the market, but with less magnitude

---

## 📁 Project Structure

```
Capital-Asset-Pricing-Model-in-Python/
│
├── CAPM.ipynb              # Main analysis notebook
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation
```

---

## ⚠️ Assumptions & Limitations

### CAPM Assumptions
1. **Efficient Markets**: All investors have access to the same information
2. **Single Period**: Analysis assumes a single investment period
3. **Normal Distribution**: Returns are normally distributed
4. **Constant Risk-Free Rate**: Risk-free rate remains constant
5. **No Transaction Costs**: Ignores brokerage fees and taxes

### Project Limitations
- **Historical Data Only**: Past performance doesn't guarantee future results
- **Single Stock Analysis**: Limited to one stock (PG) in current implementation
- **Fixed Time Period**: Analysis covers only 2012-2016
- **Market Proxy**: Uses S&P 500 as market proxy (may not represent entire market)
- **Static Parameters**: Risk-free rate and market premium are assumed constant

---

## 🚀 Future Enhancements

### Immediate Improvements
- [ ] **Data Visualization**: Add interactive plots for stock prices, returns, and regression analysis
- [ ] **Multiple Stock Analysis**: Extend to analyze portfolios of multiple stocks
- [ ] **Statistical Validation**: Add hypothesis testing for beta significance
- [ ] **Confidence Intervals**: Implement confidence intervals for all estimates

### Advanced Features
- [ ] **Rolling Beta Analysis**: Calculate time-varying beta coefficients
- [ ] **Sector Comparison**: Compare stocks across different sectors
- [ ] **Portfolio Optimization**: Implement Markowitz portfolio theory
- [ ] **Risk Attribution**: Decompose total risk into systematic and idiosyncratic components
- [ ] **Backtesting Framework**: Test CAPM predictions against actual returns

### Technical Enhancements
- [ ] **Web Dashboard**: Create Streamlit/Dash web interface
- [ ] **Automated Reporting**: Generate PDF reports automatically
- [ ] **API Integration**: Real-time data updates
- [ ] **Database Integration**: Store historical analyses
- [ ] **Docker Containerization**: Easy deployment and reproducibility

### Additional Analysis
- [ ] **Fama-French Three-Factor Model**: Extend beyond simple CAPM
- [ ] **Value at Risk (VaR)**: Add downside risk measures
- [ ] **Monte Carlo Simulation**: Simulate future price paths
- [ ] **Regime Detection**: Identify different market regimes

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

### How to Contribute
1. **Fork the Repository**
2. **Create a Feature Branch**: 
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit Your Changes**: 
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
4. **Push to Branch**: 
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request**

### Contribution Ideas
- Add new financial metrics
- Improve data visualization
- Optimize calculation performance
- Add unit tests
- Improve documentation
- Fix bugs or issues

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Contact & Support

- **Author**: [OUTGOUGUA MUSTAPHA]
- **Email**: mustaphaoutgougua@gmail.com
- **LinkedIn**: [LinkedIn Profile](https://www.linkedin.com/in/mustapha-outgougua/)
- **Project Link**: [https://github.com/outgouguamustapha/Capital-Asset-Pricing-Model-in-Python](https://github.com/outgouguamustapha/Capital-Asset-Pricing-Model-in-Python)

---

## 🙏 Acknowledgments

- **Yahoo Finance** for providing free financial data
- **Python Community** for excellent financial libraries
- **Academic Research** on CAPM and portfolio theory
- **Open Source Contributors** who made the underlying libraries possible

---

## 📚 References

1. Sharpe, W. F. (1964). "Capital asset prices: A theory of market equilibrium under conditions of risk"
2. Markowitz, H. (1952). "Portfolio Selection"
3. Fama, E. F., & French, K. R. (1993). "Common risk factors in the returns on stocks and bonds"

---

*Happy Analyzing! 📈*
