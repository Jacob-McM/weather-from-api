# Gathering Weather Data Utilizing API Calls
This repo contains two Jupyter Notebook files that contain code that will generate cities and pull weather data of those cities from the free OpenWeather API when run. This weather data is then analyzed for any potential implications based on a cities hemispheric location. Post analysis, a second notebook utilizes two types of google Maps Platform API to produce two heatmaps based on the humidity of the locations generated in the first notebook. The purpose of this repo was to demonstrate understanding and ability to make an API Call, and to combine different API calls for a directed purpose.

In this repo you will find:

In this repo you will find:
|Notebook|Description|
|--------|-----------|
|[Hemispheric Analsysis](hemispherical_analysis.ipynb)| A notebook containing an OpenWeather 'Current Weather Data' API call loop that calls for weather data from cities that were generated using the citipy library based on Lat/Long input. Based on the data retrieved from the OpenWeather API call, 4 scatter plots are made based on several parameters returned from the data. Linear regression is performed on each plot to understand if there is an observed relationship to a locations hemispheric position and its observed weather data. The city data that was generated, the weather data that was called, and the images of the plots were all saved as corresponding output files.
|[Weather Heatmaps](weather_heatmap_notebook.ipynb)|This notebook contains two heatmaps generated based on the data found in the [Hemispheric Analsysis Notebook](hemispherical_analysis.ipynb). These heatmaps were generated using Google Maps Platform API. The first map contains a heatmap of the humidity of all the locations in the dataset. The next map was based off of a transformed version of the first notebooks data. The transformation was to see locations based on my ideal weather conditions. This resulted in a list of 62 locations, which was trimed to 9 locations. Using the Google Maps Platform 'Nearby Places' API hotels within a given radius were found for these 9 locations. These locations were then added as a marker layer on a second humidity heatmap. |

|Data|Description|
|----|-----------|
|[Cities data](output_data/cities.csv)| A csv file initialy containing the city name based on a latitude and longitude range provided to the citipy library. The library then provides cities based on the provided information. After the API call, the file is updated to contain the resulting called data.
|[Weather Data](output_data/weather_data.csv)| A csv file which is a cleaned version of the post API call [cities.csv](output_data/cities.csv). Contains human legible dates and reorganized column structure. This file is used for data analysis and plotting|
|[Hotel Data](output_data/hotel_data.csv)| A csv file containing 9 cities and an associated hotel found by the Google Nearby Places API. |

There is also an [images folder](images/) with output of the plots found in the [Hemispheric Analsysis Notebook](hemispherical_analysis.ipynb).

# What is the purpose of this repo?

Generally speaking, the purpose of this repo is to demonstrate what is possible through the combination of different API calls for a unified purpose. The API calls used in this project are as follows:

|API Call|Description|
|--------|-----------|
|[Open Weather 'Current Weather Data' API](https://openweathermap.org/current)| This API call returns various data based on the input latitude and longitude. For this project, I was interested in the `date`, `country`, `max temp`, `humidity`, `cloudiness`, and `wind speed`. 
|[Google Maps Platform 'Maps JavaScript API'](https://developers.google.com/maps/documentation/javascript/overview)| This API was used to generate heatmaps based on data from this project. It was also used to display markers at specific locations in conjunction with the heatmap. This was accomplished by utilizing its layering feature. In order to display this in a JupyterNotebook, the gmaps library was used.|
|[Google Maps Platform 'Places API'](https://developers.google.com/maps/documentation/places/web-service/overview)| This API was used to find hotels based on proximity to provided locational data. The returned information was then used as the markers on the second heatmap utilized in this project|

A secondary objective of this project was to view and analyze the returned weather data form any sort of hemispheric significance. All locational data was generated with this hemispheric analysis in mind, the results of which are best viewed in the [Hemispheric Analsysis Notebook](hemispherical_analysis.ipynb) as there are indepth reasonings and explanations behind the plots generated and their resulting analysis. 

## Dependencies
In order to fully utilize this repo, these libraries/modules were utilized:

|Dependancy|ver|
|----------|---|
|[Matplotlib](https://matplotlib.org/)|3.5.1|
|[NumPy](https://numpy.org/)|1.21.5|
|[pandas](https://pandas.pydata.org/)|1.4.2|
|[Requests](https://requests.readthedocs.io/en/latest/)|2.27.1|
|[SciPy](https://scipy.org/)|1.7.3|
|[citipy](https://github.com/wingchen/citipy)|0.0.5|
|[gmaps](https://github.com/pbugnion/gmaps)|0.9.0|

Utilizing IPython 8.2.0 running Jupyter Notebook 6.4.8

## Resources/ Acknolwgedments

##### © 2022 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
##### Google and OpenWeather API services & Documentation
