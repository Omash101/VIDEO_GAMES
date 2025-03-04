# VIDEO_GAMES

![image](https://github.com/user-attachments/assets/a3f29470-c7ff-4076-b691-84efd461413a)


Amdari, a data science team, has been contacted by a video game resale company to forecast monthly sales for the next four months. The goal is to balance supply with demand, ensuring optimal inventory management.

The project involves:
1. Exploratory Data Analysis (EDA):

Identifying overall sales trends.
Detecting seasonality and cyclical patterns.
Analyzing sales by category and platform.
Assessing the impact of holidays and promotions.
Determining the influence of weekdays on sales.

2. Predictive Analytics:

Using ARIMA and ETS (Exponential Smoothing) models for forecasting.
Evaluating model accuracy and selecting the best-fitting model.
Generating four-month sales forecasts.

3. Steps to Solve the Problem
Load and clean the dataset.
Perform EDA (Visualizing trends, seasonality, category/platform impact, etc.).
Apply time series decomposition to extract trend, seasonality, and error components.
Build ARIMA and ETS models, tuning their parameters based on ACF and PACF plots.
Compare model performance using error metrics (e.g., RMSE, MAPE).
Select the best model and generate four-month forecasts.

4. Understanding the Dataset
The dataset contains the following columns:

Category: The genre of the video game.
Month: The date (first of each month).
Monthly Sales: Total sales in that month.
Year: Extracted year from the date.
DayOfWeek: The weekday of the first day of the month.
Platform: The gaming platform (e.g., Xbox, Nintendo, PC, PlayStation).
Holiday: Binary indicator (1 if a holiday is in that month, 0 otherwise).
Promotion: Binary indicator (1 if there was a promotion, 0 otherwise).

5. Next Steps
Convert the Month column to a datetime format and set it as the index.
Perform Exploratory Data Analysis (EDA).
Decompose the time series to understand trends and seasonality.
Build ARIMA and SES and Holt-Winters  models for forecasting.
Evaluate the models and make a four-month forecast.

Looking at the forecasting models
After building the models the we compare the models as below:

          Actual          ARIMA   Holt-Winters           SES
Month                                                         
2023-09-01  143373  116317.282605   94168.683589  114150.35762
2023-10-01  126410  116682.890976   87588.086270  114150.35762
2023-11-01   91200  113380.775304  101041.512820  114150.35762
2023-12-01  159721  115998.185396  105454.792863  114150.35762

Holt-Winters performs best as it captures seasonality better.
ARIMA provides a stable forecast but does not adjust well to sales fluctuations.
SES produces a constant forecast, making it unsuitable for dynamic sales data

FINAL FORECAST FOR THE NEXT FOUR MONTHS
Since Holt-Winter seem to perform best is best to use it to predict the next four months

            Forecasted Sales
2024-01-01      94168.683589
2024-02-01      87588.086270
2024-03-01     101041.512820
2024-04-01     105454.792863

CONCLUSION
Holt-Winters Model was the best choice for forecasting due to clear seasonal trends.
Forecasting helps synchronize supply with demand, avoiding stockouts and overstock situations.

Next Steps: Fine-tune models further using hyperparameter tuning or more advanced techniques like Prophet or LSTMs.
Best Model: None
Best RMSE: inf

After fine tuning we concluded below:
The actual sales and the predicted sales are far apart. This can predict correctly¶
