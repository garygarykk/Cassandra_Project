# Data Modeling with Postgres
The aim of this project is to create a relational database in Postgresql with optimized queries for data retrieval (ETL) and data analysis.

A star schema optimized for queries on song play analysis based on song and log datasets is created.

## Star Schema:
> ### Fact Table
>> 1. songplays - records in log data associated with song plays i.e. records with page NextSong
>>> - songplay_id (PRIMARY KEY)
>>> - start_time (Dimension table - time)
>>> - user_id (Dimension table - users)
>>> - level
>>> - song_id (Dimension table - songs)
>>> - artist_id (Dimension table - artists)
>>> - session_id
>>> - location
>>> - user_agent

> ### Dimension Tables
>> 1. users - users in the app
>>> - user_id (PRIMARY KEY)
>>> - first_name
>>> - last_name
>>> - gender
>>> - level
>> 2. songs - songs in music database
>>> - song_id (PRIMARY KEY)
>>> - title
>>> - artist_id
>>> - year
>>> - duration
>> 3. artists - artists in music database
>>> - artist_id (PRIMARY KEY)
>>> - name
>>> - location
>>> - latitude
>>> - longitude
>>4. time - timestamps of records in songplays broken down into specific units
>>> - start_time (PRIMARY KEY)
>>> - hour
>>> - day
>>> - week
>>> - month
>>> - year
>>> - weekday

## Files details and descriptions:
- | data 
    - | song_data
      - | ...
    - | log_data
      - | ...
- | sql_queries.py
- | create_tables.py
- | etl.ipynb
- | test.ipynb
- | etl.py
- | testing-final.ipynb
  
### `data`
Folder that contains `song_data` and `log_data` files which are the dataset in JSON format.
### `sql_queries.py`
Python file with SQL queries of dropping, creating and inserting queries in Postgresql database.
### `create_tables.py`
Python file with functions creating the database and excuting the queries in `sql_queries.py` file.
### `etl.ipynb`
Jupyter notebook that excutes `create_tables.py` file and processes testing data from JSON to database (ETL testing).
### `test.ipynb` 
Jupyter notebook that confirms the creation of database and tables after entering testing data.
### `etl.py`
Python file with ETL functions based on `etl.ipynb` to process all the data in `song_data` and `log_data` files.
### `testing-final.ipynb`
Jupyter notebook that confirms the creation of database and tables after the whole ETL process.