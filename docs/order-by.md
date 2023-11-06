Sort record using order by 
```
select * 
FROM products
order BY price DESC, weight DESC;
```

Five most expensive products
```
select * 
FROM products
order BY price DESC, weight DESC
LIMIT 5
```

Get second pagination, each page has 20 products
```
select * 
FROM products
order BY price DESC, weight DESC
LIMIT 20
OFFSET 20
```

Get the names of only the second and third most expensive phones
```
select name
from phones
order by price desc
limit 2
offset 1
```