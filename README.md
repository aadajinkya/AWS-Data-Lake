# Problem Statement

A music streaming startup, Sparkify, has grown their user base and song database even more and want to move their data warehouse to a data lake. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

You are tasked with building an ETL pipeline that extracts their data from S3, processes them using Spark, and loads the data back into S3 as a set of dimensional tables.


# Objectives

- Define fact and dimension table for star schema for a particular analytic focus.
- To implement ETL pipeline to extract data from S3, process it using spark and load it back into S3


# Dataset

Datasets reside in S3. Here are the S3 links for each:
- Song data: s3://udacity-dend/song_data
- Log data: s3://udacity-dend/log_data


# Database Schema

### Fact Table
#### songplay_table : records in event data associated with song plays i.e. records with page NextSong 
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension tables:
#### users : users in the app
user_id, first_name, last_name, gender, level

#### songs : songs in music database
song_id, title, artist_id, year, duration

#### artists : artists in music database
artist_id, name, location, lattitude, longitude

#### time - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday


# File structure

- **etl.py:** reads data from S3, processes that data using Spark, and writes them back to S3 
- **dl.cfg:** contains your AWS credentials


# Running the project:
- Load credentials in the dl.cfg file
- Create S3 bucket where the output will be stored
- Run the python file
