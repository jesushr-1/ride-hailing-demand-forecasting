## Ride-Hailing Demand Forecasting

Time Series Analysis | Machine Learning | Python

### Project Overview

Sweet Lift Taxi needs to forecast hourly taxi demand at airports to improve driver availability and operational planning.

This project develops and evaluates machine learning models using historical taxi order data to predict demand for the next hour.

### Dataset

The dataset contains 4,416 hourly observations from March to August 2018, including timestamps and taxi order counts.

### Methodology

- Data Preparation: Chronological sorting and hourly resampling.

- Exploratory Data Analysis: Identification of demand trends, recurring patterns, and fluctuations.

- Feature Engineering: Time-based features, 24 hourly lag features, and a 24-hour rolling average.

- Modeling: Linear Regression, Random Forest, CatBoost, and LightGBM.

- Evaluation: Chronological training, validation, and test splits using RMSE.

### Results

| Model | Validation RMSE |
|---|---:|
| Linear Regression | 34.22 |
| Random Forest | 32.58 |
| CatBoost | **31.02** |
| LightGBM | 31.75 |

### Modelo Final

Final Model: CatBoost

Test RMSE: 41.33

Target RMSE: ≤ 48

Outcome: Target achieved.

**Result Interpretation:**

The CatBoost model achieved a test RMSE of 41.33, meeting the project's target of keeping RMSE below 48.

From an operational perspective, this represents a root mean squared prediction error of 41.33 taxi orders per hour. Since RMSE penalizes larger prediction errors more heavily, this value should not be interpreted as the average absolute number of incorrectly predicted orders.

Although the model met the required performance target, there is still room for improvement in supporting driver allocation decisions, particularly during periods of high demand.

**Validation vs. Test Performance:**

The CatBoost model achieved a validation RMSE of 31.02 and a test RMSE of 41.33, representing an increase of approximately 33.2%.

Further error analysis showed that the model struggled particularly during high-demand periods, defined as hours with at least 211.1 taxi orders (the top 10% of observed demand in the test set).

During these periods, RMSE increased to 90.11, compared with 31.56 during normal-demand hours. The mean prediction error (actual minus predicted) was +74.84 orders during high-demand periods, indicating a tendency to underestimate demand.

These findings suggest that demand peaks contribute substantially to prediction errors in the test set and may help explain the difference between validation and test performance. However, the analysis does not establish that demand peaks are the sole cause of this difference.

### Key Findings

CatBoost achieved the lowest validation error and successfully captured general hourly demand patterns.

However, the model tended to underestimate sudden demand spikes, highlighting an opportunity to improve forecasting during peak periods.

### Business Recommendations
- Use demand forecasts to improve driver allocation.
- Maintain additional driver availability during historically high-demand periods.
- Monitor prediction errors and periodically retrain the model with updated data.

### Tools & Technologies

Python | Pandas | NumPy | Matplotlib | Scikit-learn | CatBoost | LightGBM

### Conclusion

This project demonstrates how time series forecasting and machine learning can support operational decision-making in ride-hailing services.