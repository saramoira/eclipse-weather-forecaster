# Solar Elipse Classifier
Saramoira Shields

## Abstract
On April 8th, 2024, a total solar eclipse will trace a path across portions of Canada, the United States, and Mexico. Many people will be travelling to locations in the path of totality in order to view this rare event. The ultimate purpose of this tool is to model the likelihood of clear sky on that date so that people can better decide where to travel to for this event. 

## Design 
After realizing that MODIS data was not granular enough for my purposes, I updated my dataset to all 2021 data from US weather stations reporting local climatological data. The dataset descriptions can be found [here](https://www.ncei.noaa.gov/data/local-climatological-data/doc/LCD_documentation.pdf). I then used Geopandas to take a subset of those stations by plotting only those in the eclipse path. From that dataset I was able to generate a cleaned multi-indexed timeseries of weather station readings, with a lagged variable for the recorded clear sky value for the next day. I also added categorical variables for month and growing zone. 

Due to the importance of reducing false positives, I tested multiple logistic classifiers using an F beta metric with beta = 0.5. I found that the KNN classifier with k = 5.

## Data
* NOAA’s [Local Climatological Data for 2021](https://www.ncei.noaa.gov/data/local-climatological-data/)
* [Eclipse path information](https://eclipse.gsfc.nasa.gov/solar.html) from NASA for plotting the path and selecting stations. 
* [Daily NASA MODIS satellite cloud fraction data](https://neo.gsfc.nasa.gov/view.php?datasetId=MODAL2_D_CLD_FR&year=2021) and https://neo.gsfc.nasa.gov/archive/csv/MODAL2_D_CLD_FR/  

## Algorithms/Tools
This project used pandas timeseries tools and geopandas for data cleaning and selection, as well as multiple tools from sckikit-learn for preprocessing, metric evaluations, and model selection. Seaborn and Folium were used for visualization.

