# Eclipse Weather Forecaster

This is a tool for forecasting the probability of cloud cover along the path of the 2024 solar eclipse. (Limited to land-based locations)

Note to Metis: Main code is in [Data Cleaning - Model Fit](https://github.com/saramoira/eclipse-weather-forecaster/blob/main/Data%20Cleaning%20-%20Model%20Fit.ipynb).

[Wunderground](https://github.com/saramoira/eclipse-weather-forecaster/blob/main/Wunderground.ipynb) was my first scraping attempt - it technically worked, but would time out constantly due to ads on the page. I also didn't like the quality of the Wunderground data, it was really spotty.

[MADIS scraping](https://github.com/saramoira/eclipse-weather-forecaster/blob/main/MADIS%20scraping.ipynb) is what I used to get better quality data using Selenium. 

[Solar Eclipse Path](https://github.com/saramoira/eclipse-weather-forecaster/blob/main/Solar%20Eclipse%20Path.ipynb) and [MODIS]() were mapping and visualization tests when I was learning how to use GeoPandas and Xarray. 
