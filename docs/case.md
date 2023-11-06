```
select 
    name, 
    price, 
    case 
        when price > 600 then 'high'
        when price > 300 then 'medium'
        else 'cheap'
from products;
```