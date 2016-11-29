## Example:
1.
 - `SQL:`
    SELECT count(\*) from items

 - `ANSWER:`
   100

---
<!-- How many users are there?
What are the titles of the 5 most expensive items?
What's the cheapest item in the Books category?
Who lives at 6439 Zetta Hills, Willmouth, WY?
Correct Virginie Mitchell's address to "New York, NY, 10108".
How much would it cost to buy one of each item in the Tools category?
How many total items did we sell?
How much was spent on Books?
Simulate buying an item by inserting a User for yourself and an Order for yourself. -->

1.
 - `SQL:`select title from items ORDER BY price DESC limit 5

 - `ANSWER:`
 +-----------------------+
| title                 |
|-----------------------|
| Small Cotton Gloves   |
| Small Wooden Computer |
| Awesome Granite Pants |
| Sleek Wooden Hat      |
| Ergonomic Steel Car   |
+-----------------------+


2.
 - `SQL:`

 - `ANSWER:`
