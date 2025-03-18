# University-project
This repository contains various university projects focused on different modules such as quantitative finance and risk analysis. Each project explores theoretical concepts applied to real-world financial and economic data, using Python, R, and statistical modeling techniques.
## Brownian Motion in Finance
Objective: Explore the concept of Brownian motion and its applications in finance, including geometric and fractional Brownian motion. Special focus is given to the Hurst exponent and its role in modeling market behavior.
 Methods:
Introduction to standard Brownian motion (Wiener process) and its properties.
Implementation of geometric Brownian motion (GBM) as a fundamental model for asset prices.
Application of fractional Brownian motion (fBM) and analysis of the Hurst component.
Empirical study using Apple stock price data.
📌 Files available:
📂 Python Notebook – Implementation of GBM. [🔗 View on GitHub](https://github.com/ghazzoul12/University-project/blob/main/GBM.ipynb)
📂 Apple Stock Dataset (CSV) – Historical stock price data. [🔗 View on GitHub](https://github.com/ghazzoul12/University-project/blob/main/AAPL.csv)
📂 Paper on Brownian Motion (PDF) - [🔗 View on GitHub](https://github.com/ghazzoul12/University-project/blob/main/Brownian%20motion)

## Credit and Equity Beta
Objective: Investigate the relationship between credit markets and equity markets, focusing on Credit Default Swaps (CDS) indices such as CDX (North America) and iTraxx (Europe). The project examines CDS beta relative to equity indices and quantifies the sensitivity of investment-grade (IG) and high-yield (HY) CDS spreads.
 Methods:
Understanding CDS indices as tools for hedging and speculation in credit markets.
Computing CDS beta to evaluate how different CDS indices respond to equity market movements.
Comparing Investment-Grade (IG) and High-Yield (HY) CDS beta, highlighting the greater volatility and risk associated with HY.
Key Finding: The beta of CDX IG to CDX HY is 3.33, reinforcing that HY reacts much more aggressively to market fluctuations than IG.
📌 Files available:
📂 Jupyter Notebook – CDS beta calculations. [🔗 View on GitHub](https://github.com/ghazzoul12/University-project/blob/main/Project_Creditandequitybeta.ipynb)
📂 Excel Dataset (XLSX) – Historical CDS data. [🔗 View on GitHub](https://github.com/ghazzoul12/University-project/blob/main/HistoricalIndices.xlsx)

## Adaptive Conformal Inference (ACI) & Aggregated Adaptive Conformal Inference (AgACI) in Finance
Objective: Apply Conformal Prediction and Adaptive Conformal Inference (ACI) to financial time series data, particularly in volatility modeling and risk estimation. This project extends these methods using eGARCH models and explores the benefits of Aggregated Adaptive Conformal Inference (AgACI).
 Methods:
Conformal Prediction provides prediction intervals based on conformity scores, ensuring reliable uncertainty estimation.
Adaptive Conformal Inference (ACI) dynamically updates confidence intervals based on past errors, improving its adaptability to financial data.
eGARCH models are implemented for volatility forecasting, with ACI used to refine prediction accuracy.
Aggregated ACI (AgACI) optimally combines multiple models with different step size parameters (γ) using Bayes Optimal Aggregation (BOA), enhancing performance.
Key Finding: AgACI outperforms traditional eGARCH models, providing more stable and adaptive prediction intervals for financial markets.
📌 Files available:
📜 R Markdown File (.Rmd) – Implementation and analysis. [🔗 View on GitHub](https://github.com/ghazzoul12/University-project/blob/main/R%20markdown%20file%20for%20ACI%20AgACI)
📜 HTML file: [🔗 View on GitHub](https://github.com/ghazzoul12/University-project/blob/main/ACI%20AgACI)




