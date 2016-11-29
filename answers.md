1. How many users are there?
  `SQL:
    select * from users
  `ANSWER:
    +------+--------------+-------------+-----------------------------------+
    |   id | first_name   | last_name   | email                             |
    |------+--------------+-------------+-----------------------------------|
    |    1 | Axel         | Robel       | ludie_reynolds@schaden.net        |
    |    2 | Missouri     | Carroll     | darby@rohan.org                   |
    |    3 | Fatima       | Toy         | bertrand@langrunolfsdottir.info   |
    |    4 | Devyn        | Bode        | naomie_hilpert@hettinger.com      |
    |    5 | Eldon        | Aufderhar   | samantha_haley@effertz.org        |
    |    6 | Kacie        | Johns       | muhammad.crooks@white.name        |
    |    7 | Leann        | Runte       | bryana.sauer@buckridge.biz        |
    |    8 | Judge        | Frami       | deangelo@okuneva.net              |
    |    9 | Shane        | Dibbert     | santiago@crooksbayer.info         |
    |   10 | Cloyd        | Maggio      | koby.jerde@ullrichsenger.biz      |
    |   11 | Phoebe       | Kshlerin    | juvenal.effertz@ryan.name         |
    |   12 | Vilma        | McCullough  | janae.mitchell@weinatbruen.biz    |
    |   13 | Mekhi        | Lakin       | sienna.skiles@kshlerin.com        |
    |   14 | Orland       | Effertz     | finn_mcglynn@hamill.info          |
    |   15 | Frida        | Hauck       | tianna@mann.name                  |
    |   16 | Amina        | Boehm       | sarai_abernathy@gusikowski.biz    |
    |   17 | Caitlyn      | Murazik     | van.auer@bahringerschowalter.com  |
    |   18 | Devonte      | Schoen      | kendrick@binawayn.biz             |
    |   19 | Hassan       | Runte       | weston.kautzer@hoppe.biz          |
    |   20 | Kendrick     | Ward        | rick@hoeger.org                   |
    |   21 | Felicity     | Carroll     | rashawn@quigley.biz               |
    |   22 | Jovan        | McClure     | miller@harrishalvorson.net        |
    |   23 | Brian        | Dooley      | leon_feeney@cummings.name         |
    |   24 | Julien       | Pfeffer     | camron@bergnaum.info              |
    |   25 | Cleta        | Adams       | stanford@kertzmann.org            |
    |   26 | Verner       | Schiller    | audrey@hartmann.org               |
    |   27 | Monserrate   | Legros      | maggie.anderson@spinka.name       |
    |   28 | Dewitt       | Gutkowski   | bart@armstrongconn.com            |
    |   29 | Kennedi      | McLaughlin  | amy.hagenes@damorewalker.org      |
    |   30 | Cole         | Walker      | elfrieda@rogahn.org               |
    |   31 | Shany        | Hodkiewicz  | ivah_jacobs@kshlerinmarks.name    |
    |   32 | Ursula       | Macejkovic  | isaac@dietrich.info               |
    |   33 | Sanford      | Pagac       | tyrique_oconnell@upton.net        |
    |   34 | Jayme        | Waters      | ellsworth_kuhn@rogahn.net         |
    |   35 | Flavio       | Schinner    | diana.bauch@hodkiewicz.biz        |
    |   36 | Jennie       | Smith       | vivien@grady.com                  |
    |   37 | Dee          | Balistreri  | kaya@walker.net                   |
    |   38 | Marshall     | Franecki    | hyman@hamill.org                  |
    |   39 | Virginie     | Mitchell    | daisy.crist@altenwerthmonahan.biz |
    |   40 | Corrine      | Little      | rubie_kovacek@grimes.net          |
    |   41 | Dakota       | McGlynn     | marjolaine@herzog.net             |
    |   42 | Cleo         | Effertz     | hilario@bergnaum.net              |
    |   43 | Kyra         | Kilback     | demarcus.predovic@grimes.org      |
    |   44 | Randi        | Kirlin      | craig.berge@sauerweimann.net      |
    |   45 | Kayden       | DuBuque     | gage.langworth@millsturcotte.net  |
    |   46 | Derrick      | Cummerata   | libby.langosh@hodkiewicz.com      |
    |   47 | Colton       | Crooks      | declan_mclaughlin@carroll.biz     |
    |   48 | Roselyn      | Zboncak     | jeyca@pfannerstill.com            |
    |   49 | Ignacio      | Buckridge   | chance@wiegand.name               |
    |   50 | Norene       | Bartell     | natalie@cainkeeling.biz           |
    +------+--------------+-------------+-----------------------------------+
    SELECT 50

2. What are the titles of the 5 most expensive items?
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


3.What's the cheapest item in the Books category?
  `SQL:`
    select * from items where category = 'Books' order by price LIMIT 1

 `ANSWER:`
   +------+-------------------------+------------+-------------------------------------+---------+
   |   id | title                   | category   | description                         |   price |
   |------+-------------------------+------------+-------------------------------------+---------|
   |   76 | Ergonomic Granite Chair | Books      | De-engineered bi-directional portal |    1496 |
   +------+-------------------------+------------+-------------------------------------+---------+


4. Who lives at 6439 Zetta Hills, Willmouth, WY?
  `SQL:
  select first_name, last_name from users, addresses where users.id = addresses.user_id AND addresses.street = '6439 Zetta Hills' AND addresses.city = 'Willmouth' AND addresses.state = 'WY';
+--------------+-------------+
| first_name   | last_name   |
|--------------+-------------|
| Corrine      | Little      |
+--------------+-------------+
  `ANSWER:`

5. Correct Virginie Mitchell's address to "New York, NY, 10108".

  `SQL:
    update addresses set city = 'New York', state = 'NY', zip = '10108'
    where id = (select addresses.id
      from addresses, users
      where users.id = addresses.user_id
      AND users.first_name = 'Virginie'
      AND users.last_name = 'Mitchell')

    select users.first_name, users.last_name, addresses.city, addresses.state, addresses.zip
    from addresses, users
    where users.id = addresses.user_id
    AND users.first_name = 'Virginie'
    AND users.last_name = 'Mitchell'

  `ANSWER:`
    UPDATE 1
    +--------------+-------------+----------+---------+-------+
    | first_name   | last_name   | city     | state   |   zip |
    |--------------+-------------+----------+---------+-------|
    | Virginie     | Mitchell    | New York | NY      | 10108 |
    +--------------+-------------+----------+---------+-------+


6. How much would it cost to buy one of each item in the Tools category?
  `SQL:
    select sum(price) from items where category = 'Tools'

  `ANSWER:`
    +-------+
    |   sum |
    |-------|
    |  7383 |
    +-------+
    SELECT 1

7. How many total items did we sell?
  `SQL:
    select sum(quantity) from orders

  `ANSWER:`
    +-------+
    |   sum |
    |-------|
    |  2125 |
    +-------+
8. How much was spent on Books?
  `SQL:
    SELECT sum(price* quantity)
      from items, orders
      where items.id = orders.item_id
      AND items.category = 'Books'

  `ANSWER:`
    +--------+
    |    sum |
    |--------|
    | 420566 |
    +--------+
    SELECT 1

9. Simulate buying an item by inserting a User for yourself and an Order for yourself.
  `SQL:
    insert into users(id, first_name, last_name, email) values(51, 'Kenia', 'Valladarez', 'keniavalladarez@gmail.com')
    select * from users ORDER BY id desc limit 1

    insert into orders(id, user_id, item_id, quantity, created_at) values(378, 51, 18, 1, '2016-11-29 00:40:30.457665')
    select * from orders ORDER BY created_at desc limit 1
  `ANSWER:`

    +------+--------------+-------------+---------------------------+
    |   id | first_name   | last_name   | email                     |
    |------+--------------+-------------+---------------------------|
    |   51 | Kenia        | Valladarez  | keniavalladarez@gmail.com |
    +------+--------------+-------------+---------------------------+
    +------+-----------+-----------+------------+----------------------------+
    |   id |   user_id |   item_id |   quantity | created_at                 |
    |------+-----------+-----------+------------+----------------------------|
    |  378 |        51 |        18 |          1 | 2016-11-29 00:40:30.457665 |
    +------+-----------+-----------+------------+----------------------------+
