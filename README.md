# co2-tsa
Used Time Series modelling in R on co2 dataset including data analysis, decomposition, stationarity testing, differencing, model selection and forecasting using ARIMA and SARIMA models. 

Do you notice any trends or seasonality? -> Yes, the data shows an upwards trend and homoscedastic seasonality. 

Which model fits better, and why? -> The additive model fits better as the seasonal variation in the data is almost constant and is homoscedastic.

What insights can you draw from the decomposition results? -> The data has the component of trend, seasonality and randomness.

Are the residuals stationary (constant mean and variance)? Provide your reasoning. -> ADF test was applied on the residuals of additive series. Following is the hypothesis:
H0: Not Stationary
H1: Stationary
The test gave a p value of 0.01 which is less than 0.05. Hence, we reject the NULL Hypothesis and claim that the residual of additive series is stationary.

What does the p-value indicate? -> The p value derived from ADF test tells if the series is stationary or not. If p value is lesser than 0.05 then we accept the NULL Hypothesis which says that series is stationary while we reject the NULL Hypothesis if p value is greater than 0.05.
Here, p value is 0.2269 which is greater than 0.05. We accept the NULL Hypothesis and prove that the series is not stationary. 

Which model has better fit statistics (e.g., AIC, BIC)? -> The auto ARIMA provides a better fit statistic.

Are the residuals white noise? Justify your answer. -> The residual is a white noise. Following are the plausible reasons for the same:
•	ACF plot lies within the confidence interval, also there are no spikes in the ACF plot implies that there is no Auto-Correlation factor present.
•	As per the output from Ljung test, the p value is greater than 0.05 i.e. 0.4714. This implies that the residuals are independent and confirms that residual is a White Noise.

How well do the forecasts capture the trends and seasonality? -> The forecasting perfectly captures the trend and seasonality. For a better quality for decision making, h=60 was kept. The forecasted pattern strictly follows "Homoskedasticity" as like for the original dataset and follows the same growing pattern.

What are the potential limitations of your forecast? -> SARIMA model is based on fixed seasonality, in case if the seasonality gets disrupted, the model will fail.
SARIMA model does not account any exogenous effect therefore in case of any external event, the model will fail.

