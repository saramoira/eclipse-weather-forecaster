# 2024 Solar Eclipse Cloud Cover Forecaster - UPDATE


## Question/need:
### What is the framing question of your analysis, or the purpose of the model/system you plan to build?

On April 8th, 2024, a total solar eclipse will trace a path across portions of Canada, the United States, and Mexico. Many people will be travelling to locations in the path of totality in order to view this rare event. The ultimate purpose of this tool is to model the likelihood of clear sky on that date so that people can better decide where to travel to for this event.  

### Who benefits from exploring this question or building this model/system?

Anyone who is interested in viewing the 2024 solar eclipse, but especially those who have to travel from outside of the United States and make destination decisions well in advance of the event.

## Data Description:
### What dataset(s) do you plan to use, and how will you obtain the data?

1. [Global MADIS weather data](https://madis-data.ncep.noaa.gov/public/sfcdumpguest.shtml), including temperature, humidity, pressure, precipitation, wind speed, visibility, and dew point. I will be using Selenium and Beuatiful Soup to scrape all readings from selected stations over a 24 hour period. I will then calculate max, min, and mean for the selected variables over that day to test as variables in the model. MADIS returns approximately 32,000 stations with data in this set, so after cleanup I should have at alease 10,000 stations. 

* [NASA MODIS satellite cloud fraction data](https://neo.gsfc.nasa.gov/view.php?datasetId=MYDAL2_D_CLD_FR&date=2022-02-09). This is the target variable. The data is in csv format and will be loaded as an xarray in python. I will also be using NASA's API tools to get time stamps associated with the array cells. The daily "image" is actually multiple bands representing a pass of the satellite, so having a sense of when each part of the array was recorded will help with data cleanup. 

### What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?

* For the weather data, an individual sample would include high/low temperature, high/low humidity, high/low pressure, day length, total precipitation, high/low wind speed, high/low visibility, and high/low dew point over one day for a single location. 

### If modeling, what will you predict as your target?

I expect to predict the lowest chances of cloud cover for the next day in Texas and Mexico, and the highest chances in Canada and locations near the Great Lakes. 

## Tools:
### How do you intend to meet the tools requirement of the project?

I plan to use Beautiful Soup and Selenium to scrape the MADIS data. I will clean and organize the datasets using Pandas Geopandas, and Xarray, do logistic regression with scikit-learn, and use Seaborn, Plotly, and Folium to create visualizations.

### Are you planning in advance to need or use additional tools beyond those required?

Currently I plan on using Folium, which is a mapping tool for python. I may use other mapping tools as required.  

## MVP Goal:
### What would a minimum viable product (MVP) look like for this project?

Basic logistic model probabilities for next-day clear skies at 10 locations along the path of the eclipse. (Note: I've worked on this project before in the linear regression module. I have a backup project if this is not acceptable.)
