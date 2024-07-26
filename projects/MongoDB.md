# MongoDB

## Task: 

* To create one database in MongoDB with data based on a chosen case study (a collection with at least 20-30 documents of a different structure).
  
* To implement at least 10 different queries on that data. The data and queries are to demonstrate appropriate variety and complexity. 

## Solution:

Started the MongoDB shell from the terminal:
```
mongo
```
![mongodb1](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic1.png)

Created a database whose name is 'rell_db':
```
use rell_db;
```

Inserted the following 24 documents into the 'rell_info' collection for the database:
```
db.rell_info.insert({
  _id: 1,
  Info: 'General',
  Info_rank: 1,
  Info_priority: 'High',
  Classified: 'No',
  Name: 'Pharell Isodje',
  Vocation: 'Businessman',
  Location: 'UK',
  Activities: ['Trading', 'Investing', 'Research'],
  Overview: 'Pharell is a Nigerian-born tech enthusiast, FOREX investor, manager, and businessman.'
})

db.rell_info.insert({
  _id: 2,
  Info: 'Personal',
  Info_rank: 3,
  Info_priority: 'Medium',
  Classified: 'Yes',
  First_name: 'Pharell',
  Last_name: 'Isodje',
  Middle_name: 'Okiemute',
  Title: 'Mr.',
  Profession: 'Businessman',
  DOB: '1991-12-26',
  Miscellaneous: [
    {Likes: ['Honesty', 'Contentment', 'Loyalty']},
    {Dislikes: ['Dishonesty', 'Greed', 'Envy']},
    {Hobbies: ['Reading', 'Traveling', 'Painting']}
  ]
})

db.rell_info.insert({
  _id: 3,
  Info: 'Financial',
  Info_rank: 4,
  Info_priority: 'Low',
  Classified: 'Yes',
  Businesses: 3,
  Net_worth: 50000000.00,
  Currency: 'GBP',
  Assets: 200000000.00,
  Liabilities: 150000000.00,
  Annual_income: 1850000.00
})

db.rell_info.insert({
  _id: 4,
  Info: 'Location',
  Info_rank: 2,
  Info_priority: 'High',
  Classified: 'Yes',
  Country: 'UK',
  City: 'London',
  Apartment_type: 'Duplex',
  Apartment_colour: 'Blue'
})

db.rell_info.insert({
  _id: 5,
  Info: 'Interests',
  Info_rank: 1,
  Info_priority: 'High',
  Classified: 'No',
  Career: ['Business', 'Tech', 'Motivationals'],
  Political: 'Representative',
  Spiritual: 'Christian lifestyle',
  Personal: 'Modest family'
})

db.rell_info.insert({
  _id: 6,
  Info: 'Education',
  Info_rank: 2,
  Info_priority: 'Medium',
  Classified: 'No',
  Level: 'Masters',
  Field: 'Tech',
  Discipline: 'Big Data and BI',
  Concepts: ['AI', 'ML', 'Data', 'Finance']
})

db.rell_info.insert({
  _id: 7,
  Info: 'Investments',
  Info_rank: 3,
  Info_priority: 'Medium',
  Classified: 'Yes',
  Portfolios: 5,
  Accounts: 8,
  Capital: 70000000,
  Currency: 'GBP',
  Risk_level: 'Medium',
  Leverage: 0.01,
  Markets: ['FOREX', 'Futures', 'Metals', 'Minerals']
})

db.rell_info.insert({
  _id: 8,
  Info: 'Spirituality',
  Info_rank: 4,
  Info_priority: 'Medium',
  Classified: 'No',
  Religion: 'Christian',
  Denomination: 'Pentecostal',
  Outlook: 'Evangelical'
})

db.rell_info.insert({
  _id: 9,
  Info: 'Travels',
  Info_rank: 2,
  Info_priority: 'High',
  Classified: 'No',
  Countries_visited: 6,
  Hotels_used: 15,
  Tourist_sites: 7,
  Passports_owned: 2,
  Travel_reasons: ['Tourism', 'Educational', 'Research', 'Networking']
})

db.rell_info.insert({
  _id: 10,
  Info: 'Gadgets',
  Info_rank: 1,
  Info_priority: 'Medium',
  Classified: 'No',
  Items: 6,
  Items_list: ['MacBook', 'iPhone', 'Galaxy S22', 'iPad', 'Apple Smart watch', 'ThinkPad PC'],
  Work_gadget: 'ThinkPad PC',
  Mobile: 'iPhone'
})

db.rell_info.insert({
  _id: 11,
  Info: 'Cars',
  Info_rank: 1,
  Info_priority: 'High',
  Classified: 'No',
  Fleet: 3,
  Main_car: [
    {Name: 'Audi A8'}, 
    {Engine_cylinders: 6}, 
    {Displacement: 3.2}
  ]
})

db.rell_info.insert({
  _id: 12,
  Info: 'Health',
  Info_rank: 5,
  Info_priority: 'High',
  Classified: 'Yes',
  Allergies: ['Dust', 'Antimony'],
  Genotype: 'AA',
  Blood_group: 'O+',
  Rhesus_factor: 'Rh-',
  Risk_factors: ['Diabetes', 'Prostatitis'],
  Health_level_percent: 89.95,
  Weight_kg: 73.2
})

db.rell_info.insert({
  _id: 13,
  Info: 'Food',
  Info_rank: 1,
  Info_priority: 'Medium',
  Classified: 'No',
  Square_meals: 3,
  Favourite: 'Rice and chicken',
  Snacks: ['Meat pie', 'Sausage roll'],
  Native_dish: 'Starch with banga soup'
})

db.rell_info.insert({
  _id: 14,
  Info: 'Drinks',
  Info_rank: 2,
  Info_priority: 'Medium',
  Classified: 'No',
  Beverage_type: 'Non-alcoholic',
  Favourites: ['Eggovin', 'Amarula', 'Fruit juice'],
  Drinking_style: 'Social',
  Frequency: 'Moderate'
})

db.rell_info.insert({
  _id: 15,
  Info: 'Clothing',
  Info_rank: 2,
  Info_priority: 'Medium',
  Classified: 'No',
  Trouser_length: 32,
  Waist_girth: 32,
  Shoe_size: 43,
  Fashion_style: 'Impeccable',
  Designer: 'Tommy Hilfiger',
  Perfume: 'Latafa Hayatta'
})

db.rell_info.insert({
  _id: 16,
  Info: 'Music',
  Info_rank: 3,
  Info_priority: 'Low',
  Classified: 'No',
  Genres: ['Gospel', 'RnB', 'Pop'],
  Favourite_artist: 'Michael Jackson',
  Danceability: '64%'
})

db.rell_info.insert({
  _id: 17,
  Info: 'Tech Career',
  Info_rank: 4,
  Info_priority: 'Low', 
  Classified: 'No',
  Skills: ['Coding', 'Analytics', 'Reporting', 'Collaboration'],
  Programming: [
    {Languages: ['SQL', 'Python', 'R', 'C++']},
    {Tools: ['Jupyter Notebook', 'Oracle SQL Developer', 'RStudio', 'Google Analytics']}
  ]
})

db.rell_info.insert({
  _id: 18,
  Info: 'Employment',
  Info_rank: 2,
  Info_priority: 'High',
  Classified: 'No',
  Work_place: 'Rell Investments LLC',
  Position: 'CEO',
  Date_started: '2018-05-19',
  Status: 'Full-time',
  Mode: 'Hybrid'
})

db.rell_info.insert({
  _id: 19,
  Info: 'Residence',
  Info_rank: 1,
  Info_priority: 'Medium',
  Classified: 'Yes',
  Apartment_type: 'Duplex',
  Apartment_colour: 'Blue',
  Rooms: 4,
  Amenities: ['Overhead tank', 'Swimming pool', 'Air conditioning', 'Power plant', 'Garden', 'Garage'],
  Security: ['Fencing', 'Gate', 'Burglar alarm', 'Barbed wire']
})

db.rell_info.insert({
  _id: 20,
  Info: 'Internet',
  Info_rank: 2,
  Info_priority: 'Low',
  Classified: 'Yes',
  Facebook: 'rell_trader042',
  Email: 'rellguy@relltrader.com',
  Instagram: 'rell_investor'
})

db.rell_info.insert({
  _id: 21,
  Info: 'Politics',
  Info_rank: 1,
  Info_priority: 'Medium',
  Classified: 'No',
  Political_party: 'PDP',
  Aspiration: 'Senator',
  Outlook: 'Liberal'
})

db.rell_info.insert({
  _id: 22,
  Info: 'Pets',
  Info_rank: 1,
  Info_priority: 'Low',
  Classified: 'No',
  Number_of_pets: 2,
  Favourite: [
  {Type_of_pet: 'Bull dog'}, 
  {Name_of_pet: 'Martin'}, 
  {Age_of_pet: 5}
  ]
})

db.rell_info.insert({
  _id: 23,
  Info: 'Productivity',
  Info_rank: 2,
  Info_priority: 'Low',
  Classified: 'Yes',
  PC_apps: ['Office365', 'Zoom desktop', 'Metatrader', 'Chrome'],
  Mobile_apps: ['G-Suite', 'Zoom', 'WhatsApp', 'Metatrader', 'Telegram']
})

db.rell_info.insert({
  _id: 24,
  Info: 'Family',
  Info_rank: 5,
  Info_priority: 'High',
  Classified: 'Yes',
  Siblings: 4,
  Children: 0,
  Marital_status: 'Single',
  Next_of_kin: 'Isodje Dorcas'
})
```
![mongodb2](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic2.png)
![mongodb3](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic3.png)

## Queries:

Q1: Queried the database for all documents (while presenting the results in a formatted manner): 
```
db.rell_info.find().pretty()
```

Q2: Queried the database for the first document: 
```
db.rell_info.find({_id:1}).pretty()
```
![mongodb4](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic4.png)

Q3: Queried the database and return only one document; this essentially returned the first document: 
```
db.rell_info.findOne()
```
![mongodb5](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic5.png)

Q4: Queried the database for the document having 'Info: Financial': 
```
db.rell_info.find({Info:'Financial'}).pretty()
```
![mongodb6](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic6.png)

Q5: Queried the database to know if the document having 'Info: Productivity' is classified or not: 
```
db.rell_info.find({Info:'Productivity'}, {Classified:1, _id:0})
```

Q6: Queried the database to show only the 'Info' entries of the list of documents that are classified: 
```
db.rell_info.find({Classified:'Yes'}, {Info:1, _id:0})
```
![mongodb7](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic7.png)

Q7: Queried the database to see the first 10 documents sorted in descending order of their 'Info_rank' values, and excluding the entries for '_id', 'Info_rank', 'Info_priority', 'Classified': 
```
db.rell_info.find({}, {Info_rank:0, Info_priority:0, Classified:0, _id:0}).sort({Info_rank:-1}).limit(10).pretty()
```
![mongodb8](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic8.png)

Q8: Queried the database for the documents having 'Info_rank: 5': 
```
db.rell_info.find({Info_rank:5}).pretty()
```
![mongodb9](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic9.png)

Q9: Queried the database for the first 5 documents: 
```
db.rell_info.find({_id:{$lte:5}}).pretty()
```
![mongodb10](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic10.png)

Q10: Queried the database for the first 5 documents (ideal method): 
```
db.rell_info.find().limit(5).pretty()
```
![mongodb11](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic11.png)

Q11: Queried the database for only the 'Info' entries of the first 10 documents, sorted in asccending order of their 'Info_rank' values, and without showing their '_id' values: 
```
db.rell_info.find({}, {Info:1, _id:0}).sort({Info_rank:1}).limit(10).pretty()
```
![mongodb12](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic12.png)

Q12: Queried the database for any document having '_id' values of 1 or 25; this essentially returns the first and last documents in the database: 
```
db.rell_info.find({$or: [{_id:1}, {_id:25}] }).pretty()
```
![mongodb13](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic13.png)

Q13: Queried the database for the documents having 'Info_priority: High' and 'Classified: Yes':
```
db.rell_info.find({$and: [{Info_priority:'High'}, {Classified:'Yes'}] }).pretty()
```
![mongodb14](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic14.png)

Q14: Queried the database for the number of documents per 'Info_priority' count:
```
db.rell_info.aggregate([{$group: {_id:'$Info_priority', priority_count: {$sum: 1}} }])
```

Q15: Queried the database for the average 'Info_rank' values of documents per 'Classified' value:
```
db.rell_info.aggregate([{$group: {_id:'$Classified', average_info_rank: {$avg: '$Info_rank'}} }])
```
![mongodb15](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/mongodb/mongodb-pic15.png)
