
# IS 477 – Project Plan

Traffic Crash Severity and Road Conditions in Chicago

## 1. Overview

For our project, we want to look at how road conditions, vehicle characteristics, and driver-related factors relate to the severity of traffic crashes in Chicago. There are a lot of different things that can contribute to a car accident, whether it's bad weather, poor road conditions, or something involving the driver or vehicle. We're interested in seeing which of these factors tend to be associated with crashes that result in injuries.

To explore this, we're using three datasets from the City of Chicago's Open Data Portal: Traffic Crashes – Crashes, Traffic Crashes – Vehicles, and Traffic Crashes – People. Each dataset gives us different information about the same traffic incidents, and they all share a common identifier called CRASH_RECORD_ID. This allows us to connect them and get a more complete picture of each crash.

Our data covers 2025 and part of 2026. We're using Python and Pandas to check for missing values, duplicates, and inconsistencies before combining everything. Once the datasets are integrated, we'll compare injury outcomes across different road, weather, lighting, vehicle, and driver conditions.

The main focus of our project is the data curation process rather than building complicated statistical models. We want to show how we can take multiple datasets, clean and combine them, and use the results to answer meaningful questions. We'll also document our steps so that someone else can reproduce our work.

## 2. Team

Our group has four members, and we've divided the work based on the different parts of the project. Since changing our topic, we've also adjusted our responsibilities to better match the new datasets and the work that needs to be completed.

**Suha Khan:** Helped find and download the new Chicago traffic crash datasets, identify their common identifier, and clean the data. Suha will also help prepare the datasets for integration.

**Chris Geier:** Helped with discussions about changing our topic and selecting the new datasets. Chris will also help review data quality, document our processing steps, and support the remaining project work.

**Stephanie Li:** Worked on cleaning the Crashes dataset and identifying data quality issues. Stephanie also helped document our project changes and challenges and will contribute to the integration process.

**Roqaya Elmenshawy:** Helped with discussions about changing the topic, reviewing the new datasets, and updating our project timeline. Roqaya will also help with documentation, quality checks, and reviewing the integrated data.

All four of us will contribute to the final report and make sure our work is documented through GitHub commits.

## 3. Research Questions

Our main research question is:

**How are road conditions, vehicle characteristics, and driver-related factors associated with traffic crash severity in Chicago?**

We also want to answer a few more specific questions:

1. How do road surface, weather, and lighting conditions relate to the number and severity of injuries reported in crashes?
2. Are certain vehicle types or characteristics more commonly associated with crashes involving injuries?
3. How do driver-related factors, such as age and other available characteristics, relate to crash severity?

To answer these questions, we'll look at things like the number of injuries reported, whether a crash involved injuries, and the injury classifications available in our data. We'll compare these across different conditions to see if any patterns stand out.

We also recognize that just because two factors are related doesn't mean one directly causes the other. Our goal is to identify patterns and relationships rather than prove that any single factor causes more severe crashes.

## 4. Datasets

We selected three datasets from the City of Chicago's Open Data Portal. We chose them because they all describe different parts of the same traffic incidents, which makes them easier to connect than our original airport datasets.

### Traffic Crashes – Crashes

**Source:** City of Chicago Open Data Portal

This dataset contains general information about traffic crashes in Chicago, including when and where they happened, road surface conditions, weather, lighting, and reported injuries.

We'll use this as our main dataset because it contains information about each crash as a whole. It will help us understand how different environmental and road conditions relate to injury outcomes.

**Join Attribute:** CRASH_RECORD_ID

Some challenges include missing values, inconsistent categories, and potentially invalid location information. We have already worked on identifying and cleaning several of these issues.

### Traffic Crashes – Vehicles

**Source:** City of Chicago Open Data Portal

This dataset includes information about the vehicles involved in traffic crashes, such as vehicle types, model years, and other characteristics.

We'll use it to explore whether certain vehicle characteristics are more commonly associated with crashes involving injuries.

**Join Attribute:** CRASH_RECORD_ID

One challenge is that a single crash can involve multiple vehicles, meaning there can be several rows for the same crash. We'll need to summarize the vehicle information before combining it with the main dataset so that we don't accidentally create duplicate crash records.

### Traffic Crashes – People

**Source:** City of Chicago Open Data Portal

This dataset contains information about the people involved in crashes, including drivers, passengers, pedestrians, available demographic details, and reported injuries.

We'll use it to better understand who is involved in crashes and how different driver-related characteristics relate to injury outcomes.

**Join Attribute:** CRASH_RECORD_ID

Like the Vehicles dataset, this dataset can contain multiple records for one crash. We also noticed that some demographic and injury-related fields have missing information, so we'll need to keep that in mind when analyzing the data.

### How We'll Combine the Datasets

All three datasets share CRASH_RECORD_ID, which gives us a way to connect them.

We plan to use the Crashes dataset as our starting point since it has one record per crash. For the Vehicles and People datasets, we'll group the records by CRASH_RECORD_ID and create summaries of the information we need, such as the number of vehicles or people involved.

We'll then use Pandas to join these summaries to the Crashes dataset. This should allow us to keep one row per crash while bringing in useful information from the other two sources.

After combining everything, we'll check for duplicate records, missing matches, and other issues to make sure the integration worked as expected.

## 5. Timeline

We originally planned to spend October collecting and preparing our flight, weather, and airport datasets. However, after reviewing those sources, we realized that integrating them would be more difficult than we expected. We decided to change topics and adjust our schedule while keeping the December 7 final deadline.

**October 12–25: Original Dataset Research – Completed**

We researched the BTS, NOAA, and FAA datasets and looked into how we could combine them. During this process, we started identifying some challenges with the different identifiers and data formats.

**October 26–November 8: Reconsider Project Scope – Completed**

After discussing the issues with our original datasets, we decided to switch to a Chicago traffic crash project. We felt that the new datasets would give us a more realistic way to complete the data integration requirements while still answering an interesting question.

**November 9–15: Data Collection, Quality Assessment, and Cleaning – Completed**

We found and downloaded the three Chicago traffic crash datasets and performed an initial quality assessment. We checked for missing values, duplicate records, inconsistent formatting, and other potential issues. We also cleaned the datasets using Python and Pandas and saved separate cleaned CSV files.

**November 16–19: Data Integration – In Progress**

Our next step is to combine the three datasets using CRASH_RECORD_ID. We'll first summarize the Vehicles and People datasets to avoid creating duplicate crash records, then join them with the Crashes dataset.

**November 20–24: Post-Integration Quality Assessment – Not Started**

After combining the data, we'll check whether the joins worked correctly. This will include reviewing row counts, unmatched records, duplicate identifiers, and missing values. We'll also evaluate the integrated dataset for accuracy, completeness, timeliness, and consistency.

**November 25–29: Analysis and Visualizations – Not Started**

We'll use the integrated data to compare crash injuries across different road conditions, weather, lighting, vehicle characteristics, and driver-related factors. We'll also create charts to show any patterns we find.

**November 30–December 2: Workflow Automation and Reproducibility – Not Started**

We'll organize our code into separate steps for data acquisition, quality assessment, cleaning, integration, and analysis. We'll connect these steps through an automated workflow so that the project can be run without manually executing every notebook.

**December 3–4: Metadata and Documentation – Not Started**

We'll work on the data dictionary, project metadata, software dependencies, and documentation explaining how we collected, cleaned, and combined the data.

**December 5–6: Final Testing and Report – Not Started**

We'll test the workflow from a fresh copy of the GitHub repository and fix any issues that come up. We'll also finish the README, review our findings, and make sure all required files are included.

**December 7: Final Submission – Not Started**

We'll create the final GitHub release and submit the release URL through Canvas.

We may adjust some of these dates if certain steps take longer than expected, especially integration and workflow testing. We'll make sure to document any changes.

## 6. Constraints

There are a few challenges we need to keep in mind as we finish the project.

**Multiple records for the same crash:** One of our biggest concerns is that the three datasets don't all have the same number of records. A single crash can involve several vehicles and people, so directly merging the datasets could create duplicate crash records. To avoid this, we're planning to group and summarize the Vehicles and People datasets before combining them with the Crashes dataset.

**Missing or inconsistent information:** While cleaning the data, we came across missing values, inconsistent categories, and formatting differences. Some fields, like vehicle years, demographic information, and injury classifications, may not be complete for every record. We'll need to make sure these issues are handled consistently and explain any cleaning decisions we make.

**Different levels of detail:** Each dataset focuses on something different. The Crashes dataset describes the incident itself, while the Vehicles and People datasets describe individual vehicles and people. We need to be careful about how we summarize this information so that we don't lose anything important or create misleading results.

**Defining crash severity:** We still need to decide exactly how we'll measure crash severity. We could look at the number of injuries, whether someone was injured, or specific injury classifications. The measure we choose could affect our findings, so we'll need to explain how we define severity.

**Incomplete 2026 data:** Since we're using data from 2025 and 2026, we won't have a complete year of information for 2026. Some records could also be updated after we download them. We'll document the dates covered by our datasets and keep track of the versions we're using.

**Other factors affecting crashes:** Road conditions, vehicle types, and driver characteristics aren't the only things that affect crashes. Factors like traffic volume, speed, and driver behavior may also influence how severe an accident is. We might not have enough information to account for everything, so we'll be careful not to make claims about direct causes.

**Large datasets:** Our cleaned datasets contain hundreds of thousands of records, and each CSV is over 50 MB. Because of GitHub's file-size restrictions and our course requirements, we're storing the files in UIUC Box. We'll provide access to the files and include a way to download them as part of our final project workflow.

**Legal and ethical considerations:** We're using publicly available data from the City of Chicago. We'll document where the data came from and review any terms of use. Since the People dataset includes information about individuals involved in crashes, we'll focus on overall patterns rather than trying to identify specific people.

**Reproducibility:** Right now, our cleaning work is organized in Python notebooks. For the final project, we'll need to make sure the workflow can be reproduced without having to manually change file paths or run everything separately. We'll also document the packages and software needed.

## 7. Gaps

Although we've made progress with collecting and cleaning our data, there are still a few things we need to figure out before the final submission.

First, we need to decide exactly which variables from the Vehicles and People datasets we want to include when combining everything. Since multiple vehicles and people can be involved in one crash, we need to find a way to summarize this information without losing important details.

We also need to finalize how we'll measure crash severity. We're considering injury counts and injury classifications, but we want to make sure whichever measure we choose is reliable and has enough complete data to work with.

Another thing we haven't completed yet is the post-integration quality assessment. Once we've merged the datasets, we'll need to check for unmatched records, duplicates, and missing values to make sure the final dataset makes sense.

Finally, we still need to finish the automated workflow and documentation. This includes organizing our scripts, adding software dependencies, creating metadata, and testing everything from a fresh copy of our GitHub repository. These steps will be important for making sure someone else can reproduce our project without needing additional instructions from us.
