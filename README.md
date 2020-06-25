# ETL-Project
Cody Sellers, Schuyler Marin, Krissy Santucci

Extract:
UFO: We extracted the UFO data from Kaggle.com from the dataset “UFO Sightings around the world” posted by Cam Nugent. We utilized the CSV file. The data included state/province, country, UFO shape, length of encounter in seconds, described duration of encounter, description, date documented, latitude and longitude. There were 69,586 sightings included in this dataset.
MILITARY BASES: We extracted the military base locations from the website: https://public.opendatasoft.com/explore/dataset/military-bases/export/.  
Per the website: “The Military Bases dataset as of May 5, 2017, and is part of the U.S. Department of Transportation (USDOT)/Bureau of Transportation Statistics's (BTS's) National Transportation Atlas Database (NTAD). This dataset was created from source data provided by the four Military Service Component headquarters and was compiled by the Defense Installation Spatial Data Infrastructure (DISDI) Program within the Office of the Deputy Under Secretary of Defense for Installations and Environment, Business Enterprise Integration Directorate.”
We connected to the military base API, used Python to loop through the data of each of the military base, and then exported the information as an excel file to gather the “geo-location”.

Transform:
UFO: From the CSV from the UFO dataset, we created two data frames. The first data set was grouped by City, then we looped through the data to count the recurrences of each city. This gave us a smaller data set but created a frequency column. The second dataset we created was sorted by city and included the latitude and longitude of each documented sighting. From there, we merged the 2 data frames and dropped the duplicates.
MILITARY BASES: From the API generated excel file, we extracted the “geo-points” and had to split the column for “latitude, longitude” into two separate columns. 

Load:
We used gmaps to create a heat map showing the UFO sightings, using the frequency of the cities as the weight. Then we took the coordinates of the military bases and plotted them as marker points over the heat map. We were trying to see if there was any correlation between the presence of military bases and the occurrences of UFO sightings.


Findings:
We found that there is a visible correlation between UFO sightings and military bases. There seems to be a high concentration of UFO sightings where military bases are located. The gmap seems to show that the more bases in an area the more UFO sighting are reported.

Further Research:
It would have been interesting to see if population was correlated to the amount of UFO sightings reported.
We could have focused on each type of military base at a time i.e. (Army, Air Force, Navy, Marine Corp). Or narrowed the bases down by only plotting active bases. 

![alt text][logo]

[logo]: https://github.com/krissysantucci/UFOs_ETL-Project/blob/master/Screen%20%20shot1.png "Logo Title Text 2"

https://github.com/krissysantucci/UFOs_ETL-Project/blob/master/Screen%20%20shot1.png?raw=true
