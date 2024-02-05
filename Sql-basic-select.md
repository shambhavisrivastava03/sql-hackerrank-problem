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






