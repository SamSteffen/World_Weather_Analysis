# World_Weather_Analysis

## 6.1.2 Overview of the Project
At the most fundamental level, Jack needs help answering a question: How might we provide real-time suggestions for our client's ideal hotels? Your first task was to define what you meant by "ideal." So, over the course of the conversation, you narrowed that to hotels that were (1) within a given range of latitude and longitude and that (2) provided the right kind of weather for the client.

## Basic Project Plan
Here's an outline of your project plan:

- Task: Collect and analyze weather data across cities worldwide.
- Purpose: PlanMyTrip will use the data to recommend ideal hotels based on clients' weather preferences.
- Method: Create a Pandas DataFrame with 500 or more of the world's unique cities and their weather data in real time. This process will entail collecting, analyzing, and visualizing the data.
Your analysis of the data will be split into three main parts, or stages.

### Collect the Data
- Use the NumPy module to generate more than 1,500 random latitudes and longitudes.
- Use the citipy module to list the nearest city to the latitudes and longitudes.
- Use the OpenWeatherMap API to request the current weather data from each unique city in your list.
- Parse the JSON data from the API request.
- Collect the following data from the JSON file and add it to a DataFrame:
* City, country, and date
* Latitude and longitude
* Maximum temperature
* Humidity
* Cloudiness
* Wind speed

### Exploratory Analysis with Visualization
- Create scatter plots of the weather data for the following comparisons:
* Latitude versus temperature
* Latitude versus humidity
* Latitude versus cloudiness
* Latitude versus wind speed
- Determine the correlations for the following weather data:
* Latitude and temperature
* Latitude and humidity
* Latitude and cloudiness
* Latitude and wind speed

- Create a series of heatmaps using the Google Maps and Places API that showcases the following:
* Latitude and temperature
* Latitude and humidity
* Latitude and cloudiness
* Latitude and wind speed

### Visualize Travel Data
- Create a heatmap with pop-up markers that can display information on specific cities based on a customer's travel preferences. Complete these steps:
- Filter the Pandas DataFrame based on user inputs for a minimum and maximum temperature.
- Create a heatmap for the new DataFrame.
- Find a hotel from the cities' coordinates using Google's Maps and Places API, and Search Nearby feature.
- Store the name of the first hotel in the DataFrame.
- Add pop-up markers to the heatmap that display information about the city, current maximum temperature, and a hotel in the city.

### Findings
From 6.1.5 - When you run the code block, you should get slightly more than 500 unique cities. If you get fewer than 500, increase your size limit on the np.random.uniform() function.

### Findings
From 6.4.2. - The correlation between the latitude and the maximum temperature is strong to very strong because the r-value is less than –0.7 for the Northern Hemisphere and greater than 0.7 for the Southern Hemisphere, as shown by the plots here. This means that as we approach the equator, 0° latitude, the temperatures become warmer. And when we are further from the equator the temperatures become cooler. Check the r-values for your plots. 

### Findings
From 6.4.3 - The correlation between the latitude and percent humidity is very low because the r-value is less than 0.04 for the Northern and Southern Hemispheres for the plots shown here. This means that percent humidity is unpredictable due to changing weather patterns that can increase or decrease percent humidity. Check the r-values for your plots. 

### Findings
From 6.4.4 - The correlation between the latitude and percent cloudiness is very low because the r-value is less than –0.09 for the Northern Hemisphere and less than –0.02 for the Southern Hemisphere for the plots shown here. This means that cloudiness is unpredictable due to changing weather patterns that can increase or decrease percent cloudiness. Check the r-values for your plots.

### Findings
From 6.4.5 - The correlation between the latitude and wind speed is very low because the r-value is less than –0.07 for the Northern Hemisphere and less than –0.3 for the Southern Hemisphere for the plots shown here. This means that wind speed is unpredictable due to changing weather patterns that can increase or decrease wind speed. Check the r-values for your plots.

# Challenge
Jack loves the PlanMyTrip app. Beta testers love it too. And, as with any new product, they’ve recommended a few changes to take the app to the next level. Specifically, they recommend adding the weather description to the weather data you’ve already retrieved in this module. Then, you'll have the beta testers use input statements to filter the data for their weather preferences, which will be used to identify potential travel destinations and nearby hotels. From the list of potential travel destinations, the beta tester will choose four cities to create a travel itinerary. Finally, using the Google Maps Directions API, you will create a travel route between the four cities as well as a marker layer map.

This new assignment consists of three technical analyses. You will submit the following deliverables:

Deliverable 1: Retrieve Weather Data
Deliverable 2: Create a Customer Travel Destinations Map
Deliverable 3: Create a Travel Itinerary Map

+
A README.md that describes the purpose of the repository. Although there is no graded written analysis for this challenge, it is encouraged and good practice to add a brief description of your project.

IMPORTANT
Do not include your config.py file in your submission.

If you’d like a hint on how to not include the config.py file when adding your files to your GitHub repository, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

HINT
To prevent GitHub from tracking and adding the config.py file to your GitHub repository, revisit Lesson 6.2.7: Create a DataFrame of city weather data.
