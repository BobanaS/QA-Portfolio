# Some SQL queries

**Description:**

Some SQL Queries for the DVD rental database that we used during the database class at IT Bootcamp.

##1
**Description:**

SQL query for the total number of rentals by movie category.

**SQL Query:**

```sql
select c.name, count(r.rental_id) from rental as r
join inventory as i
on r.inventory_id=i.inventory_id
join film as f
on i.film_id=f.film_id
join film_category as fa
on f.film_id=fa.film_id
join category as c
on fa.category_id=c.category_id
group by c.category_id;
  ```

**Result Example**

| name     | count|
|----------|-------|
| Classics |	939  |
| Sci-Fi   |	1101|
|Children  |	945|
|New       |	940|
|Games     |	969|
|Drama     |	1060|

