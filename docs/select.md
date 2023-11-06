Retrieve all data in cities table
```
SELECT * FROM cities
```

Retrieve name, country in cities table
```
SELECT name, country FROM cities
```

Retrieve name, density in cities table (density is calculated by population/area)
```
SELECT name, population/area as density FROM cities
```

String operators and functions
|| => join two strings
```
SELECT name || ', ' || country as location FROM cities
```
CONCAT() join two strings
```
SELECT concat(name, ', ', country) as location FROM cities
```
LOWER() convert string to lowercase
```
SELECT LOWER(concat(name, ', ', country)) as location FROM cities
```
UPPER() convert string to uppercase
```
SELECT UPPER(concat(name, ', ', country)) as location FROM cities
```
LENGTH() get a length of string