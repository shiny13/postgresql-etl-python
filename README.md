# PostgreSQL ETL Process with Python

## Purpose 
A startup called Sparkify wants to analyze data for their music streaming app which produces a lot of data in log file format. They want to analyze mainly what songs the users listen to but they don't have an easy query for their data. Their data exists as logs user activity logs and JSON metadata on the songs. 

The purpose of this project is to produce a star-schema with a fact table to produce simple queries to analyse user's information associated with songs and albums and multiple dimension table which contain further details from the fact table. 

## Proejct description
The following project contains an ETL process to create and populate a PostgreSQL database using Python from some JSON log files. The ETL pipeline will process the songs data and user activity data from the log files and populate the various dimension tables, then finally populate the fact table to produce analytical data for the music streaming application.

## Run the ETL process
Run the following two files using the python3 command (python can also be used but for the further of this project python3 was used): 
```
python3 create_tables.py
python3 etl.py
```

## File description
- create_tables.py: Clean previous schema and creates tables.
- sql_queries.py: All queries used in the ETL pipeline.
- etl.py: Read JSON logs and JSON metadata and load the data into generated tables.

### Schema description
**Fact Table**
1. songplays - records in log data associated with song plays i.e. records with page NextSong
```
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
```
**Dimension Tables**
1. users - users in the app
```
user_id, first_name, last_name, gender, level
```
2. songs - songs in music database
```
song_id, title, artist_id, year, duration
```
3. artists - artists in music database
```
artist_id, name, location, latitude, longitude
```
4. time - timestamps of records in songplays broken down into specific units
```
start_time, hour, day, week, month, year, weekday
```
