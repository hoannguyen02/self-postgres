- Produces values by merging together rows from different related tables
- Find data involves multiple resources

4 Kinds of joins:
- inner join:
- left join
- right join
- full join 

Examples
```
SELECT url, username
FROM photos
LEFT JOIN users on users.id = photos.user_id
```
```
SELECT url, contents
FROM comments
JOIN photos on photos.id = comments.photo_id
WHERE comments.user_id = photos.user_id;
```
```
SELECT url, contents, username
FROM comments
JOIN photos on photos.id = comments.photo_id
JOIN users ON users.id = comments.user_id AND users.id = photos.user_id;
```
