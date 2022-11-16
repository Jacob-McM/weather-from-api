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
