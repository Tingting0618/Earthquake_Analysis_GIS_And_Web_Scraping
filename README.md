# Earthquake Since 1900 -  GIS Programming and Web Scraping with Python

## Goal/inspiration
Nate Silver discusses the difficulty of predicting earthquakes in **The Signal and the Noise**. Nevertheless, we will review earthquakes that have occurred since 1900.

To start, we read the table of earthquakes from https://en.wikipedia.org/wiki/List_of_deadly_earthquakes_since_1900 using the `requests` and/or `beautifulsoup` library and load it to a pandas dataframe.

Data cleaning includes:

* Replaced empty strings with NaN
* Removed the footnotes from the 'Other Source Deaths' column
* Converted Magnitude to a numeric type.
* Corrected number of deaths when there is more than one value. When there is more than one value given, we chose the largest.
* Created a new column ('deaths') that evaluates the four total-death columns ('PDE Total Deaths', 'Utsu Total Deaths', 'EM-DAT Total Deaths', and 'Other Source Deaths') and populates the new column with the highest value.
* Explored the data in terms of when and where earthquakes occurred and how severe they were (magnitude, deaths, secondary effects).

![by year](https://user-images.githubusercontent.com/44503223/123418559-cb663200-d57e-11eb-98e8-33f7be9209ac.gif)
 
## Tenessee Earthquake Observations
To start, we used the `requests` library and the USGS's API (https://earthquake.usgs.gov/fdsnws/event/1/) to retrieve information about all recorded earthquakes that occurred in Tennessee since 1900.

![TnEarthquakeByLat/Lng](https://user-images.githubusercontent.com/44503223/123421233-35cca180-d582-11eb-8a68-88b5fc7d8adf.png)

Then, we downloaded the US County Boundaries.geojson from https://public.opendatasoft.com/explore/dataset/us-county-boundaries/download/?format=geojson&timezone=America/Chicago&lang=en.

Lastly, we spatial joined the earthquake's lat/long with the geojson file.

This chart maps all earthquake in TN since 1900.

![overview](https://user-images.githubusercontent.com/44503223/123421794-f3579480-d582-11eb-8383-88b7f817645d.png)

But more importantly, some earthquakes are more deadly than others. 

![death](https://user-images.githubusercontent.com/44503223/123421916-1da95200-d583-11eb-8726-3846b5508d22.png)

Based on the findings, we would like to recommend the Tennessee Earthquake Preparedness Group concentrate more resources in the two major metropolitan areas (Knoxville, Chattanooga), and Lake and Dyer Counties.


## Learn More

You can learn more in the [Tingting Duan's Project Portfolio](https://tingting0618.github.io).

