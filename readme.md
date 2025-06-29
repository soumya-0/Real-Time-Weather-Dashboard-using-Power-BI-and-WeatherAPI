# Real-Time Weather Dashboard using Power BI and WeatherAPI

## Project Overview

This project demonstrates how to integrate real-time weather data from a RESTful API into Power BI to build an interactive and visually appealing weather analytics dashboard. By leveraging the WeatherAPI, I have extracted and modeled JSON data to visualize current weather conditions, forecasts, and air quality indices for four major Indian cities: Kolkata, Chennai, Gujarat, and Lucknow.

### Technologies Used
Power BI Desktop

WeatherAPI – For live weather data

Power Query (M Language) – To extract and transform JSON data

DAX – For creating measures and calculated columns

Custom Visuals – Used for aesthetic and functional charts (e.g., donut charts, line graphs, KPI cards)

### Cities Tracked

The dashboard presents weather details for the following cities:

Chennai

Gujarat

Kolkata

Lucknow

Each city’s data is fetched from a REST API call structured as:
http://api.weatherapi.com/v1/forecast.json?key=<your_api_key>&q=<city_name>&days=4&aqi=yes&alerts=no
 
### Key Dashboard Features

Real-Time Conditions
Current temperature

Weather description (e.g., partly cloudy)

Live update timestamp

Quick city switching panel

🔹 Forecast Section
7-day forecast showing predicted daily temperatures

Line chart of daily temperature trends

🔹 Atmospheric Indicators
Precipitation (mm)

Humidity (%)

Wind speed (kmph)

Visibility (km)

Atmospheric pressure (inHg)

UV index

🔹 Air Quality Index
Real-time metrics:

CO (Carbon Monoxide)

NO₂ (Nitrogen Dioxide)

SO₂ (Sulfur Dioxide)

PM2.5 and PM10 (particulate matter)

O₃ (Ozone)

Pie chart breakdown of major pollutants

EPA and DEFRA index scores for easy interpretation

🔹 Sunrise and Sunset Times
Displays sunrise and sunset times for the selected city.

🔹 Rain Probability
A horizontal bar chart showing the daily chances of rain for the upcoming days.

![Dashboard Screenshot](./Screenshot%202025-06-29%20215723.png)


### Data Modeling Process
API Connection:
Connected to WeatherAPI using Power Query’s Web.Contents() for four cities: Chennai, Kolkata, Gujarat, and Lucknow.

JSON Parsing:
    Flattened the nested JSON response into accessible tables covering current, forecast.day, and forecast.hour data.

Data Transformation:

    Created individual tables for each city’s current, daily, and hourly weather data.

    Renamed and formatted columns for clarity and consistency.

    Combined all city data into a central master table using city names as a key.

    Created three unified tables: current, forecast_days, and forecast_hours.

DAX Calculations:

    Organized all measures in a dedicated measures table for model cleanliness.

    Developed dynamic metrics for temperature, wind, visibility, rain probability, and air quality components (CO, NO₂, SO₂, PM2.5, PM10, O₃).
