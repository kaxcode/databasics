## Example:
1.
 - `SQL:`
    SELECT count(\*) from items

 - `ANSWER:`
   100

---
<!-- How many users are there?
1. What are the titles of the 5 most expensive items?
2. What's the cheapest item in the Books category?
3. Who lives at 6439 Zetta Hills, Willmouth, WY?
4. Correct Virginie Mitchell's address to "New York, NY, 10108".
5. How much would it cost to buy one of each item in the Tools category?
6. How many total items did we sell?
7. How much was spent on Books?
8. Simulate buying an item by inserting a User for yourself and an Order for yourself. -->

1. What are the titles of the 5 most expensive items?
  `SQL:
    `select title from items ORDER BY price DESC limit 5

 `ANSWER:`
    +-----------------------+
    | title                 |
    |-----------------------|
    | Small Cotton Gloves   |
    | Small Wooden Computer |
    | Awesome Granite Pants |
    | Sleek Wooden Hat      |
    | Ergonomic Steel Car   |
    +-----------------------+


2.What's the cheapest item in the Books category?
  `SQL:`
    select * from items where category = 'Books' order by price LIMIT 1

 `ANSWER:`
   +------+-------------------------+------------+-------------------------------------+---------+
   |   id | title                   | category   | description                         |   price |
   |------+-------------------------+------------+-------------------------------------+---------|
   |   76 | Ergonomic Granite Chair | Books      | De-engineered bi-directional portal |    1496 |
   +------+-------------------------+------------+-------------------------------------+---------+

3. Who lives at 6439 Zetta Hills, Willmouth, WY?
  `SQL:

  `ANSWER:`

4. Correct Virginie Mitchell's address to "New York, NY, 10108".
  `SQL:

  `ANSWER:`

5. How much would it cost to buy one of each item in the Tools category?
  `SQL:

  `ANSWER:`

6. How many total items did we sell?
  `SQL:

  `ANSWER:`

7. How much was spent on Books?
  `SQL:

  `ANSWER:`

8. Simulate buying an item by inserting a User for yourself and an Order for yourself.
  `SQL:

  `ANSWER:`
