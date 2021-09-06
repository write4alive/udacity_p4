Data Engineering Nano Degree Programm of Udacity - Project 4 -<br>
<h2>Project: Data Lake</h2>
<br>
Introduction<br>
A music streaming startup, Sparkify, has grown their user base and song database even more and want to move their data warehouse to a data lake. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.<br>
<br>
As their data engineer, you are tasked with building an ETL pipeline that extracts their data from S3, processes them using Spark, and loads the data back into S3 as a set of dimensional tables. This will allow their analytics team to continue finding insights in what songs their users are listening to.<br>
<br>
You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.<br>
<br>
<h2>Project Description</h2>
In this project, you'll apply what you've learned on Spark and data lakes to build an ETL pipeline for a data lake hosted on S3. To complete the project, you will need to load data from S3, process the data into analytics tables using Spark, and load them back into S3. You'll deploy this Spark process on a cluster using AWS.<br>
<br>
<br>
<h2>Project Datasets</h2>
You'll be working with two datasets that reside in S3. Here are the S3 links for each:<br>
<br>
Song data: s3://udacity-dend/song_data<br>
Log data: s3://udacity-dend/log_data<br>
<br>
Song Dataset
The first dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID. For example, here are filepaths to two files in this dataset.<br>
<br>
song_data/A/B/C/TRABCEI128F424C983.json<br>
song_data/A/A/B/TRAABJL12903CDCF1A.json<br>
And below is an example of what a single song file, TRAABJL12903CDCF1A.json, looks like.<br>
<br>
{"num_songs": 1, "artist_id": "ARJIE2Y1187B994AB7", "artist_latitude": null, "artist_longitude": null, "artist_location": "", "artist_name": "Line Renaud", "song_id": "SOUPIRU12A6D4FA1E1", "title": "Der Kleine Dompfaff", "duration": 152.92036, "year": 0}<br>
<br>
Log Dataset
The second dataset consists of log files in JSON format generated by this event simulator based on the songs in the dataset above. These simulate app activity logs from an imaginary music streaming app based on configuration settings.<br>
<br>
The log files in the dataset you'll be working with are partitioned by year and month. For example, here are filepaths to two files in this dataset.<br>
<br>
log_data/2018/11/2018-11-12-events.json<br>
log_data/2018/11/2018-11-13-events.json<br>

And below is an example of what the data in a log file, 2018-11-12-events.json, looks like.<br>
![log-data](https://user-images.githubusercontent.com/16669517/132220518-e54fe8ba-ef03-45ee-aee9-12bd14a47631.png)
<br>
Schema for Song Play Analysis
Using the song and log datasets, you'll need to create a star schema optimized for queries on song play analysis. This includes the following tables.
<br>
Fact Table<br>
songplays - records in log data associated with song plays i.e. records with page NextSong<br>
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
<br>
Dimension Tables<br>
<br>
users - users in the app<br>
user_id, first_name, last_name, gender, level<br>
<br>
songs - songs in music database<br>
song_id, title, artist_id, year, duration<br>
<br>
artists - artists in music database<br>
artist_id, name, location, lattitude, longitude<br>
<br>
time - timestamps of records in songplays broken down into specific units<br>
start_time, hour, day, week, month, year, weekday<br>
<br>
Project Template
To get started with the project, go to the workspace on the next page, where you'll find the project template. You can work on your project with a smaller dataset found in the workspace, and then move on to the bigger dataset on AWS.

Alternatively, you can download the template files in the Resources tab in the classroom and work on this project on your local computer.

The project template includes three files:

etl.py reads data from S3, processes that data using Spark, and writes them back to S3
dl.cfgcontains your AWS credentials
README.md provides discussion on your process and decisions
