# Project Description: Black Friday Sales Prediction

## 🚀 Project Overview
The **Black Friday Sales Prediction** project focuses on performing rigorous Exploratory Data Analysis (EDA) and data preprocessing on a large-scale retail transaction dataset. The primary objective is to analyze customer purchasing behavior across diverse demographics and product categories, handle missing data efficiently, and prepare a clean dataset for predictive modeling.

---

## 📊 Dataset Structure & Summary
The dataset comprises retail transaction records capturing customer demographics, product details, and purchase values. 
* **Total Rows (Transactions):** 550,068
* **Total Columns (Features):** 12
* **Key Features:**
  * **Identifiers:** `User_ID`, `Product_ID`
  * **Customer Demographics:** `Gender`, `Age`, `Occupation`, `City_Category`, `Stay_In_Current_City_Years`, `Marital_Status`
  * **Product Attributes:** `Product_Category_1`, `Product_Category_2`, `Product_Category_3`
  * **Target Variable:** `Purchase` (Transaction purchase amount)

---

## 🛠️ Data Cleaning & Preprocessing
To ensure data integrity and optimize performance, the following preprocessing steps were executed:

* **Handling Missing Values:** 
  * `Product_Category_2` contained 173,638 missing values (~31.57%) and `Product_Category_3` contained 383,247 missing values (~69.67%).
  * These missing values were replaced with `0` as a placeholder category to signify the absence of recorded secondary or tertiary product categories without discarding valuable row data.
* **Duplicate Check:** Verified that the dataset contained **0 duplicate rows**.
* **Data Type Optimization:** 
  * Converted `User_ID` to string format.
  * Converted categorical variables (`Gender`, `Age`, `Occupation`, `City_Category`, `Stay_In_Current_City_Years`, `Marital_Status`, `Product_Category_1`, `Product_Category_2`, `Product_Category_3`) to `category` data types, significantly reducing memory usage from ~59.3 MB down to ~25.7 MB.

---

## 📈 Exploratory Data Analysis (EDA) Insights

### 1. Univariate Analysis of Purchases
* **Statistical Summary:** The mean purchase amount is approximately **9,264**, with a standard deviation of **5,023**, ranging from a minimum of **12** to a maximum of **23,961**.
* **Visualizations:** Histograms and KDE plots revealed the distribution shape of transaction amounts, while boxplots highlighted data spread.

### 2. Outlier Detection (IQR Method)
* **First Quartile ($Q_1$):** 5,823.0
* **Third Quartile ($Q_3$):** 12,054.0
* **Interquartile Range ($IQR$):** 6,231.0
* **Thresholds:** Lower limit = $-3,523.5$ | Upper limit = $21,400.5$
* **Findings:** A total of **2,677 outliers** (~0.49% of the dataset) were flagged above the upper limit. Rather than blindly removing them, these extreme values were retained as genuine high-value customer purchases to preserve the integrity and variance of the original transaction records.

### 3. Demographic & Bivariate Analysis
* **Gender Analysis:** Compared transaction volumes and spending behavior between male and female shoppers. Male customers accounted for a significantly higher share of transactions (**414,259** records or **75.31%**) compared to female customers (**135,809** records or **24.69%**), with males also exhibiting higher average and total purchase values.
* **Categorical Distribution:** Analyzed purchasing trends across age brackets (e.g., peak activity observed in the 26–35 age group), city categories (`A`, `B`, `C`), and residency durations.

---

## ✨ Conclusion & Next Steps
This exploratory phase successfully cleaned the raw data, handled missing category hierarchies, optimized memory footprints, and surfaced key customer purchasing patterns. 

**Next Steps for the Project:**
1. **Feature Engineering:** Encode categorical features using techniques like Label Encoding or One-Hot Encoding.
2. **Model Training:** Build regression models (such as Linear Regression, Decision Trees, Random Forests, and XGBoost) to accurately predict customer purchase amounts.
3. **Model Evaluation:** Evaluate model performance using metrics like Root Mean Squared Error (RMSE) to optimize predictive accuracy.
