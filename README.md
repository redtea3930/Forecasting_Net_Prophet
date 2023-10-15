# Forecasting Net Prophet
This exercise uses the Facebook Prophet library to make predictions based on financial data from MercadoLibre. Supplied source data csv's are stored in the [Resources](https://github.com/redtea3930/Forecasting_Net_Prophet/tree/main/Resources) folder.  Code was compiled in Google Colab before being uploaded to this repository. Plots were made with HoloViews and Prophet, the Holoviews plots are stored in the [Output Plots](https://github.com/redtea3930/Forecasting_Net_Prophet/tree/main/Output%20Plots) folder. A basic outline of the exercise is supplied here, further analysis is shown in [forecasting_net_prophet.ipynb](https://github.com/redtea3930/Forecasting_Net_Prophet/blob/main/forecasting_net_prophet.ipynb)

## Finding unusual patterns in hourly Google search traffic
Search traffic data was uploaded to a dataframe, traffic for May 2020 and monthly median traffic data was isolated and compared. It was found that traffic in May 2020, when MercadoLibre financial reports were publicized, was higher than the monthly over median for several years.

![MeradoLibre Search Traffic May 2020](https://github.com/redtea3930/Forecasting_Net_Prophet/blob/main/Output%20Plots/MercadoLibre%20Search%20Traffic%20May%202020.png)

## Mining the search traffic data for seasonality
Hourly and day-of-week data were then extracted and compared to find patterns in search traffic over the course of a week, traffic peaks around midnight during the work week.

![MercadoLibre Search Traffic by Day of Week](https://github.com/redtea3930/Forecasting_Net_Prophet/blob/main/Output%20Plots/MercadoLibre%20Search%20Trends%202016-2020%20by%20Day%20of%20Week.png)

![MercadoLibre Search Traffic Hourly Across Week](https://github.com/redtea3930/Forecasting_Net_Prophet/blob/main/Output%20Plots/MercadoLibre%20Search%20Trends%202016-2020%2C%20Hourly%20across%20Week.png)

Week-of-year data were extracted, traffic varies over the year but dips noticeably in mid-October and around Christmas.

![MercadoLibre Search Traffic 2016-2020 by Week of Year](https://github.com/redtea3930/Forecasting_Net_Prophet/blob/main/Output%20Plots/MercadoLibre%20Search%20Traffic%202016-2020%20by%20Week%20of%20Year.png)
## Relating the search traffic to stock price patterns
A new dataframe was created from a csv of MercadoLibre closing prices.
![MercadoLibre Closing Price](https://github.com/redtea3930/Forecasting_Net_Prophet/blob/main/Output%20Plots/MercadoLibre%20Closing%20Price.png)

Dataframes of search traffic and closing price were concatenated, data for these values for the first half of 2020 were compared. It was found that both search traffic and closing price sharply declined in early 2020 but recovered by mid-year.
![MercadoLibre Hourly Search Traffic and Closing Price First Half 2020](https://github.com/redtea3930/Forecasting_Net_Prophet/blob/main/Output%20Plots/MercadoLibre%20Hourly%20Search%20Traffic%20and%20Closing%20Price%20first%20half%202020.png)

Columns for stock volatility and hourly stock return were calculated.
![MercadoLibre Stock Volatility 2016-2020](https://github.com/redtea3930/Forecasting_Net_Prophet/blob/main/Output%20Plots/MercadoLibre%20Stock%20Volatility%202016-2020.png)

## Creating a time series model with Prophet
A Prophet model was fit to search traffic data to predict traffic for 80 days beyond the supplied data.

## Forecasting revenue by using time series models
Another csv of daily sales was used in Prophet to predict revenue for the last quarter of 2020.
![MercadoLibre Daily Sales Jan 2019-May 2020](https://github.com/redtea3930/Forecasting_Net_Prophet/blob/main/Output%20Plots/MercadoLibre%20Daily%20Sales%20Jan%202019%20-%20May%202020.png)