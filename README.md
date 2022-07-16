# World_Weather_Analysis
## Project Overview
The following is an analysis that visually and statistically illustrates the relationship between geographical latitude and a variety of weather parameters using Jupyter notebook, Pandas, CityPy, Python Requests, APIs, and JSON traversals. This analysis was undertaken to assist PlanMyTrip, a vacation planning service in the provision of real-time suggestions for hotels matching client weather preferences.  

To perform this analysis, we first collected and analyzed weather data across cities worldwide to recommend ideal hotels based on clients' weather preferences using OpenWeatherMap and Google APIs. This analysis was undertaken in three main parts:

### (1) Collecting the Data
- Using the NumPy module, more than 1,500 random latitudes and longitudes were generated.
- Using the citipy module, the nearest cities to the returned latitudes and longitudes were found.
- Using the OpenWeatherMap API we requested the current weather data from each unique city in the list.
- The JSON data from the API request was parsed to find the following and add it to a DataFrame:   
   * City, country, and date
   * Latitude and longitude
   * Maximum temperature
   * Humidity
   * Cloudiness
   * Wind speed

### (2) Exploratory Analysis with Visualization
- Following the collection of the above data, we created scatter plots of the weather data for the following comparisons. (These maps are viewable in the above WeatherPy.ipynb file).   
   * Latitude versus temperature
   * Latitude versus humidity
   * Latitude versus cloudiness
   * Latitude versus wind speed

- We then determined the correlations for the following weather data:
   * Latitude and Temperature   
The correlation between the latitude and the maximum temperature is strong to very strong because the r-value is less than –0.7 for the Northern Hemisphere and greater than 0.7 for the Southern Hemisphere, as shown by the plots here. This means that as we approach the equator, 0° latitude, the temperatures become warmer. And when we are further from the equator the temperatures become cooler. 

   * Latitude and Humidity   
The correlation between the latitude and percent humidity is very low because the r-value is less than 0.04 for the Northern and Southern Hemispheres for the plots shown here. This means that percent humidity is unpredictable due to changing weather patterns that can increase or decrease percent humidity. 

   * Latitude and Cloudiness   
The correlation between the latitude and percent cloudiness is very low because the r-value is less than –0.09 for the Northern Hemisphere and less than –0.02 for the Southern Hemisphere for the plots shown here. This means that cloudiness is unpredictable due to changing weather patterns that can increase or decrease percent cloudiness. 

   * Latitude and Wind Speed   
The correlation between the latitude and wind speed is very low because the r-value is less than –0.07 for the Northern Hemisphere and less than –0.3 for the Southern Hemisphere for the plots shown here. This means that wind speed is unpredictable due to changing weather patterns that can increase or decrease wind speed.

- We then created a series of heatmaps using the Google Maps and Places API to showcase the following:
   * Latitude and temperature
   * Latitude and humidity
   * Latitude and cloudiness
   * Latitude and wind speed

### (3) Visualization of the Travel Data
- Once the above visualizations were prepared, we created a heatmap with pop-up markers to display information on specific cities based on a customer's travel preferences. 

### Additional Analysis
Upon completing the above, we then refactored our code to comply with Beta tester recommendations, specifically, adding a description of the current weather to the weather data already collected. We then asked users to input statements to filter the data for their weather preferences, which were used to identify potential travel destinations and nearby hotels. The following used a customer temperature preference of anything between 75 and 90 degrees Fahrenheit to return hotel recommendations. From the list of potential travel destinations, the beta tester selected four cities in Mexico (Lazaro Cardenas, Acapulco, Puerto Espandido and Pochutla) to create a travel itinerary. Finally, using the Google Maps Directions API, a travel route was created between the four cities as well as a marker layer map.

## Results
The results of the analysis described above were as follows:   

- We initialized a geographical map of data based on our tester's temperature preference with markers showing cities where the criteria was met, as well as current weather conditions for the returned cities.   
<img width="740" alt="WeatherPy_vacation_map" src="https://user-images.githubusercontent.com/104729703/179362670-ba0d6457-269b-44b4-a954-ca0dac4beaa8.png">


- Following the creation of this interactive map, we honed in on a specific country to locate four cities in a close proximity that matched the user's preferences. Mexico is the country used in the example. The following shows 4 cities in Mexico where the user's temperature preferences are satisfied.   
<img width="742" alt="WeatherPy_travel_map_markers" src="https://user-images.githubusercontent.com/104729703/179362695-0b44a2db-fdb3-4823-935c-7ec3083c7391.png">

- We then modified the above map to make an itinerary for our user. The route of travel specified in the image below would satisfy bicycling as the mode of travel, and assumes the travelers would want to travel to the city furthest from their destination first and visit other cities on their return to the city of origin:   
<img width="737" alt="WeatherPy_travel_map" src="https://user-images.githubusercontent.com/104729703/179362684-04631c60-c461-490b-af44-13b76d17bfbe.png">


## Summary 
The above travel itinerary assumes that the starting and ending city will be the same. In the example used in this analysis, becuase of the coastal geography of the selected cities, the itinerary will involve "backtracking", i.e., returning to places already visited on the forward journey in order to return.    

To make the above code even more useful for potential travelers who do not wish to return to places twice on the same trip, it might be interesting to develop parameters for the directions layer map where "backtracking" is eliminated from the realm of possible returns. This could be done by establishing limits on the distance between cities, based on the mode of travel, and then making sure that cities are not visited more than once in a given itinerary.   

In order to make these calculations, it would also be beneficial to determine the distance between cities witihin a given travel itinerary and establish an estimated time of travel between cities based on the input of the traveler's mode of transportation ("DRIVING", "BICYCLING", "WALKING").  
