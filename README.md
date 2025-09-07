# Capital-Asset-Pricing-Model-in-Python
This project demonstrates the calculation of **CAPM, Beta, Expected Return, and Sharpe Ratio** for **Procter & Gamble (PG)** using the **S&P500 index (^GSPC)** as the market benchmark.  
The analysis covers the period **2012–2016**.

---

## 🚀 Project Workflow

1. **Data Collection**
   - Source: Yahoo Finance via `yfinance` + `pandas_datareader`
   - Assets: PG (stock) and ^GSPC (market)

2. **Return Calculation**
   - Daily log returns computed as:  
     \[
     r_t = \ln\left(\frac{P_t}{P_{t-1}}\right)
     \]

3. **Covariance & Variance**
   - Annualized covariance and variance estimated using 250 trading days.

4. **Beta Estimation**
   - \[
     \beta = \frac{\text{Cov}(R_{PG}, R_{M})}{\text{Var}(R_{M})}
     \]
   - Captures PG’s sensitivity to market movements.

5. **Expected Return (CAPM)**
   - Using the Capital Asset Pricing Model:  
     \[
     E(R_{PG}) = R_f + \beta \times (R_m - R_f)
     \]

6. **Sharpe Ratio**
   - Risk-adjusted return:  
     \[
     Sharpe = \frac{E(R) - R_f}{\sigma}
     \]

---

## 📊 Key Results (2012–2016)

- **PG Beta:** `0.616` → less volatile than the market  
- **Expected Return (CAPM):** `5.58%`  
- **Sharpe Ratio:** `0.216` → low but positive risk-adjusted performance  

---

## 🛠️ Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
