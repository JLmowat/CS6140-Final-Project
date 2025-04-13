### README: CS6140-Final-Project Micro-Hydropower Plants (MHPs) in the Kalam Region


--- 
###### Zindi competitions IBM SkillsBuild Hydropower Climate Optimisation Challenge 

Raw Data:
https://zindi.africa/competitions/ibm-skillsbuild-hydropower-climate-optimisation-challenge/data

https://www.kaggle.com/datasets/muhammadqasimshabbir/ibmskillsbuildhydropowerclimateoptimisationupdated/data

---

#### **Overview of MHPs in the Kalam Region**
Micro-hydropower plants (MHPs) are small-scale, water-based energy generation systems that play a critical role in electrifying remote areas like the Kalam region of Pakistan. These plants provide sustainable and affordable electricity to off-grid communities, empowering local residents and improving quality of life. However, their functionality is heavily dependent on water availability, which fluctuates due to seasonal and meteorological conditions.

Key insights:
- **Seasonal Dependency**: MHPs rely on consistent water flow, which diminishes during winter and spring due to freezing temperatures or insufficient rainfall.
- **Community Impact**: MHPs have transformed lives by powering households, businesses, schools, and healthcare facilities while reducing reliance on costly fossil fuels.
- **Challenges**: Variability in water flow, maintenance issues, and logistical difficulties in transporting parts to remote areas hinder their reliability.

---

#### **Data Preparation**
The dataset for this project contains energy metrics (e.g., kWh) and climate indicators (e.g., temperature, precipitation). However, missing data and seasonal gaps require careful preprocessing.

**Steps for Data Preparation**:
1. **Addressing Missing Values**:
   - Use interpolation methods or domain-specific knowledge to fill minor gaps.
   - For periods with no kWh measurements (e.g., Spring 2024), leave as-is since they represent real-world conditions where energy could not be generated due to low water flow.
2. **Limiting the Dataset**:
   - Exclude data before July 2024 because:
     - Missing Fall 2023 data creates inconsistencies.
     - No kWh measurements exist for Spring 2024 (January–June).
   - Focus on data from **July 2024 onward**, which contains valid kWh values.

---

#### **Why Missing Data Exists**
- The absence of measurements during Spring is not due to errors but reflects real-world limitations of MHPs. Water flow during this period is insufficient for energy generation. This highlights the seasonal dependency of MHP operations.

---

#### **Quick Summary of Models**
1. **ARIMA (AutoRegressive Integrated Moving Average)**:
   - Forecasts based on past values and error terms.
   - Suitable for univariate time series without external predictors.
   - Captures trends and seasonality after differencing.

2. **SARIMAX (Seasonal ARIMA with eXogenous variables)**:
   - Extends ARIMA by incorporating seasonality and external predictors like temperature or precipitation.
   - Ideal for datasets influenced by both internal patterns and external factors.

3. **LGBM (Light Gradient Boosting Machine)**:
   - A machine learning model that uses decision trees for regression tasks.
   - Handles large datasets with non-linear relationships effectively.
   - Outperforms traditional models when multiple features are involved.

---

By focusing on post-July 2024 data and leveraging advanced forecasting models like SARIMAX or LGBM, we can better predict energy load generation while accounting for the unique challenges of MHP operations in the Kalam region.


___


## Model Evaluations 

### ARIMA    Date and kWh 

ARIMA Order (5, 1, 0): Average AIC across all groups: -468.09210823690466
Train RMSE: 8.720043497960631
Submission RMSE: 8.38863658

ARIMA  Order (6, 1, 3): Average AIC across all groups: -482.99233798858523
Train RMSE: 8.720043497960631
Submission RMSE: 8.135190388


ARIMA (7, 0, 2): Average AIC across all groups: -483.5011645121932
Train RMSE: 8.73175993014636
Submission RMSE: 7.079242261

###### **Best Overall**
**ARIMA (7, 1, 3)**
Order (7, 1, 3): Average AIC across all groups: -482.26954080898076
Train RMSE: 8.809956482182832
**Submission RMSE: 6.987309958**

ARIMA Order (7, 1, 4): Average AIC across all groups: -482.9539904169344
Train RMSE: 8.673224757610807
Submission RMSE: 8.860194086

### SARIMAX  Date, kWh, Temp, and other climate factors
SARIMAX order=(0, 0, 0), seasonal_order=(1, 1, 1, 7)
Train validation RMSE = 15.305284056653731
Submission RMSE = 13.88233814
