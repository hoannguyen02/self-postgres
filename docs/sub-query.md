Sub queries can be used as:
- A source of a value: in select
- A source of rows: In from, join
```
select max(average_price) as max_average_price
from (
    select avg(price) as average_price from phones group by manufacturer
);
```
- A source of column: in where 
```
select name, price 
FROM products
WHERE price > (
	select avg(price) FROM products
);
```

```
select name, price
FROM products
WHERE price > (
  select max(price) FROM products WHERE department = 'Toys'
);
```

```
select id 
FROM orders
WHERE product_id in (
	select id FROM products WHERE price / weight > 50
);
```

```
select name, price
from phones
where price > (
    select price from phones where name = 'S5620 Monte'
)
```

```
select name, department
from products
where department not in (
  select department from products where price < 100
)
```
Show name of the products that are more expensive than all products in the "Industrial" department
```
select name, department, price
from products
where price > all (
  select price from products where department = 'Industrial'
)
```
Show name of the products that are more expensive than at least one product in the "Industrial" department
```
select name, department, price
from products
where price > some (
  select price from products where department = 'Industrial'
)
```
Show the name, department, and price of the most expensive product in each department
```
select name, department, price
from products
where price 
```

Select name and orders using correlated sub queries
```
select p1.name, (select count(*) from orders as o1 where o1.product_id = p1.id) as num_orders
from products as p1
```