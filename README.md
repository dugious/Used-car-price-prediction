# Used Car Price Prediction: Finding the "Good Deals"

An end-to-end Data Science project that scrapes real-world data from the Vietnamese used car market and builds a Machine Learning model to predict car prices. The ultimate goal is to identify undervalued vehicles ("Good Deals") for potential buyers.

##  Project Objectives
* Build an automated Web Scraping pipeline to collect thousands of used car listings.
* Perform Data Preprocessing, Outlier Removal, and Feature Engineering (e.g., calculating car age, categorizing brand tiers).
* Train and optimize an **XGBoost Regressor** to accurately predict the market value of vehicles based on their specifications.
* Create interactive data visualizations to analyze price discrepancies and market trends.

##  Tech Stack
* **Language:** Python
* **Data Collection (Scraping):** `requests`, `BeautifulSoup`, `Regex`
* **Data Manipulation:** `pandas`, `numpy`
* **Machine Learning:** `scikit-learn`, `XGBoost`
* **Data Visualization:** `Matplotlib`, `Seaborn`, `Plotly`

##  Pipeline Overview

### 1. Data Collection
* The `scraper.py` script automatically navigates through Bonbanh.com listings.
* Utilizes Regular Expressions (Regex) to extract structured features (`Brand_Model`, `Manufacture_Year`, `Price`, `Mileage`) from complex raw text.

### 2. Data Preprocessing & Feature Engineering
* **Outlier Removal:** Filtered out anomalous listings (e.g., fake prices > 10 Billion VND) to ensure model robustness.
* **Feature Creation:** * `Car_Age`: Derived from the manufacture year.
  * `Brand_Tier`: Grouped car brands into distinct tiers (Luxury, High-Retention Standard, Normal Standard) based on market depreciation behaviors.

### 3. Modeling
* Evaluated baseline models (Random Forest) against **XGBoost**.
* Applied Hyperparameter Tuning to the XGBoost model (adjusting `max_depth`, `subsample`, `learning_rate`) to mitigate overfitting and improve prediction accuracy on unseen data.
* **Result:** Achieved a stable R2 Score and minimized Mean Absolute Error (MAE), reflecting true market depreciation patterns.

##  Key Visualizations

* **Interactive Deal Finder:** Plotly scatter plots allow users to hover over data points and identify specific cars being sold below their predicted market value (Listing Price < Predicted Price).
* **Feature Importance:** Visual proof that `Car_Age` and `Brand_Tier` are the most influential factors dictating a vehicle's residual value.

## 🚀 How to Run the Project
1. Clone this repository to your local machine:
   ```bash
   git clone [https://github.com/your-username/UsedCar-Price-Prediction.git](https://github.com/your-username/UsedCar-Price-Prediction.git)
