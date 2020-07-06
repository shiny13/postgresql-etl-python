# PostgreSQL ETL Process with Python

## Proejct description
The following project contains an ETL process to create and populate a PostgreSQL database using Python from some JSON log files. 

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

### File description
The sql_queries.py file is responsible for declaring the raw SQL statements for creating the tables' schema, insert statements, and select queries.

the create_tables.py file contain python functions responsible to call the database to execute all the queries defined in the sql_queries.py file.

The etl.py file contains python functions to pull data from the source to populate the PostgreSQL tables.

You may use Jupyter notebook to execute the etl.ipynb file to call all the python files to execute them and the test.ipynb fiel for testing. 

