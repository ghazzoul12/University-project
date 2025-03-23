#  University Projects
This repository contains various university projects focused on different modules such as quantitative finance, risk analysis, and stochastic modeling.  
Each project explores theoretical concepts applied to real-world financial and economic data, using Python, R, and statistical modeling techniques.

---

## Brownian Motion in Finance
📌 Objective:  
Explore the concept of Brownian motion and its applications in finance, including geometric and fractional Brownian motion.  
Special focus is given to the Hurst exponent and its role in modeling market behavior.

📌 Methods:
- Introduction to standard Brownian motion (Wiener process) and its properties.
- Implementation of geometric Brownian motion (GBM) as a fundamental model for asset prices.
- Application of fractional Brownian motion (fBM) and analysis of the Hurst component.
- Empirical study using Apple stock price data.

📌 Files available:
- 📂 Python Notebook – Implementation of GBM. 
- 📂 Apple Stock Dataset (CSV) – Historical stock price data.  
- 📂 Paper on Brownian Motion (PDF)

---

##  Credit and Equity Beta
📌 Objective:  
Investigate the relationship between credit markets and equity markets, focusing on Credit Default Swaps (CDS) indices such as CDX (North America) and iTraxx (Europe).  
The project examines CDS beta relative to equity indices and quantifies the sensitivity of investment-grade (IG) and high-yield (HY) CDS spreads.

📌 Methods:
- Understanding CDS indices as tools for hedging and speculation in credit markets.
- Computing CDS beta to evaluate how different CDS indices respond to equity market movements.
- Comparing Investment-Grade (IG) and High-Yield (HY) CDS beta, highlighting the greater volatility and risk associated with HY.
- Key Finding: The beta of CDX IG to CDX HY is 3.33, reinforcing that HY reacts much more aggressively to market fluctuations than IG.

📌 Files available:
- 📂 Jupyter Notebook – CDS beta calculations.
- 📂 Excel Dataset (XLSX) – Historical CDS data.  

---

##  Adaptive Conformal Inference (ACI) & Aggregated Adaptive Conformal Inference (AgACI) in Finance
📌 Objective:  
Apply Conformal Prediction and Adaptive Conformal Inference (ACI) to financial time series data, particularly in volatility modeling and risk estimation.  
This project extends these methods using eGARCH models and explores the benefits of Aggregated Adaptive Conformal Inference (AgACI).

📌 Methods:
- Conformal Prediction provides prediction intervals based on conformity scores, ensuring reliable uncertainty estimation.
- Adaptive Conformal Inference (ACI) dynamically updates confidence intervals based on past errors, improving its adaptability to financial data.
- eGARCH models are implemented for volatility forecasting, with ACI used to refine prediction accuracy.
- Aggregated ACI (AgACI) optimally combines multiple models with different step size parameters (γ) using Bayes Optimal Aggregation (BOA), enhancing performance.
- Key Finding: AgACI outperforms traditional eGARCH models, providing more stable and adaptive prediction intervals for financial markets.

📌 Files available:
- 📜 R Markdown File (.Rmd) – Implementation and analysis. 
- 📜 HTML File 

---

##  Happiness Score Analysis
📌 Objective:  
Analyze the Happiness Score of 153 countries using economic and social factors from the Gallup World Poll (GWP).  
The study examines key contributors such as GDP per capita, life expectancy, social support, and corruption level.

📌 Methods:
- Load and clean the dataset using R.  
- Conduct exploratory data analysis (EDA) and visualizations.  
- Implement linear regression and LASSO regression for variable selection.  
- Interpret findings and present results in R Markdown and HTML reports.  

📌 Files available:
- 📜 R Markdown File (.Rmd) – Implementation and analysis.  
- 📜 HTML Report – Final project report. 
- 📂 Dataset (CSV) – Happiness Score data. 


  ---

## Stock Price Prediction
📌 Objective:  
Develop predictive models for stock price forecasting using historical stock data.  
The project applies multiple machine learning and deep learning models to improve accuracy.

📌 Methods:
- Data Collection & Preprocessing
- Modeling Approaches:
  - Moving Average Model – Baseline prediction using simple averaging.
  - Linear Regression – Capturing relationships between stock price and time-based features.
  - K-Nearest Neighbors (KNN) – Distance-based stock price prediction.
  - LSTM (Long Short-Term Memory) – Deep learning model for time-series forecasting.
  - Decision Tree Regressor & MLP Regressor – Additional machine learning models for enhanced prediction.

- Evaluation & Results:
  - Compare model RMSE and R² scores.
  - Visualize actual vs predicted prices to assess model accuracy.

📌 File available:
- 📂 Code in a PDF Format – Implementation of models. 


