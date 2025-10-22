# Sequential Air Temperature Forecasting using LSTM Layers

## Project Description
This project focuses on predicting air temperature based on the concentration of various particles in the air. Using a time-series dataset from 2017 to 2023, the model leverages Exploratory Data Analysis (EDA) and Long Short-Term Memory (LSTM) deep learning architecture to identify correlations, seasonal patterns, and forecast future temperature trends.

---

## Objective
- Identify relationships between air temperature and multiple particulate matter variables through EDA.  
- Analyze seasonal and temporal patterns across hours, days, weeks, months, and years.  
- Develop an LSTM-based model to predict future air temperatures.  
- Fine-tune the model to understand the impact of different structures and hyperparameters.

---

## Dataset Information
- Time coverage: **July 1, 2017 – March 31, 2023**  
- Data type: Air quality and meteorological measurements  
- Key variables include particulate concentrations (e.g., PM2.5, PM10) and air temperature readings.  
- Missing values were below 20% threshold → handled using **imputation**.  
- Outliers detected and treated using the **winsorizing method** to maintain LSTM robustness.  
- Date column converted from object to **datetime datatype** for time-series analysis.

---

## Methodology

### 1. Exploratory Data Analysis (EDA)
- Reviewed dataset structure, variable types, and missing value proportions.  
- Visualized numerical variable distributions and identified skewness and outliers.  
- Applied winsorization to stabilize extreme values and ensure reliable modeling.  
- Visualized temperature variation across different time granularities to detect seasonality.

### 2. Preprocessing
- Converted date column into proper datetime format.  
- Handled missing values through imputation.  
- Normalized input variables to support deep learning stability.  
- Created lag-based features for sequential dependency learning.  
- Split data into **training**, **validation**, and **testing** sets following temporal order.

### 3. Modeling
**Base Model:**  
- Architecture: LSTM (Long Short-Term Memory)  
- Loss Function: Mean Squared Error (MSE)  
- Optimizer: Adam  
- Activation: ReLU (final output: linear)

### 4. Model Modifications
**Version 1:** Basic LSTM model with one hidden layer.  
**Version 2:** Stacked LSTM layers with dropout regularization to prevent overfitting.  
**Version 3:** Fine-tuned hyperparameters (batch size, learning rate, sequence length) for optimal forecasting accuracy.

Model versions were compared using MSE and trend-matching visualization metrics.

---

## Results and Findings
- LSTM effectively captured both **short-term variations** and **long-term seasonal trends**.  
- Winsorizing and normalization improved training stability and reduced loss.  
- Stacked and fine-tuned models provided smoother and more accurate temperature predictions.  
- Predicted temperature curves closely followed actual readings, indicating good generalization capability.

---

## Conclusion
This project demonstrates how LSTM networks can model complex time-series dependencies between air temperature and particulate matter levels. Through systematic EDA, preprocessing, and model fine-tuning, the approach successfully improved forecasting accuracy while maintaining interpretability of seasonal and temporal air patterns.
