## Cloud cover forecasting with linear regression

The goal of this project is to use linear regression to model cloud coverage (fraction of the sky covered by clouds) using weather station data at approximately 2000 location points. 

I have plotted cloud coverage using the MODIS dataset for one day:

![Cloud cover over the US for one day ](https://github.com/saramoira/eclipse-weather-forecaster/blob/main/images/cloud_cover.png)

I also have a cleaned dataset of stations and their readings for the previous day: 

![weather dataset](https://github.com/saramoira/eclipse-weather-forecaster/blob/main/images/dataset.png)

HOWEVER - none of my linear regression plots are making sense once I try to add the cloud data (and any other MODIS data) to the dataset. I've determined the issue has to do with reading incorrect values from the MODIS dataframes - the data is in csv format, but the files are indexed by latitude and longitude as an array. My next steps are determining how I can match the locations of the stations to the correct values in the MODIS dataframes, then it will be possible to train and test a model.  
