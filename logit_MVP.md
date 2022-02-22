# Logistic Model progress

So far I have cleaned a dataset consisting of 167 weather stations in the eclipse path, with hourly observations of both weather variables (temperature, wind speed, relative humidity, pressure, etc) and cloud coverage. I've also added some fixed effects: season (month), elevation, and USDA Plant hardiness zone. I'm going to compare a basic logistic regression (treating each observation in the full dataset as distinct, mostly done already) to a time series logistic regression for each station (which I started building today). So far the strongest features are relative humidity and altimeter setting: 

![simple logit fit for relative humidity](https://github.com/saramoira/eclipse-weather-forecaster/blob/main/images/rh.png)
![simple logit fit for altimeter](https://github.com/saramoira/eclipse-weather-forecaster/blob/main/images/altse.png)

Also wind direction has promise, especially in a lagged time series. I think the main issue with this feature is that it is reported in degrees. I will try binning the values and adding it to the model next. (This is plotting wind direction vs. the cloudy/clear boolean)
![wind_dir plot](https://github.com/saramoira/eclipse-weather-forecaster/blob/main/images/wind_dir.png)

I also really want to compare a standard logit model + fixed effects (season, usda growing zone) vs. a time series model on just the weather data. I have the fixed variables already added to my dataset, so I should have that part and the first crack at the time series done tomorrow. 
