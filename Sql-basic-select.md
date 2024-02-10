**##Revising the Select Query 1**

Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.
The CITY table is described as follows:

**CITY**
|FIELD      |TYPE        |
|-----------|------------|
|ID         |NUMBER      |
|NAME       |VARCHAR2(17)|
|COUNTRYCODE|VARCHAR2(3) |
|DISTRICT   |VARCHAR2(20)|
|POPULATION |NUMBER      |

**Solution**

select * from city where countrycode="usa" and population>"100000";

**##Revising Select Query 2**

Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.
The CITY table is described as follows:

**CITY**
|FIELD|TYPE|
|------|-----|
|ID         |NUMBER      |
|NAME       |VARCHAR2(17)|
|COUNTRYCODE|VARCHAR2(3) |
|DISTRICT   |VARCHAR2(20)|
|POPULATION |NUMBER      |

**Solution**

select name from city where population>120000 and countrycode="usa";

**##Select All**

Query all columns (attributes) for every row in the CITY table.
The CITY table is described as follows:

**CITY**
|FIELD      |TYPE        |
|-----------|------------|
|ID         |NUMBER      |
|NAME       |VARCHAR2(17)|
|COUNTRYCODE|VARCHAR2(3) |
|DISTRICT   |VARCHAR2(20)|
|POPULATION |NUMBER      |

**Solution**

select * from city;

**##Select by ID**

Query all columns for a city in CITY with the ID 1661.
The CITY table is described as follows:

**CITY**
|FIELD      |TYPE        |
|-----------|------------|
|ID         |NUMBER      |
|NAME       |VARCHAR2(17)|
|COUNTRYCODE|VARCHAR2(3) |
|DISTRICT   |VARCHAR2(20)|
|POPULATION |NUMBER      |

**Solution**

select * from city where id=1661;

**##Weather Observation Station 5**

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
The STATION table is described as follows:

**Station**
|Field|Type|
|-----|-----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Sample Input**

For example, CITY has four entries: DEF, ABC, PQRS and WXY.
**Sample Output**

ABC 3
PQRS 4
**Explanation**

When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with lengths 3,3,4 and 3 . The longest name is PQRS, but there are 3 options for shortest named city. Choose ABC, because it comes first alphabetically.
**Note**

You can write two separate queries to get the desired output. It need not be a single query.

**Solution**

select city,length(city) from station order by length(city),city asc limit 1;
select city,length(city) from station order by length(city) desc limit 1;

**##Weather Observation Station 6**

Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

**Input Format**

The STATION table is described as follows:
**Station**
|Field|Type|
|-----|-----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**

select distinct city from station where city regexp '^[aeiou]';


**##Weather Observation Station 7**

Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.
**Input Format**

The STATION table is described as follows:

**Station**
|Field|Type|
|-----|-----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where LAT_N is the northern latitude and LONG_W is the western longitude.


**Solution**

select distinct city from station where city regexp '[aeiouAEIOU]$';

**##Weather Observation Station 8**

Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.
**Input Format**

The STATION table is described as follows:
**Station**
|Field|Type|
|-----|-----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**

select distinct city from station where city regexp '^[aeiou]' and city regexp '[aeiou]$';

**##Weather Observation Station 9**

Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.
**Input Format**

The STATION table is described as follows:
**Station**
|Field|Type|
|-----|-----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where LAT_N is the northern latitude and LONG_W is the western longitude.
**Solution**

select distinct city from station where city not regexp '^[aeiou]'; 


**##Weather Observation Station 10**

Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.
**Input Format**

The STATION table is described as follows:
**Station**
|Field|Type|
|-----|-----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where LAT_N is the northern latitude and LONG_W is the western longitude.
**Solution**

select distinct city from station where city not regexp '[aeoiu]$';








