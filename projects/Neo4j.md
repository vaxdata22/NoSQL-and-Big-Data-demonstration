# Neo4j

## Task: 

* To create one Graph database using either Neo4J with data based on a chosen case study (at least 25 nodes with relationships).
  
* To implement at least 10 different queries on that data. The data and queries are to demonstrate appropriate variety and complexity. 

## Solution:

Quickly checked for and made sure there were no existing data (nodes) in the new graph database before starting to create nodes using the Neo4J browser; this command would essentially return no nodes:
```
MATCH (n) RETURN n
```
![neo4j1](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic1.png)

Inserted the following 30 nodes into the new graph database:
```
MERGE (
	person: Pharell
	  {
  Full_name: 'Pharell Isodje',
  Age: 32,
  Net_worth: 750000.00,
  Occupation: 'CEO'
  }
); 

MERGE (
    person: Dorcas
	  {
  Full_name: 'Dorcas Isodje',
  Age: 28,
  Net_worth: 250000.00,
  Occupation: 'CFO'
  }
); 

MERGE (
	person: Donatus
	  {
  Full_name: 'Donatus Enebuse',
  Age: 35,
  Net_worth: 350000.00,
  Occupation: 'COO'
  }
); 

MERGE (
	person: Jeff
	  {
  Full_name: 'Jefferson Daniels',
  Age: 30,
  Net_worth: 250000.00,
  Occupation: 'CTO'
  }
); 

MERGE (
	person: Atiku
  	{
  Full_name: 'Atiku Abubakar',
  Age: 75,
  Net_worth: 80000000.00,
  Occupation: 'Politician'
  }
); 

MERGE (
	person: Emilokan
  	{
  Full_name: 'Bola Tinubu',
  Age: 79,
  Net_worth: 85000000.00,
  Occupation: 'Politician'
  }
); 

MERGE (
	person: Bubu
  	{
  Full_name: 'Muhammadu Buhari',
  Age: 76,
  Net_worth: 8000000.00,
  Occupation: 'Politician'
  }
); 

MERGE (
	person: OBJ
  	{
  Full_name: 'Olusegun Obasanjo',
  Age: 78,
  Net_worth: 28000000.00,
  Occupation: 'Politician'
  }
); 

MERGE (
	person: Mark
  	{
  Full_name: 'Mark Zuckerberg',
  Age: 37,
  Net_worth: 750000000.00,
  Occupation: 'Businessman'
  }
); 

MERGE (
	person: Soros
  	{
  Full_name: 'George Soros',
  Age: 85,
  Net_worth: 250000000.00,
  Occupation: 'Businessman'
  }
); 

MERGE (
	person: Buffet
  	{
  Full_name: 'Warren Buffet',
  Age: 80,
  Net_worth: 350000000.00,
  Occupation: 'Businessman'
  }
); 

MERGE (
	person: Okumagba
  	{
  Full_name: 'Williams Okumagba',
  Age: 88,
  Net_worth: 650000.00,
  Occupation: 'Politician'
  }
); 

MERGE (
	person: Felix
  	{
  Full_name: 'Mamuzo Felix',
  Age: 25,
  Net_worth: 85000.00,
  Occupation: 'Student'
  }
); 

MERGE (
	person: Okpako
  	{
  Full_name: 'Bernard Okpako',
  Age: 81,
  Net_worth: 120000.00,
  Occupation: 'Professional'
  }
); 

MERGE (
	person: Frank
  	{
  Full_name: 'Frank Edoho',
  Age: 48,
  Net_worth: 250000.00,
  Occupation: 'Professional'
  }
); 

MERGE (
	person: Odjegba
  	{
  Full_name: 'Frank Odjegba',
  Age: 50,
  Net_worth: 150000.00,
  Occupation: 'Politician'
  }
); 

MERGE (
	person: Ojugba
  	{
  Full_name: 'Victory Ojugba',
  Age: 30,
  Net_worth: 75000.00,
  Occupation: 'Student'
  }
); 

MERGE (
	person: Omowo
  	{
  Full_name: 'Juliet Ozomaro',
  Age: 45,
  Net_worth: 100000.00,
  Occupation: 'Secretary'
  }
); 

MERGE (
	person: Musk
  	{
  Full_name: 'Elon Musk',
  Age: 56,
  Net_worth: 850000000.00,
  Occupation: 'Businessman'
  }
); 

MERGE (
	person: Dangote
  	{
  Full_name: 'Aliko Dangote',
  Age: 60,
  Net_worth: 200000000.00,
  Occupation: 'Businessman'
  }
); 

MERGE (
  university: 'Greenwich Uni'
  	{
  Name: 'University Of Greenwich',
  Location: 'Greenwich, UK'
  }
); 

MERGE (
  university: Unilorin
  	{
  Name: 'University Of Ilorin',
  Location: 'Ilorin, Nigeria'
  }
); 

MERGE (
  university: UNN
  	{
  Name: 'University Of Nigeria, Nsukka',
  Location: 'Enugu, Nigeria'
  }
); 

MERGE (
  company: 'Rell Inc'
  	{
  Name: 'Rell Investments Inc.',
  Location: 'London, UK'
  }
); 

MERGE (
  company: Keystone
  	{
  Name: 'Keystone Bank PLC',
  Location: 'Lagos, Nigeria'
  }
); 

MERGE (
  business: FOREX
  	{
  Type: 'FOREX Trading',
  Location: 'Global'
  }
); 

MERGE (
  business: Marketing
  	{
  Type: 'Information Marketing',
  Location: 'Global'
  }
); 

MERGE (
  location: UK
  	{
  Country: 'United Kingdom',
  Capital: 'London'
  }
); 

MERGE (
  location: Nigeria
  	{
  Country: 'Nigeria',
  Capital: 'Abuja'
  }
); 

MERGE (
  location: US
  	{
  Country: 'United States',
  Capital: 'Washington DC'
  }
)
```
![neo4j2](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic2.png) 

Checked the nodes to see how many they are in the new graph database:
```
MATCH (n) RETURN n

MATCH (n) RETURN COUNT(*) AS Number_of_nodes
```
![neo4j3](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic3.png)
![neo4j4](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic4.png)

Inserted the following 6 kinds of relationships between certain nodes into the new graph database:
  Relationship 1
  education: 'studied at'
  description: 'university';
  Relationship 2
  work: 'works at'
  description: 'company';
  Relationship 3
  place: 'is in'
  description: 'location';
  Relationship 4
  investing: 'invests in'
  description: 'business';
  Relationship 5
  relative: 'is a relative of'
  description: 'person';
  Relationship 6
  friend: 'is friends with'
  description: 'person';

```
MATCH (person: Pharell), (university: 'Greenwich Uni')
CREATE (person)-[:education]->(university);

MATCH (person: Pharell), (university: Unilorin)
CREATE (person)-[:education]->(university);

MATCH (person: Dorcas), (university: Unilorin)
CREATE (person)-[:education]->(university);

MATCH (person: Donatus), (university: UNN)
CREATE (person)-[:education]->(university);

MATCH (person: Jeff), (university: UNN)
CREATE (person)-[:education]->(university);

MATCH (person: Okumagba), (university: Unilorin)
CREATE (person)-[:education]->(university);

MATCH (person: Okumagba), (university: UNN)
CREATE (person)-[:education]->(university);

MATCH (person: Felix), (university: UNN)
CREATE (person)-[:education]->(university);

MATCH (person: Okpako), (university: Unilorin)
CREATE (person)-[:education]->(university);

MATCH (person: Okpako), (university: UNN)
CREATE (person)-[:education]->(university);

MATCH (person: Frank), (university: Unilorin)
CREATE (person)-[:education]->(university);

MATCH (person: Frank), (university: UNN)
CREATE (person)-[:education]->(university);

MATCH (person: Odjegba), (university: Unilorin)
CREATE (person)-[:education]->(university);

MATCH (person: Ojugba), (university: UNN)
CREATE (person)-[:education]->(university);

MATCH (person: Omowo), (university: 'Greenwich Uni')
CREATE (person)-[:education]->(university);

MATCH (person: Musk), (university: 'Greenwich Uni')
CREATE (person)-[:education]->(university);

MATCH (person: Pharell), (company: 'Rell Inc')
CREATE (person)-[:work]->(company);

MATCH (person: Dorcas), (company: 'Rell Inc')
CREATE (person)-[:work]->(company);

MATCH (person: Donatus), (company: 'Rell Inc')
CREATE (person)-[:work]->(company);

MATCH (person: Jeff), (company: 'Rell Inc')
CREATE (person)-[:work]->(company);

MATCH (person: Okpako), (company: Keystone)
CREATE (person)-[:work]->(company);

MATCH (person: Frank), (company: Keystone)
CREATE (person)-[:work]->(company);

MATCH (person: Omowo), (company: 'Rell Inc')
CREATE (person)-[:work]->(company);

MATCH (person: Pharell), (location: UK)
CREATE (person)-[:place]->(location);

MATCH (person: Dorcas), (location: UK)
CREATE (person)-[:place]->(location);

MATCH (person: Donatus), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Jeff), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Atiku), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Emilokan), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Bubu), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: OBJ), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Mark), (location: US)
CREATE (person)-[:place]->(location);

MATCH (person: Soros), (location: US)
CREATE (person)-[:place]->(location);

MATCH (person: Buffet), (location: US)
CREATE (person)-[:place]->(location);

MATCH (person: Okumagba), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Felix), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Okpako), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Frank), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Odjegba), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Ojugba), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Omowo), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (person: Musk), (location: US)
CREATE (person)-[:place]->(location);

MATCH (person: Dangote), (location: Nigeria)
CREATE (person)-[:place]->(location);

MATCH (university: 'Greenwich Uni'), (location: UK)
CREATE (university)-[:place]->(location);

MATCH (university: Unilorin), (location: Nigeria)
CREATE (university)-[:place]->(location);

MATCH (university: UNN), (location: Nigeria)
CREATE (university)-[:place]->(location);

MATCH (company: 'Rell Inc'), (location: UK)
CREATE (company)-[:place]->(location);

MATCH (company: Keystone), (location: Nigeria)
CREATE (company)-[:place]->(location);

MATCH (person: Pharell), (business: FOREX)
CREATE (person)-[:investing]->(business);

MATCH (person: Pharell), (business: Marketing)
CREATE (person)-[:investing]->(business);

MATCH (person: Dorcas), (business: Marketing)
CREATE (person)-[:investing]->(business);

MATCH (person: Donatus), (business: FOREX)
CREATE (person)-[:investing]->(business);

MATCH (person: Jeff), (business: FOREX)
CREATE (person)-[:investing]->(business);

MATCH (person: Atiku), (business: FOREX)
CREATE (person)-[:investing]->(business);

MATCH (person: OBJ), (business: FOREX)
CREATE (person)-[:investing]->(business);

MATCH (person: Mark), (business: Marketing)
CREATE (person)-[:investing]->(business);

MATCH (person: Soros), (business: FOREX)
CREATE (person)-[:investing]->(business);

MATCH (person: Buffet), (business: FOREX)
CREATE (person)-[:investing]->(business);

MATCH (person: Omowo), (business: Marketing)
CREATE (person)-[:investing]->(business);

MATCH (person: Musk), (business: FOREX)
CREATE (person)-[:investing]->(business);

MATCH (person: Musk), (business: Marketing)
CREATE (person)-[:investing]->(business);

MATCH (person: Dangote), (business: FOREX)
CREATE (person)-[:investing]->(business);

MATCH (university: 'Greenwich Uni'), (business: Marketing)
CREATE (university)-[:investing]->(business);

MATCH (university: Unilorin), (business: Marketing)
CREATE (university)-[:investing]->(business);

MATCH (university: UNN), (business: Marketing)
CREATE (university)-[:investing]->(business);

MATCH (company: 'Rell Inc'), (business: FOREX)
CREATE (company)-[:investing]->(business);

MATCH (company: 'Rell Inc'), (business: Marketing)
CREATE (company)-[:investing]->(business);

MATCH (company: Keystone), (business: Marketing)
CREATE (company)-[:investing]->(business);

MATCH (person: Pharell), (person: Dorcas)
CREATE (person)-[:relative]-(person);

MATCH (person: Pharell), (person: Okumagba)
CREATE (person)-[:relative]-(person);

MATCH (person: Pharell), (person: Felix)
CREATE (person)-[:relative]-(person);

MATCH (person: Pharell), (person: Okpako)
CREATE (person)-[:relative]-(person);

MATCH (person: Pharell), (person: Odjegba)
CREATE (person)-[:relative]-(person);

MATCH (person: Pharell), (person: Omowo)
CREATE (person)-[:relative]-(person);

MATCH (person: Dorcas), (person: Okumagba)
CREATE (person)-[:relative]-(person);

MATCH (person: Dorcas), (person: Felix)
CREATE (person)-[:relative]-(person);

MATCH (person: Dorcas), (person: Okpako)
CREATE (person)-[:relative]-(person);

MATCH (person: Dorcas), (person: Odjegba)
CREATE (person)-[:relative]-(person);

MATCH (person: Dorcas), (person: Omowo)
CREATE (person)-[:relative]-(person);

MATCH (person: Okumagba), (person: Felix)
CREATE (person)-[:relative]-(person);

MATCH (person: Okumagba), (person: Okpako)
CREATE (person)-[:relative]-(person);

MATCH (person: Okumagba), (person: Odjegba)
CREATE (person)-[:relative]-(person);

MATCH (person: Okumagba), (person: Omowo)
CREATE (person)-[:relative]-(person);

MATCH (person: Felix), (person: Okpako)
CREATE (person)-[:relative]-(person);

MATCH (person: Felix), (person: Odjegba)
CREATE (person)-[:relative]-(person);

MATCH (person: Felix), (person: Omowo)
CREATE (person)-[:relative]-(person);

MATCH (person: Okpako), (person: Odjegba)
CREATE (person)-[:relative]-(person);

MATCH (person: Okpako), (person: Omowo)
CREATE (person)-[:relative]-(person);

MATCH (person: Odjegba), (person: Omowo)
CREATE (person)-[:relative]-(person);

MATCH (person: Pharell), (person: Donatus)
CREATE (person)-[:friend]-(person);

MATCH (person: Pharell), (person: Jeff)
CREATE (person)-[:friend]-(person);

MATCH (person: Pharell), (person: Frank)
CREATE (person)-[:friend]-(person);

MATCH (person: Donatus), (person: Jeff)
CREATE (person)-[:friend]-(person);

MATCH (person: Donatus), (person: Felix)
CREATE (person)-[:friend]-(person);

MATCH (person: Donatus), (person: Ojugba)
CREATE (person)-[:friend]-(person);

MATCH (person: Atiku), (person: Emilokan)
CREATE (person)-[:friend]-(person);

MATCH (person: Atiku), (person: Bubu)
CREATE (person)-[:friend]-(person);

MATCH (person: Atiku), (person: OBJ)
CREATE (person)-[:friend]-(person);

MATCH (person: Atiku), (person: Okumagba)
CREATE (person)-[:friend]-(person);

MATCH (person: Atiku), (person: Frank)
CREATE (person)-[:friend]-(person);

MATCH (person: Atiku), (person: Odjegba)
CREATE (person)-[:friend]-(person);

MATCH (person: Atiku), (person: Musk)
CREATE (person)-[:friend]-(person);

MATCH (person: Atiku), (person: Dangote)
CREATE (person)-[:friend]-(person);

MATCH (person: Emilokan), (person: Bubu)
CREATE (person)-[:friend]-(person);

MATCH (person: Emilokan), (person: OBJ)
CREATE (person)-[:friend]-(person);

MATCH (person: Emilokan), (person: Okumagba)
CREATE (person)-[:friend]-(person);

MATCH (person: Emilokan), (person: Frank)
CREATE (person)-[:friend]-(person);

MATCH (person: Emilokan), (person: Odjegba)
CREATE (person)-[:friend]-(person);

MATCH (person: Emilokan), (person: Dangote)
CREATE (person)-[:friend]-(person);

MATCH (person: Bubu), (person: OBJ)
CREATE (person)-[:friend]-(person);

MATCH (person: Bubu), (person: Okumagba)
CREATE (person)-[:friend]-(person);

MATCH (person: Bubu), (person: Frank)
CREATE (person)-[:friend]-(person);

MATCH (person: Bubu), (person: Odjegba)
CREATE (person)-[:friend]-(person);

MATCH (person: Bubu), (person: Dangote)
CREATE (person)-[:friend]-(person);

MATCH (person: OBJ), (person: Okumagba)
CREATE (person)-[:friend]-(person);

MATCH (person: OBJ), (person: Frank)
CREATE (person)-[:friend]-(person);

MATCH (person: OBJ), (person: Odjegba)
CREATE (person)-[:friend]-(person);

MATCH (person: OBJ), (person: Musk)
CREATE (person)-[:friend]-(person);

MATCH (person: OBJ), (person: Dangote)
CREATE (person)-[:friend]-(person);

MATCH (person: Okumagba), (person: Frank)
CREATE (person)-[:friend]-(person);

MATCH (person: Okumagba), (person: Odjegba)
CREATE (person)-[:friend]-(person);

MATCH (person: Okumagba), (person: Dangote)
CREATE (person)-[:friend]-(person);

MATCH (person: Frank), (person: Odjegba)
CREATE (person)-[:friend]-(person);

MATCH (person: Frank), (person: Dangote)
CREATE (person)-[:friend]-(person);

MATCH (person: Odjegba), (person: Dangote)
CREATE (person)-[:friend]-(person);

MATCH (person: Mark), (person: Soros)
CREATE (person)-[:friend]-(person);

MATCH (person: Mark), (person: Buffet)
CREATE (person)-[:friend]-(person);

MATCH (person: Mark), (person: Musk)
CREATE (person)-[:friend]-(person);

MATCH (person: Soros), (person: Buffet)
CREATE (person)-[:friend]-(person);

MATCH (person: Soros), (person: Musk)
CREATE (person)-[:friend]-(person);

MATCH (person: Buffet), (person: Musk)
CREATE (person)-[:friend]-(person);
```
![neo4j5](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic5.png)

## Queries:

Q1: Viewed the graph database schema in a visual form: 
```
CALL db.schema.visualization()
```
![neo4j6](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic6.png)

Q2: Displayed the first 10 'Full_name' entries (properties) of 'person' nodes sorted in ascending order: 
```
MATCH
  (person)
RETURN
  person.Full_name
ORDER BY
  person.Full_name
LIMIT 10
```
![neo4j7](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic7.png)

Q3: Displayed the 'Full_name' of the youngest 'person' in the database: 
```
MATCH
  (person)
RETURN
  person.Full_name
ORDER BY
  person.Age
LIMIT 1
```
![neo4j8](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic8.png)

Q4: Displayed the number of 'person' nodes per 'Occupation' property: 
```
MATCH
  (person)
RETURN
  person.Occupation AS Occupation,
  COUNT(*) AS persons_per_Occupation
GROUP BY
  person.Occupation
```
![neo4j9](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic9.png)

Q5: Displayed the minimum and maximum 'Age' of 'persons' per 'Occupation': 
```
MATCH
  (person)
RETURN
  person.Occupation AS Occupation,
  MIN(person.Age) AS Minimum_Age_of_persons,
  MAX(person.Age) AS Maximum_Age_of_persons
GROUP BY
  person.Occupation
```
![neo4j10](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic10.png)

Q6: Displayed the 'Full_names' of 'persons' whose 'Occupations' are either 'CEO', 'CFO', 'COO', or 'CTO': 
```
MATCH
  (person)
WHERE
  person.Occupation IN ['CEO', 'CFO', 'COO', 'CTO']
RETURN
  person.Full_name AS Officials
```
 ![neo4j11](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic11.png)

Q7: Displayed the 'Full_name' and 'Occupation' of 'persons' whose 'Full_name' begins with 'Frank': 
```
MATCH
  (person)
WHERE
  person.Full_name =~’Frank.*’
RETURN
  person.Full_name AS FullName,
  person.Occupation AS Occupation
```
![neo4j12](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic12.png)

Q8: Displayed the 'Full_name', 'Age', 'Net_worth', and 'Occupation' of 'persons' who are 'Politicians' below the 'Age' of 70, sorted from the richest: 
```
MATCH
  (person)
WHERE
  person.Age < 70 AND person.Occupation = 'Politician'
RETURN
  person.Full_name AS FullName,
  person.Age AS Age,
  person.Net_worth AS NetWorth,
  person.Occupation AS Occupation
ORDER BY
  person.Net_worth DESC
 ```
![neo4j13](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic13.png)

Q9: Displayed the 'company.Name(s)' that a 'person' named 'Pharell' works at: 
```
MATCH
  (person: Pharell)-[:work]->(company)
RETURN
  company.Name AS Work_Place_of_Pharell
```
![neo4j14](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic14.png)

Q10: Displayed the 'Full_name' of 'persons' and the 'company.Name(s)' they work at: 
```
MATCH
  (person)-[:work]->(company)
RETURN
  person.Full_name AS Full_Name,
  company.Name AS Work_Place
```
![neo4j15](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic15.png)

Q11: Displayed the 'Full_name' of 'persons' and the 'university.Name(s)' they studied at: 
```
MATCH
  (person)-[:education]->(university)
RETURN
  person.Full_name,
  university.Name
```
![neo4j16](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic16.png)

Q12: Displayed the 'Full_name' of 'persons' that studied at 'UNN': 
```
MATCH
  (person)-[:education]->(university: UNN)
RETURN
  person.Full_name,
  university.Name
```
![neo4j17](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic17.png)

Q13: Displayed the 'Full_name' of 'persons' that studied at 'Uilorin': 
```
MATCH
  (person)-[:education]->(university: Unilorin)
RETURN
  person.Full_name,
  university.Name
```
![neo4j18](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic18.png)

Q14: Displayed the 'Full_name' of 'persons' who attended either 'Unilorin' or 'UNN': 
```
MATCH
  (person)-[:education]->(university)
WHERE
  university.Name = 'University Of Ilorin' OR university.Name = 'University Of Nigeria, Nsukka'
RETURN
  person.Full_name
```
![neo4j19](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic19.png) 

Q15: Displayed the number of 'persons', minimum and maximum 'Net_worth' of 'persons' per 'location.Country': 
```
MATCH
  (person)-[:place]->(location)
RETURN
  location.Country AS Country,
  COUNT(*) AS Number_Of_Persons,
  MIN(person.Net_worth) AS Poorest,
  MAX(person.Net_worth) AS Richest
```
![neo4j20](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic20.png) 

Q16: Displayed the 'Full_name' of 'persons' who are 'Politicians' as well as the 'university' attended: 
```
MATCH
  (person)-[:education]->(university)
WHERE
  person.Occupation = 'Politician'
RETURN
  person.Full_name AS Full_Name_of_Politician,
  university.Name AS University_Attended_by_Politician
```
![neo4j21](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic21.png) 

Q17: Displayed the 'person(s)' who 'studied' at 'Unilorin' and 'invest(s)' in 'FOREX', returning their full names, occupation, age, university name, and business type; arranged in descending order of 'age': 
```
MATCH
  (university: Unilorin)<-[education]-(person)-[investing]->(business: FOREX)
RETURN
  person.Full_name,
  person.Occupation,
  person.Age,
  university.Name,
  business.Type
ORDER BY
  person.Age DESC
``` 
![neo4j22](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/neo4j/neo4j-pic22.png)
