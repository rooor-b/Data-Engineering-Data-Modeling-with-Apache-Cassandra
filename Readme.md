# Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. 

# Project Overview
In this project, I'll apply what I've learned on data modeling with Apache Cassandra and complete an ETL pipeline using Python. I model sparkify's music history data data by creating tables in Apache Cassandra to run queries.The ETL pipeline was provided which  transfers data from a set of CSV files within a directory to create a streamlined CSV file to model and insert data into Apache Cassandra tables.

# Datasets
data was extracted from event directory which contains multiple csv files into one csv file called event_datafile_new.csv
```
event_data/2018-11-08-events.csv
event_data/2018-11-09-events.csv
```

# Project Steps
Below are steps that I make to complete the project.

## Modeling Apache Cassandra database  and ETL pipeline

1. ETL pipeline step : iterate through each event file in event_data to process and create a new CSV file in Python  called event_datafile_new.csv 
2. Create Cassandra keyspace called "sparkify" and make a connection to it.
3. Create tables to answer the queries outlined in the project template with proper primay and clustering keys.I used **If not exists** to create tables only if the tables do not already exist
    - music_library for query1
    - user_music_library for query2
    - user_songs_library for query3
4. ETL pipeline step Load the data with ```INSERT``` statement for each of the tables from csv file with the right selection of columns.
5. Test queries by running the proper select statements with the correct ```WHERE``` clause
6. Drop tables at the end before closing the session
7. Close the session and cluster connection