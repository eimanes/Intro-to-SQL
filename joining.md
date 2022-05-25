# Joining
- blend the **two or more tables** using `JOIN` 

example: one-to-one (movies-ratings)

table 1: movies | table 2: ratings | OUTPUT
---- | ---- | ---- |
|id| movie_id| id|
|title| rating| title|
|year| | year|
| | | movie_id|
| | | rating|
```
/* the output will display all the items in movies and ratings */
SELECT *
FROM
  movies JOIN ratings
    ON movies.id = ratings.movie_id
```
## Types of Joining
![image](https://user-images.githubusercontent.com/80232250/170176388-ea45a8e8-92ff-4188-9201-dbf989f72d1d.png)

### Inner Join `JOIN`
- take both tables which have datas
![image](https://user-images.githubusercontent.com/80232250/170177044-b1795d7e-3b44-4162-a1a1-0ae54795f529.png)
> note
the joining result change when the **ratings** table has less data than **movies** table

```
SELECT id, title, rating
FROM
  movies JOIN ratings
    ON movies.id = ratings.movie_id
```

### Left Join `LEFT JOIN`
- take all the left data table, right only follow the id
![image](https://user-images.githubusercontent.com/80232250/170177658-a87bd38e-3db6-43a3-a260-4b45c56a1949.png)
```
SELECT id, title, rating
FROM
  movies LEFT JOIN ratings
    ON movies.id = ratings.movie_id
```

### Right Join `RIGHT JOIN`
- take all the right data table, left only follow the id
> note: not available in SQLite
![image](https://user-images.githubusercontent.com/80232250/170177855-cd29d9bb-8666-451d-b5a3-d0cfd6617e61.png)
```
SELECT id, title, rating
FROM
  movies RIGHT JOIN ratings
    ON movies.id = ratings.movie_id
```

### Full Outer Join `FULL OUTER JOIN`
- display overall data on both tables
![image](https://user-images.githubusercontent.com/80232250/170177981-85669b36-bbf8-46ce-b6e7-b3b4257ce11f.png)
```
SELECT id, title, rating
FROM
  movies FULL OUTER JOIN ratings
    ON movies.id = ratings.movie_id
```
