# AWS-ETL-DataLake-S3-SongsPlaylist
Load data from S3 bucket, process on PySpark cluster and push the data to S3 Datalake
### Description

This repository contains the ETL pipeline designed to populate the Sparkifydb AWS S3 Data Lake using Spark. The purpose of this database is to help Sparkify address various business questions about its users, the songs they listen to, and the artists behind those songs, using the available log and file data. This database provides a consistent and reliable source for storing such information, enabling Sparkify to achieve several analytical objectives, such as identifying popular songs or peak traffic times during the day.

### Dependencies

Ensure you have the `pyspark` library installed. Additionally, you need an operational Spark cluster, either locally or on AWS EMR.

### Database Design and ETL Pipeline

The STAR schema is employed to streamline queries and facilitate rapid data aggregation. Python is chosen for the ETL pipeline due to its rich libraries like pandas, which simplify data manipulation. The ETL process involves extracting files from S3 and processing data using PySpark. There are two primary types of data: song and log data. 

- **Song data** includes information about songs and artists, which are loaded into the songs and artists dimension tables, respectively.
- **Log data** includes information on user sessions, which are loaded into the time and users dimension tables and the songplays fact table.

### Running the ETL Pipeline

Run `etl.py` to read the song and log JSON files, denormalize the data into fact and dimension tables, and export these tables to S3 as Parquet files.
