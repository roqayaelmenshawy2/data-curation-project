
# IS 477 - Project Plan

**Project Title:** Weather Extremes and Flight Delays at Major U.S. Airports

## 1. Overview

The objective of this project is to understand how different weather conditions affect flight delays and cancellations at major U.S. airports. Severe weather, such as snow, heavy rain, and strong winds, can cause flight disruptions. However, some airports may be affected more than others depending on their location, weather patterns, and size. Our project will explore these differences by combining data from multiple sources.

We plan to study approximately ten major U.S. airports, including Chicago O'Hare, JFK, Los Angeles International, and Denver International, using data from 2024. We will use flight data from the Bureau of Transportation Statistics (BTS), weather data from the National Oceanic and Atmospheric Administration (NOAA), and airport information from the Federal Aviation Administration (FAA).

The main focus of our project will be collecting, cleaning, and combining data rather than building complex models. Using Python and Pandas, we will check the datasets for missing information, errors, and differences in formatting. We will then clean the data and combine the datasets using airport codes and dates.

Once the data is combined, we will compare flight delays under different weather conditions and create charts to show how delays vary across airports.

Throughout the project, we will follow the main steps of the data lifecycle, including collecting, checking, cleaning, combining, analyzing, and documenting data. Our goal is to create a clear and repeatable process that shows how information from different government sources can be used to better understand the relationship between weather and flight delays.

## 2. Team

Our project will be completed by four team members. Responsibilities will be divided evenly so that each member contributes to data collection, cleaning, integration, analysis, and documentation. Each member will have a primary responsibility while also working together on the overall project.

| Team Member | Primary Responsibilities |
|---|---|
| **Suha Khan** | Collect and clean BTS flight data, identify missing or incorrect values, and prepare flight records for integration. |
| **Chris Geier** | Collect and clean NOAA weather data, standardize weather measurements and dates, and prepare weather records for integration. |
| **Stephanie Li** | Collect and clean FAA airport data, standardize airport identifiers, and prepare airport information for integration. |
| **Roqaya Elmenshawy** | Develop the data integration process, combine the three cleaned datasets, and check that the datasets are joined correctly. |

All team members will contribute to the project plan, status report, final README, and GitHub repository. Individual contributions will be documented through Git commits.

## 3. Research Questions

**Primary Research Question:**

How are extreme weather conditions associated with flight delays and cancellations at major U.S. airports?

**Supporting Research Questions:**

1. Which weather conditions, including snowfall, heavy rain, and high winds, are associated with the greatest average departure delays?
2. Which airports experience the largest increases in delays during severe weather compared with normal weather conditions?
3. How do airport characteristics, such as passenger volume and hub classification, relate to differences in weather-related flight disruptions?

We will measure average departure delay minutes, percentage of flights delayed, and cancellation rates. Weather conditions will be categorized using documented thresholds. We will compare outcomes across airports and weather categories while recognizing that observed relationships do not necessarily establish causation.
