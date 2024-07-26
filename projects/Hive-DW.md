# Hive Data Warehouse Design

## Task:

* To design a data warehouse in Hive with data (a collection with at least 50 records in at least 3 tables).
  
* To implement 10 different queries on that data. The data and queries are to show adequate variety and complexity.

## Solution:

Note: If the screenshots in this section are not showing, you can get the PDF [here.](https://drive.google.com/file/d/1AAxjsQcdoAWdtTU8KKCLaT1hYYsFnYMQ/view?usp=sharing)

Got the Hadoop environment started from the terminal for the Hive data warehouse implementation. 
Created a new directory called “assignment” to be the current working directory:
```
start-dfs.sh

start-yarn.sh

cd ../workspace

mkdir assignment

cd assignment
```
![hive-dw1](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic1.png)

Four (4) CSV files, “artistes.csv”, “songs.csv”, “albums.csv”, and “labels.csv” have been created for the purpose of this task to contain 50, 54, 53, and 37 rows of data respectively. 
These files were placed in the Hadoop environment (the commands were run from the terminal):
```
hdfs dfs -put artistes.csv

hdfs dfs -put songs.csv

hdfs dfs -put albums.csv

hdfs dfs -put labels.csv
```
![hive-dw2](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic2.png)

Made sure there were no pre-existing database(s) in the current working directory in Hadoop:
```
hive -e "SHOW DATABASES"
```

Started the Hive command line interface:
```
hive
```
![hive-dw3](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic3.png)

Created a database “assignment_db” in Hive for this task:
```
CREATE DATABASE assignment_db;

SHOW DATABASES;
```
![hive-dw4](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic4.png)

Switched to the newly created Hive database:
```
USE assignment_db;
```

Created four (4) tables for the data warehouse implementation in Hive:
```
CREATE TABLE artistes (
  origin STRING, artiste STRING, age INT, gender STRING, marital STRING
  ) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' STORED AS TEXTFILE;

CREATE TABLE songs (
  genre STRING, song STRING, artiste STRING, album STRING, label STRING
  ) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' STORED AS TEXTFILE;

CREATE TABLE albums (
  year INT, album STRING, tracks INT, label STRING, rating STRING
  ) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' STORED AS TEXTFILE;

CREATE TABLE labels (
  origin STRING, label STRING, owner STRING, records INT
  ) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' STORED AS TEXTFILE;
```
![hive-dw5](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic5.png)

Queried the list of tables created in the Hive data warehouse:
```
SHOW TABLES;
```
![hive-dw6](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic6.png)

Inserted all rows of data from each of the four (4) CSV files into their corresponding tables in the Hive data warehouse:
```
LOAD DATA INPATH 'artistes.csv' OVERWRITE INTO TABLE artistes;

LOAD DATA INPATH 'songs.csv' OVERWRITE INTO TABLE songs;

LOAD DATA INPATH 'albums.csv' OVERWRITE INTO TABLE albums;

LOAD DATA INPATH 'labels.csv' OVERWRITE INTO TABLE labels;
```
![hive-dw7](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic7.png)

## Queries

Q1 - Returned the oldest and latest of the Years of the music Albums:
```
SELECT
  MIN(year) AS Oldest_Year,
  MAX(year) AS Latest_Year
FROM
  albums;
```
![hive-dw8](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic8.png)

Q2 - Returned the maximum, minimum, and average Age of musical Artistes:
```
SELECT
  MIN(age) AS Minimum_Age,
  AVG(age) AS Average_Age,
  MAX(age) AS Maximum_Age
FROM
  artistes;
```
![hive-dw9](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic9.png)

Q3 - Returned the number of record Labels per label Owner:
```
SELECT
  owner AS Owner,
  COUNT(label) AS Labels
FROM
  labels
GROUP BY
  owner
ORDER BY
  Labels DESC;
```
![hive-dw10](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic10.png)
![hive-dw11](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic11.png)

Q4 – Returned the “Independent” record labels and their countries of origin:
```
SELECT
  label AS Labels,
  origin AS Country
FROM
  labels
WHERE
  owner = “Independent”;
```
![hive-dw12](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic12.png)

Q5 - Returned the maximum, minimum, and average of the Rating and Tracks of music Albums:
```
SELECT
  MIN(rating) AS Minimum_Rating,
  AVG(rating) AS Average_Rating,
  MAX(rating) AS Maximum_Rating,
  MIN(tracks) AS Minimum_Tracks,
  AVG(tracks) AS Average_Tracks,
  MAX(tracks) AS Maximum_Tracks
FROM
  albums;
```
![hive-dw13](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic13.png)

Q6 - Returned the maximum, minimum, and average album Records produced by record Labels:
```
SELECT
  MIN(records) AS Lowest_Records,
  AVG(records) AS Average_Records,
  MAX(records) AS Highest_Records
FROM
  labels;
```
![hive-dw14](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic14.png)

Q7 - Returned the number of Songs per Year (sorted in descending order of the Year):
```
SELECT
  year AS Year,
  COUNT(song) AS Songs
FROM
  albums a
JOIN
  songs s
ON
  (a.album = s.album)
GROUP BY
  year
ORDER BY
  Year DESC;
```
![hive-dw15](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic15.png)

Q8 - Returned the number of Songs, music Albums, and Genre(s) per musical Artiste as well as (top 10 highest by Songs):
```
SELECT
  a.artiste AS Artiste,
  COUNT(song) AS Songs,
  COUNT(album) AS Albums,
  COUNT(genre) AS Genres
FROM
  artistes a
JOIN
  songs s
ON
  (a.artiste = s.artiste)
GROUP BY
  a.artiste
ORDER BY
  Songs DESC
LIMIT 10;
```
![hive-dw16](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic16.png)
![hive-dw17](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic17.png)

Q9 - Returned the number of Songs, music Albums, musical Artistes, average Age, and average Rating per Gender:
```
SELECT
  gender AS Gender,
  COUNT(song) AS Songs,
  COUNT(al. album) AS Albums,
  COUNT(s.artiste) AS Artistes,
  AVG(age) AS Average_Age,
  AVG(rating) AS Average_Rating
FROM
  artistes a
JOIN
  songs s
ON
  (a.artiste = s.artiste)
JOIN
  albums al
ON
  (s.album = al.album)
GROUP BY
  gender
ORDER BY
  Songs DESC;
```
![hive-dw18](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic18.png)

Q10 - Returned the number of Songs, music Albums, Genre(s), average Age, average Rating, and musical Artistes (male/female) per Marital status:
```
SELECT
  marital AS Marital,
  COUNT(song) AS Songs,
  COUNT(al.album) AS Albums,
  COUNT(genre) AS Genres,
  AVG(age) AS Average_Age,
  AVG(rating) AS Average_Rating,
  COUNT(s.artiste) AS Artistes,
  SUM(Male) AS Males,
  SUM(Female) AS Females
FROM
  (
  SELECT
    marital,
    age,
    artiste,
    CASE WHEN gender = 'Male'
      THEN 1
      ELSE 0
    END AS Male,
    CASE WHEN gender = 'Female'
      THEN 1
      ELSE 0
    END AS Female
  FROM
    artistes
  ) sub
  JOIN
    songs s
  ON
    (sub.artiste = s.artiste)
  JOIN
    albums al
  ON
    (s.album = al.album)
  GROUP BY
    marital
  ORDER BY
    Artistes;
```
![hive-dw19](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic19.png)

Q11 - Returned the number of Songs, music Albums, Genre(s), record Labels, number of Records sold, total Rating, average Rating, average Age, and number of musical Artistes (male and female) per Country of Origin (top 10):
```
SELECT
  l.origin AS Country,
  COUNT(song) AS Songs,
  COUNT(al.album) AS Albums,
  COUNT(genre) AS Genres,
  COUNT(l.label) AS Labels,
  SUM(records) AS Records_Sold,
  SUM(rating) AS Total_Rating,
  AVG(rating) AS Average_Rating,
  AVG(age) AS Average_Age,
  COUNT(s.artiste) AS Artistes,
  SUM(Male) AS Males,
  SUM(Female) AS Females
FROM
  (
  SELECT
    origin,
    age,
    artiste,
    CASE WHEN gender = 'Male'
      THEN 1
      ELSE 0
    END AS Male,
    CASE WHEN gender = 'Female'
      THEN 1
      ELSE 0
    END AS Female
  FROM
    artistes
  ) sub
  JOIN
    songs s
  ON
    (sub.artiste = s.artiste)
  JOIN
    albums al
  ON
    (s.album = al.album)
  JOIN
    labels l
  ON
    (al.label = l.label)
  GROUP BY
    l.origin
  ORDER BY
    Artistes DESC
  LIMIT 10;
```
![hive-dw20](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic20.png)

Q12 - Returned the number of Songs, music Albums, record Labels, number of Records sold, total Rating, average Rating, average Age, Countries of Origin, and number of musical Artistes (male and female) per music Genre:
```
SELECT
  genre AS Genre,
  COUNT(song) AS Songs,
  COUNT(al.album) AS Albums,
  COUNT(genre) AS Genres,
  COUNT(l.label) AS Labels,
  SUM(records) AS Records_Sold,
  SUM(rating) AS Total_Rating,
  AVG(rating) AS Average_Rating,
  AVG(age) AS Average_Age,
  COUNT(l.origin) AS Countries,
  COUNT(s.artiste) AS Artistes,
  SUM(Male) AS Males,
  SUM(Female) AS Females
FROM
  (
  SELECT
    origin,
    age,
    artiste,
    CASE WHEN gender = 'Male'
      THEN 1
      ELSE 0
    END AS Male,
    CASE WHEN gender = 'Female'
      THEN 1
      ELSE 0
    END AS Female
  FROM
    artistes
    ) sub
  JOIN
    songs s
  ON
    (sub.artiste = s.artiste)
  JOIN
    albums al
  ON
    (s.album = al.album)
  JOIN
    labels l
  ON
    (al.label = l.label)
  GROUP BY
    genre
  ORDER BY
    Artistes DESC
  LIMIT 10;
```
![hive-dw21](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic21.png)

Q13 - Returned the number of Songs, music Albums, total Rating, average Rating, average Age, and musical Artistes (males/females) per record Label:
```
SELECT
  l.label AS Label,
  COUNT(s.song) AS Songs,
  COUNT(al.album) AS Albums,
  SUM(rating) AS Total_Rating,
  AVG(rating) AS Average_Rating,
  AVG(age) AS Average_Age,
  COUNT(s.artiste) AS Artistes,
  SUM(Male) AS Males,
  SUM(Female) AS Females
FROM
  (
  SELECT
    age,
    artiste,
    CASE WHEN gender = 'Male'
      THEN 1
      ELSE 0
    END AS Male,
    CASE WHEN gender = 'Female'
      THEN 1
      ELSE 0
    END AS Female
  FROM
    artistes
    ) sub
  JOIN
    songs s
  ON
    (sub.artiste = s.artiste)
  JOIN
    albums al
  ON
    (s.album = al.album)
  JOIN
    labels l
  ON
    (al.label = l.label)
  GROUP BY
    l.label
  ORDER BY
    Artistes DESC
  LIMIT 10;
```
![hive-dw22](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/hive/hive-pic22.png)
