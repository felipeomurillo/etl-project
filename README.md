# etl-project
Extract, transform and load!

# Project Proposal
Imagine a scenario where a bunch of data came in and you and your team are tasked with migrating it to a
production data base.

# Finding Data
Data chosen belong to kaggle, subject killings by US police.

Data Source: https://www.kaggle.com/kwullum/fatal-police-shootings-in-the-us/¶

a.- PoliceKillingsUS.csv
b.- ShareRaceByCity.csv
c.- PercentOver25CompletedHighSchool.csv
d.- PercentagePeopleBelowPovertyLevel.csv
e.- MedianHouseholdIncome2015.csv

# Data Cleanup & Analysis

From the collected database are relational due all of them had State and city, however cities had different format, ex: Atlanta City on ShareRaceByCity.csv and Atlanta City city on PoliceKillingsUS.csv

First thing was to set all columns of 'city' with the same format and delete the duplicated or unnecessary words.
* For this step we used pandas process such as split and replace to get specifically the words we needed

After being sure all the 'city' columns has the same format we used QuickDBD to see the relationship between tables getting to the confirming that the data we where using is relational and therefore SQL as chosen the database to use.

But also, this action let us see that there was a lot of “duplicated” rows in each table, so, there was needed to clean the DataFrames in order to have a more lean information so we created a City_df that set a city_id and apply this one to every other dataframe we created to make it cleaner.

Once getting all the DataFrames as we expected to start  an analysis
* Created the DB manually on PostgreSQL
* Created the connection to PostgreSQL
* Create each of the 5 tables 
* Confirm tables and information is at the the db by looking directly at the PostgreSQL program and with pandas.

# Regards Team F
