# Some SQL queries

**Description:**

Some SQL Queries for the DVD rental database that we used during the database class at IT Bootcamp.

## 1

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

## 2

**Description:**

SQL query for the average rental price of movies in February of any year.

**SQL Query:**

```sql
select extract(year from r.rental_date), 
round(avg(p.amount),2) from rental as r
join payment as p
on p.rental_id=r.rental_id
where extract(month from r.rental_date)=02
group by (extract(year from r.rental_date));
  ```

**Result Example**

| extract   | round|
|----------|------|
| 2005     |	2.83 |


## 3

**Description:**

SQL query for the total rental revenue by staff.

**SQL Query:**

```sql
select sum(amount), staff_id from payment as p
group by staff_id;
  ```

**Result Example**

| sum     | staff_id|
|-------- |---------|
|30252.12 | 	1     | 
|31059.92	| 2       |  



## 4

**Description:**

SQL query for the number of customers by country.

**SQL Query:**

```sql
select co.country, count(c.customer_id) from customer as c
join address as ad
on c.address_id=ad.address_id
join city as ci
on ad.city_id=ci.city_id
join country as co
on ci.country_id=co.country_id
group by co.country_id;
  ```

**Result Example**

| country   | count|
|-------- |---------|
|Liechtenstein|	1   |
| Dominican Republic |	3|
| China |	53|
| Lithuania|	1|
| Malawi |	1|

## 5

**Description:**

SQL query for the number of customers by country.

**SQL Query:**

```sql
select f.title, count(r.rental_id) from rental as r
join inventory as i
on r.inventory_id=i.inventory_id
join film as f
on i.film_id= f.film_id
group by f.title 
order by count(r.rental_id) desc
limit 10;
  ```

**Result Example**

| title   | count|
|-------- |---------|
|Bucket Brotherhood|	34|
|Rocketeer Mother|	33 |
|Juggler Hardly|	32 |
|Ridgemont Submarine|	32 |
|Grit Clockwork|	32 |
|Forward Temple|	32 |
|Scalawag Duck|	32 |
|Apache Divine|	31 |
|Goodfellas Salute|	31 |
|Rush Goodfellas|	31 |
