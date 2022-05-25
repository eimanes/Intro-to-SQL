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
