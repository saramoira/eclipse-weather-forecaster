# Logistic Model progress

So far I have cleaned a dataset consisting of 167 weather stations in the eclipse path, with hourly observations of both weather variables (temperature, wind speed, relative humidity, pressure, etc) and cloud coverage. I've also added some fixed effects: season (month), elevation, and USDA Plant hardiness zone. I'm going to compare a basic logistic regression (treating each observation in the full dataset as distinct, mostly done already) to a time series logistic regression for each station (which I started building today). So far the strongest features are relative humidity and altimeter setting: 

