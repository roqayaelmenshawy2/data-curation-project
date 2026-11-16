
# IS 477 – Milestone 3: Interim Status Report

## Changes to Our Project

Our group originally planned to study how extreme weather conditions affect flight delays and cancellations at major U.S. airports. We planned to use flight data from the Bureau of Transportation Statistics, weather data from the National Oceanic and Atmospheric Administration, and airport information from the Federal Aviation Administration.

However, after reviewing the datasets, we realized that combining them would be more difficult than expected. The datasets used different identifiers, and matching weather observations to specific airports and flight dates would be very difficult. We were concerned that these challenges would make it difficult to complete the data integration process within the project timeline.

As a result, we decided to change our project to **Traffic Crash Severity and Road Conditions in Chicago**. Our new project focuses on understanding how road conditions, vehicle characteristics, and driver-related factors are associated with traffic crash injuries in Chicago.

We also decided to update our research questions. Our main research question is:

**How are road conditions, vehicle characteristics, and driver-related factors associated with traffic crash severity in Chicago?**

We also plan to explore three supporting questions:

1. How do road surface, weather, and lighting conditions relate to the number and severity of injuries reported in crashes?
2. Are certain vehicle types or characteristics more commonly associated with crashes involving injuries?
3. How do driver-related factors, such as age and other available characteristics, relate to crash severity?

These questions will help guide our analysis once the three datasets have been cleaned and combined.

## Datasets

We selected three datasets from the City of Chicago's Open Data Portal:

1. **Traffic Crashes – Crashes:** Contains information about crash dates, road conditions, weather, lighting, and injuries.
2. **Traffic Crashes – Vehicles:** Contains information about the vehicles involved in each crash, including vehicle types and characteristics.
3. **Traffic Crashes – People:** Contains information about individuals involved in crashes, including drivers, passengers, pedestrians, and reported injuries.

These datasets are closely related and can be combined using a shared identifier, `CRASH_RECORD_ID`. This makes it easier to connect information about crashes, vehicles, and people involved in the same incident.

Although our topic and datasets changed, our overall goals of data quality assessment, cleaning, analysis, and reproducibility remain the same.

## Current Progress

Our group has successfully found all three datasets for our new project and downloaded records for 2025–2026. We have also completed an initial data quality assessment of each dataset, focusing on accuracy, completeness, timeliness, and consistency.

We examined missing values, duplicate records, data types, and inconsistent formatting in our data. We also reviewed important variables such as crash dates, vehicle years, injury classifications, and crash identifiers. Through this assessment, we identified issues that needed to be addressed before integration and improved our understanding of the datasets' structures.

To clean the datasets, we used Python and Pandas.

For the **Crashes dataset**, we standardized column names and categorical values, checked crash identifiers and dates, examined numeric values, and addressed invalid coordinate information.

For the **Vehicles dataset**, we standardized formatting and checked vehicle identifiers and vehicle years for invalid or unrealistic values. Invalid and placeholder values were handled as missing data in such cases.

For the **People dataset**, we checked person identifiers and injury classifications, standardized city names, and examined missing demographic information and ZIP code formatting.

We organized our initial data quality assessment around four dimensions: accuracy, completeness, timeliness, and consistency. For accuracy, we checked values such as vehicle years, crash dates, and coordinates for possible errors. For completeness, we examined missing values in important fields, including injury classifications and demographic information. For timeliness, we reviewed the date coverage of our 2025–2026 records. For consistency, we checked data types, identifier formats, and categorical values across the three datasets.

Our cleaned Crashes dataset contains **205,758 records**, Vehicles contains **418,477**, and People contains **449,848**. Since the datasets contain different numbers of records, we will need to account for their one-to-many relationships when integrating them. We plan to document how many records successfully match across datasets and investigate unmatched records during our post-integration assessment.

After cleaning, each dataset was saved as a separate CSV file, allowing us to review the cleaned datasets before integration.

## Project Artifacts

The following files document the work completed so far:

- [Updated Project Plan](https://github.com/roqayaelmenshawy2/data-curation-project/blob/main/ProjectPlan.md)
- [Crashes Data Cleaning Notebook](https://github.com/roqayaelmenshawy2/data-curation-project/blob/main/notebooks/Traffic%20Crashes%20-%20Crashes.ipynb)
- [Vehicles Data Cleaning Notebook](https://github.com/roqayaelmenshawy2/data-curation-project/blob/main/notebooks/Traffic%20Crashes%20-%20Vehicle.ipynb)
- [People Data Cleaning Notebook](https://github.com/roqayaelmenshawy2/data-curation-project/blob/main/notebooks/Traffic%20Crashes%20-%20People.ipynb)
- [Cleaned Crashes, Vehicles, and People Datasets (UIUC Box)](https://uofi.box.com/s/mzlfx8xnymp7of6ui5m4s8jlmvcnubl8)

The cleaned CSV files are stored in UIUC Box because they exceed GitHub's file-size limits. These files document our progress and will be used during the integration stage.

## Next Steps

Now that we have cleaned our datasets, we must work on data integration. Following our updated project timeline, we plan to complete the initial integration process by November 19.

As mentioned previously, we identified `CRASH_RECORD_ID` as the common identifier across all three datasets. Our plan is to use the Crashes dataset as the main dataset because it contains one record per crash. The Vehicles and People datasets may contain multiple records for the same crash, so directly merging all three datasets risks creating duplicate crash records.

Thus, we plan to group the Vehicles dataset by `CRASH_RECORD_ID` and summarize various factors, such as the number and types of vehicles involved. The People dataset will also be grouped to summarize information about individuals involved and their reported injuries.

From there, we will use Pandas to perform left joins with the Crashes dataset, allowing us to preserve the original crash records while adding information from the other datasets.

Following integration, we will check row counts, duplicate identifiers, unmatched records, and missing values to confirm that the datasets were combined correctly. We will also conduct a post-integration quality assessment covering accuracy, completeness, timeliness, and consistency.

After creating our combined dataset, we will examine relationships between crash injuries and road conditions, weather, lighting, vehicle characteristics, and driver information. We will create visualizations to communicate the patterns identified. Our processing steps and data cleaning procedures will also be documented and organized.

## Updated Timeline

Since changing topics, we have adjusted our original tasks to reflect our new datasets while keeping the overall project schedule.

| Time Period | Task | Status |
|---|---|---|
| Oct. 12–25 | Original dataset research and acquisition | Completed |
| Oct. 26–Nov. 8 | Review original datasets and reconsider project scope | Completed |
| Nov. 9–15 | Select new project datasets, assess quality, and clean data | Completed |
| Nov. 16–19 | Develop and test data integration process | In progress |
| Nov. 20–24 | Post-integration data quality assessment | Not started |
| Nov. 25–29 | Crash severity analysis and visualizations | Not started |
| Nov. 30–Dec. 2 | Workflow automation and reproducibility | Not started |
| Dec. 3–4 | Metadata and documentation | Not started |
| Dec. 5–6 | Final testing and report completion | Not started |
| Dec. 7 | Final project release and submission | Not started |

## Challenges and Solutions

Our biggest challenge so far has been changing our project topic after realizing that our original datasets would be too difficult to integrate. This required meeting up once again as a team to search for new datasets, review their structures, and adjust our project plan. However, we feel much more confident having selected datasets that seem more manageable to work with.

Another challenge we've faced has been dealing with missing and inconsistent data. While cleaning, our team encountered issues with categorical values, identifiers, dates, and other fields. These issues were addressed by standardizing formatting, checking for invalid values, and handling missing information where appropriate.

We also anticipate challenges during integration because the datasets contain different numbers of records for each crash, as a single incident can involve multiple vehicles and people. Moving forward, we need to be careful when summarizing records, and we plan to review the combined datasets to avoid incorrectly increasing the number of crashes.

## Team Contributions

**Stephanie Li:** I helped with discussions about our new topic, cleaned the Crashes dataset, and drafted the updates and challenges sections of this status report.

**Suha Khan:** I found the datasets for our new project and cleaned the three datasets that we will be working with.

**Roqaya Elmenshawy:** I updated our project plan and status report to reflect our new topic, datasets, timeline, and remaining tasks. I also uploaded the cleaning notebooks to GitHub and organized the cleaned datasets in UIUC Box.

**Chris Geier:** I helped select a topic for our new project and contributed to the status report.
