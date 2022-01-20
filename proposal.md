# 2024 Solar Eclipse Cloud Cover Forecaster


## Question/need:
### What is the framing question of your analysis, or the purpose of the model/system you plan to build?

On April 8th, 2024, a total solar eclipse will trace a path across portions of Canada, the United States, and Mexico. Many people will be travelling to locations in the path of totality in order to view this rare event. The purpose of this tool is to model the likelihood of cloud cover on that date for approximately 10-15 locations along that path, so that people can better decide where to travel to for this event.  

### Who benefits from exploring this question or building this model/system?

Anyone who is interested in viewing the 2024 solar eclipse, but especially those who have to travel from outside of the United States and make destination decisions well in advance of the event.

## Data Description:
### What dataset(s) do you plan to use, and how will you obtain the data?

1. Daily Weather Underground data from 2016-present, including temperature, humidity, pressure, day length, precipitation, wind speed, and dew point. I will be focusing on data from the following locations:<br>
* Terra Nova National Park, Newfoundland, Canada
* Baxter State Park, Maine, USA
* Montreal, Quebec, Canada
* Buffalo, New York, USA
* Erie, Pennsylvania, USA
* Cleveland, Ohio, USA
* Indianapolis, Indiana, USA
* Little Rock, Arkansas, USA
* Dallas/Fort Worth, Texas, USA
* Austin, Texas, USA
* Piedras Negras, Coahuila, Mexico
* Durango, Victoria de Durango, Mexico
* Mazatlán, Sinaloa, Mexico

Example location: Buffalo, NY: https://www.wunderground.com/history/daily/us/ny/buffalo/KBUF

* Daily NASA MODIS satellite cloud fraction data from 2016-present . <br>
Location:  https://neo.gsfc.nasa.gov/view.php?datasetId=MODAL2_D_CLD_FR&year=2022 and https://neo.gsfc.nasa.gov/archive/csv/MODAL2_D_CLD_FR/

### What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?

* For the weather data, an individual sample would include high/low temperature, high/low humidity, high/low pressure, day length, total precipitation, high/low wind speed, and high/low dew point over one day for a single location. 

* For the MODIS data, and individual sample would include a data array of observed cloud fractions for a chosen location over one day. 

### If modeling, what will you predict as your target?

I expect to predict the lowest chances of cloud cover in Texas and Mexico, and the highest chances in Canada and locations near the Great Lakes. 

## Tools:
### How do you intend to meet the tools requirement of the project?

I plan to use Beautiful Soup to scrape the weather and MODIS data, clean and organize the datasets using Pandas and SQL, do linear regression with scikit-learn, and use Seaborn and Plotly to create visualizations.

### Are you planning in advance to need or use additional tools beyond those required?

I am not currently planning to use additional tools, but may choose to do so as analysis progresses. 

## MVP Goal:
### What would a minimum viable product (MVP) look like for this project?

A ranking of the listed locations in order of predicted rainfall for the month of April, 2024.
