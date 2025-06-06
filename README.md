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
- 📂 Python Notebook – Implementation of GBM. [View](https://github.com/ghazzoul12/University-project/blob/main/Brownian_Motion/GBM.ipynb)
- 📂 Apple Stock Dataset (CSV) – Historical stock price data.  [Dataset](https://github.com/ghazzoul12/University-project/blob/main/Brownian_Motion/AAPL.csv)
- 📂 Paper on Brownian Motion (PDF)[Paper](https://github.com/ghazzoul12/University-project/blob/main/Brownian_Motion/Brownian%20motion)

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
- 📂 Jupyter Notebook – CDS beta calculations.[🔗 Collab](https://github.com/ghazzoul12/University-project/blob/main/Credit_Equity_Beta/Project_Creditandequitybeta.ipynb)
- 📂 Excel Dataset (XLSX) – Historical CDS data. [Dataset](https://github.com/ghazzoul12/University-project/blob/main/Credit_Equity_Beta/HistoricalIndices.xlsx) 

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
- 📜 R Markdown File (.Rmd) – Implementation and analysis. [R markdown](https://github.com/ghazzoul12/University-project/blob/main/ACI_AgACI/R%20markdown%20file%20for%20ACI%20AgACI)
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
- 📜 R Markdown File (.Rmd) – Implementation and analysis.  [R markdown](https://github.com/ghazzoul12/University-project/blob/main/Happiness_Score/Happiness%20score%20Project)
- 📜 HTML Report – Final project report. 
- 📂 Dataset (CSV) – Happiness Score data. [Dataset](https://github.com/ghazzoul12/University-project/blob/main/Happiness_Score/data%20for%20Happiness%20score.csv)


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
- 📂 Code in a PDF Format – Implementation of models.[🔗 View on GitHub](https://github.com/ghazzoul12/University-project/blob/main/Stock_Prediction/The%20full%20code%20for%20Stockprice%20prediction.pdf)

  ---
## Principal Component Analysis (PCA) 
📌 Objective:
Apply Principal Component Analysis (PCA) to a vehicle dataset to reduce feature dimensionality while preserving variance.
Evaluate the effectiveness of PCA by comparing K-Nearest Neighbors (KNN) classification performance before and after dimensionality reduction.

📌 Methods:

-Standardization of features to ensure equal scaling.
-Application of PCA to identify principal components and retain maximum variance.
-Visualization techniques including both 2D and 3D scatter plots.
-Pairplots for component interactions.
-KNN model evaluation with cross-validation before and after dimensionality reduction.



📌 Files available:

📂 Python Notebook – PCA [🔗 Collab](https://github.com/ghazzoul12/University-project/blob/main/PCA_Project/PCA_project.ipynb)

