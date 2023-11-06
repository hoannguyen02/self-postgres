- Looks at many rows and calculates a single value 
- With words such as most, average, least, etc

- Grouping: Reduce many rows down to fewer rows using group by
- Aggregates: Reduce many values down to one using aggregate functions such as max, min, count, etc

Examples:

Find the number of comments for each photo
```
select photo_id, count(*)
FROM comments
group BY photo_id
```

Find the number of comments for each photo where the photo id is less than 3 and the photo has more than 2 comments
```
select photo_id, count(*)
FROM comments
WHERE photo_id < 3
group BY photo_id
HAVING count(*) > 2
```

Find the users(user ids) where the user as commented on the first 50 photos and the user added more than 20 comments on those photos 
```
select user_id, count(*)
FROM comments
WHERE photo_id < 50
group BY user_id
HAVING count(*) > 20
```