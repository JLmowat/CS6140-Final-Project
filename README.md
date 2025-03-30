# CS6140-Final-Project
Zindi competitions IBM SkillsBuild Hydropower Climate Optimisation Challenge 

Raw Data:
https://zindi.africa/competitions/ibm-skillsbuild-hydropower-climate-optimisation-challenge/data

https://www.kaggle.com/datasets/muhammadqasimshabbir/ibmskillsbuildhydropowerclimateoptimisationupdated/data

Cleaned Data:
https://drive.google.com/file/d/1OehdbyCkvIytGM6GA2vQ-JrpDqAB96rG/view?usp=sharing


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
