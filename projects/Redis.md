# Redis

## Task: 

* To create one database in Redis with your data based on a chosen case study (at least 10 key/value pairs with values varying in data type). 

* To implement at least 10 different queries on that data. The data and queries are to demonstrate appropriate variety and complexity. 

## Solution:

Note: If the screenshots in this section are not showing, you can get the PDF [here.](https://drive.google.com/file/d/1xh3u2CHpoGha5u3H-2gFwLjg6eGyF2vM/view?usp=sharing)

Got the Redis server running from the terminal, and started the command line interface:
```
redis-server

redis-cli

PING
```
![redis1](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/redis/redis-pic1.png)


Created a new database (i.e. selected a new namespace):
```
SELECT 15
```

Checked if there are any data in this namespace (database):
```
KEYS *
```

Added the first key-value pair (KVP) data:
```
SET db_name rell_db
```

Added the next two KVPs: 
```
MSET description "coursework assignment namespace" comment "this is my redis coursework assignment database"
```

Added six more string KVPs: 
```
MSET name pharell occupation business country "united kingdom" age 30 account_balance 9504650.15 special_number 96
```

Created a hash data type whose key is "rell_info:1": 
```
HSET rell_info:1 username rell password r477pr1$3 birthyear 1990 field bigdata
```

Created a list data type whose key value is "rell_hobbies" and add elements to it:
```
RPUSH rell_hobbies reading writing swimming trading investing

EXISTS rell_hobbies
```

Created a set data type whose key is "rell_interests" and add elements to it:
```
SADD rell_interests bigdata python finance markets advisors trading
```
![redis2](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/redis/redis-pic2.png)


## Queries:

Q1: Retrieved all the keys so far (this should return 12 items):
```
KEYS *
```
![redis3](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/redis/redis-pic3.png)

Q2: Returned the value of the key "db_name"; and the values of the keys "name", "occupation", and "account_balance":
```
GET db_name

MGET name occupation account_balance
```

Q3: Returned the field value of "username"; and the values of "password" and "birthyear" in a hash whose key is "rell_info:1":
```
HGET rell_info:1 username

HMGET rell_info:1 password birthyear
```
![redis4](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/redis/redis-pic4.png)

Q4: Returned all the fields and values in a hash whose key is "rell_info:1":
```
HKEYS rell_info:1

HVALS rell_info:1
```

Q5: Returned all the field-value pairs in a hash whose key is "rell_info:1":
```
HGETALL rell_info:1
```
![redis5](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/redis/redis-pic5.png)

Q6: Checked the data type of the key value "rell_hobbies":
```
TYPE rell_hobbies
```

Q7: Deleted the key "special_number", and verify that it no longer exists:
```
DEL special_number

EXISTS special_number
```

Q8: Retrieved all the keys so far (this should return 10 items):
```
KEYS *
```
![redis6](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/redis/redis-pic6.png)

Q9: Retrieved all the elements of the list "rell_hobbies" from the first (0) to the last (-1):
```
LRANGE rell_hobbies 0 -1
```

Q10: Checked how many elements are in the list "rell_hobbies":
```
LLEN rell_hobbies
```

Q11: Retrieved all the elements of the set "rell_interests":
```
SMEMBERS rell_interests
```

Q12: Checked how many elements are in the set "rell_interests":
```
SCARD rell_interests
```
![redis7](https://github.com/vaxdata22/NoSQL-and-Big-Data-demonstration/blob/main/screenshots/redis/redis-pic7.png)

