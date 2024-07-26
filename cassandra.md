# Cassandra

## Task: 

* To create one database in Cassandra with data based on a chosen case study (a column-family with at least 7 columns and 30-40 rows).
  
* To implement at least 10 different queries on that data. The data and queries are to demonstrate appropriate variety and complexity.
  
## Solution:

Started the Cassandra CQL shell from the terminal:
```
cqlsh
```

Created a database (keyspace) whose name is “rell_db” and connected to it:
```
CREATE KEYSPACE rell_db WITH replication = {'class':'SimpleStrategy', 'replication_factor':1};
USE rell_db;
```

Created a table (column family) “rell_countries” with the following columns:
1)	SNo of type int
2)	Country of type String
3)	Continent of type String
4)	Currency of type String
5)	Language of type String
6)	Independence of type date
7)	NRate of type double
```
CREATE TABLE rell_countries (
  SNo int PRIMARY KEY,
  Country varchar,
  Continent varchar,
  Currency varchar,
  Language varchar,
  Independence DATE,
  NRate double
);
```

Queried the database to see the column family created: 
```
SELECT * FROM rell_countries;
```
![cassandra1](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic1.png)

Inserted the following 35 rows of data to the “rell_countries” column family:
```
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (2, 'UK', 'Europe', 'Pound Sterling', 'English', '1399-10-13', 1135.25);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (2, 'UK', 'Europe', 'Pound Sterling', 'English', '1399-10-13', 1135.25);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (3, 'France', 'Europe', 'Euro', 'French', '1789-07-14', 967.26);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (4, 'Germany', 'Europe', 'Euro', 'German', '1949-05-23', 967.26);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (5, 'Canada', 'America', 'Canadian Dollar', 'English', '1867-07-01', 666.62);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (6, 'Poland', 'Europe', 'Polish Zloty', 'Polish', '1918-11-11', 221.48);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (7, 'Austria', 'Europe', 'Euro', 'Austrian', '1955-05-15', 967.26);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (8, 'Australia', 'Oceania', 'Australian Dollar', 'English', '1986-03-03', 588.23);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (9, 'Russia', 'Europe', 'Russian Rubble', 'Russian', '1990-06-12', 10.01);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (10, 'China', 'Asia', 'Chinese Yuan', 'Chinese', '1949-09-21', 128.20);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (11, 'Portugal', 'Europe', 'Euro', 'Portuguese', '1640-12-01', 967.26);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (12, 'Spain', 'Europe', 'Euro', 'Spanish', '1516-03-14', 967.26);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (13, 'Mexico', 'America', 'Mexican Peso', 'Spanish', '1821-09-27', 52.63);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (14, 'Brazil', 'America', 'Brazilian Real', 'Portuguese', '1822-09-07', 180.46);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (15, 'Mali', 'Africa', 'CFA Franc', 'French', '1960-09-22', 1.50);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (16, 'South Korea', 'Asia', 'South Korean Won', 'Korean', '1945-08-15', 0.68);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (17, 'Togo', 'Africa', 'CFA Franc', 'French', '1960-04-12', 1.50);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (18, 'Ghana', 'Africa', 'Ghanaian Cedi', 'English', '1957-03-06', 102.50);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (19, 'South Africa', 'Africa', 'South African Rand', 'Afrikaans', '1910-05-31', 65.59);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (20, 'Egypt', 'Africa', 'Egyptian Pound', 'Arabic', '1922-03-15', 40.48);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (21, 'Cameroon', 'Africa', 'CFA Franc', 'French', '1961-10-01', 1.50);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (22, 'Kenya', 'Africa', 'Kenyan Shilling', '7.79', '1963-12-12', 5.52);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (23, 'UAE', 'Asia', 'AED', 'Arabic', '1971-12-02', 340.46);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (24, 'Israel', 'Asia', 'Israeli New Shekel', 'Hebrew', '1948-05-14', 340.54);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (25, 'India', 'Asia', 'Indian Rupee', 'Hindi', '1947-08-15', 15.06);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (26, 'Pakistan', 'Asia', 'Pakistani Rupee', 'Urdu', '1947-08-14', 4.47);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (27, 'Afghanistan', 'Asia', 'Afghan Afghani', 'Pashto', '1919-08-19', 17.54);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (28, 'Kazakhstan', 'Asia', 'Kazakhstani Tenge', 'Russian', '1991-12-16', 2.74);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (29, 'Kyrgyzstan', 'Asia', 'Kyrgyzstani Som', 'Russian', '1991-08-31', 13.98);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (30, 'Turkmenistan', 'Asia', 'Turkmenistani Manat', 'Turkmen', '1991-10-27', 356.92);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (31, 'Uzbekistan', 'Asia', 'Uzbekistani Som', 'Uzbek', '1991-08-31', 0.10);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (32, 'Tajikistan', 'Asia', 'Tajikistani Somoni', 'Tajik', '1991-09-09', 114.34);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (33, 'Ukraine', 'Europe', 'Ukrainian Hryvnia', 'Ukrainian', '1991-08-24', 33.26);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (34, 'Azerbaijan', 'Asia', 'Azerbaijani Manat', 'Azerbaijani', '1991-08-30', 735.59);
INSERT INTO rell_countries (SNo, Country, Continent, Currency, Language, Independence, NRate) VALUES (35, 'Bahrain', 'Asia', 'Bahraini Dinar', 'Arabic', '1971-08-15', 3317.95);
```
![cassandra2](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic2.png)

## Queries:

Q1: Queried the database for all records: 
```
SELECT * FROM rell_countries;
```
![cassandra3](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic3.png)

Q2: Returned the first 10 data: 
```
SELECT * FROM rell_countries LIMIT 10;
```
![cassandra4](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic4.png)

Q3: Returned the list of Continents: 
```
SELECT Continent FROM rell_countries;
```
![cassandra5](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic5.png)

Q4: Checked how many rows of data that are there in the table: 
```
SELECT COUNT(*) FROM rell_countries ALLOW FILTERING;
```
![cassandra6](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic6.png)

Q5: Returned the Countries that speaks English: 
```
SELECT Country FROM rell_countries WHERE Language = “English” ALLOW FILTERING;
```
![cassandra7](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic7.png) 

Q6: Returned the number of countries that speak French:
```
SELECT COUNT(*) FROM rell_countries WHERE Language = ‘French’ ALLOW FILTERING;
```
![cassandra8](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic8.png)

Q7: Computed the average value of the NRate column for countries in Africa: 
```
SELECT AVG(NRate) AS Average_NRate FROM rell_countries WHERE Continent = “Africa” ALLOW FILTERING;
```

Q8, 9: Created index on the Continent and NRate columns which will be frequently used for filtering: 
```
CREATE INDEX ON rell_countries(Continent);
CREATE INDEX ON rell_countries(NRate);
```
![cassandra9](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic9.png)

Q10: Returned the countries in Africa continent whose NRate is less than the average NRate (31.23) of the countries in that same continent:
```
SELECT Country FROM rell_countries WHERE Continent = “Africa” AND NRate < 31.23;
```
![cassandra10](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/cassandra/cassandra-pic10.png)
