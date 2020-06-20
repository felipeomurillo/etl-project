# etl-project
Extract, transform and load!

# Project Proposal
Imagine a scenario where a bunch of data came in and you and your team are tasked with migrating it to a
production data base.

# Finding Data
The team decided to tackle data about current U.S. events regarding police shootings. The team found a useful data set in kaggle (in form of static CSVs). The team acknowledges that static data lends itself to aging and ideally data shoudl be coming from API to stay more current.

Data Source: https://www.kaggle.com/kwullum/fatal-police-shootings-in-the-us/¶

Data Sets:
1. PoliceKillingsUS.csv
1. ShareRaceByCity.csv
1. PercentOver25CompletedHighSchool.csv
1. PercentagePeopleBelowPovertyLevel.csv
1. MedianHouseholdIncome2015.csv

# Data Cleanup & Analysis

All dataset collected share geolocation data: city and state. However, cities had different format, ex: Atlanta City on ShareRaceByCity.csv and Atlanta City city on PoliceKillingsUS.csv

First thing, was to assign a unique city ID to a specific geolocation (city, city type, state combination). The city dataframe was used to assign IDs to all datasets. Formatting and extraction was then perfromed with pandas to clean up indvidual city entries.

* For this step we used pandas process such as split and replace to get specifically the words we needed

After being sure all the 'city' columns have the same format we decided to use SQL vs MongoDB because the data used is well structured, despite the cleaning process we performed. Additionally, we use the QuickDBD schema in order to build the relationship model that bonds the five tables.

This action let us see that there was a lot of “duplicated” rows in each table, so it was required to clean the DataFrames in order to have a more lean information. Therefore, we created a City_df that set a city_id and apply this one to every other dataframe we created to make it cleaner.
* The reason behind leaving 5 tables instead of concatenating or merging them into 2 or 3 is that after a close review of each table we can see that not all 'city_id's are on each table, so if we merge them we will have NA or lose some data. We wanted to keep all data available, when new city data becomes available, we can populate income data even when educational data may not be available.

Once getting all the DataFrames as we expected to start  an analysis
* Created the DB manually on PostgreSQL
* Created the connection to PostgreSQL via SQLAlchemy
* Created each of the 5 tables 
* Confirm table contents by looking directly at the PostgreSQL program and with SQLAlchemy (making queries to said tables.

# Regards Team F
