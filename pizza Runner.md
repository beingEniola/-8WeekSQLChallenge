```python
%load_ext sql
```


```python
%sql postgresql://***:***@***/***
```


```sql
%%sql
SELECT * 
FROM pizza_runner.runners
```

     * postgresql://postgres:***@localhost/postgres
    4 rows affected.
    




<table>
    <thead>
        <tr>
            <th>runner_id</th>
            <th>registration_date</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>2021-01-01</td>
        </tr>
        <tr>
            <td>2</td>
            <td>2021-01-03</td>
        </tr>
        <tr>
            <td>3</td>
            <td>2021-01-08</td>
        </tr>
        <tr>
            <td>4</td>
            <td>2021-01-15</td>
        </tr>
    </tbody>
</table>




```sql
%%sql
SELECT * 
FROM pizza_runner.customer_orders
```

     * postgresql://postgres:***@localhost/postgres
    14 rows affected.
    




<table>
    <thead>
        <tr>
            <th>order_id</th>
            <th>customer_id</th>
            <th>pizza_id</th>
            <th>exclusions</th>
            <th>extras</th>
            <th>order_time</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>101</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-01 18:05:02</td>
        </tr>
        <tr>
            <td>2</td>
            <td>101</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-01 19:00:52</td>
        </tr>
        <tr>
            <td>3</td>
            <td>102</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-02 23:51:23</td>
        </tr>
        <tr>
            <td>3</td>
            <td>102</td>
            <td>2</td>
            <td></td>
            <td>None</td>
            <td>2020-01-02 23:51:23</td>
        </tr>
        <tr>
            <td>4</td>
            <td>103</td>
            <td>1</td>
            <td>4</td>
            <td></td>
            <td>2020-01-04 13:23:46</td>
        </tr>
        <tr>
            <td>4</td>
            <td>103</td>
            <td>1</td>
            <td>4</td>
            <td></td>
            <td>2020-01-04 13:23:46</td>
        </tr>
        <tr>
            <td>4</td>
            <td>103</td>
            <td>2</td>
            <td>4</td>
            <td></td>
            <td>2020-01-04 13:23:46</td>
        </tr>
        <tr>
            <td>5</td>
            <td>104</td>
            <td>1</td>
            <td>null</td>
            <td>1</td>
            <td>2020-01-08 21:00:29</td>
        </tr>
        <tr>
            <td>6</td>
            <td>101</td>
            <td>2</td>
            <td>null</td>
            <td>null</td>
            <td>2020-01-08 21:03:13</td>
        </tr>
        <tr>
            <td>7</td>
            <td>105</td>
            <td>2</td>
            <td>null</td>
            <td>1</td>
            <td>2020-01-08 21:20:29</td>
        </tr>
        <tr>
            <td>8</td>
            <td>102</td>
            <td>1</td>
            <td>null</td>
            <td>null</td>
            <td>2020-01-09 23:54:33</td>
        </tr>
        <tr>
            <td>9</td>
            <td>103</td>
            <td>1</td>
            <td>4</td>
            <td>1, 5</td>
            <td>2020-01-10 11:22:59</td>
        </tr>
        <tr>
            <td>10</td>
            <td>104</td>
            <td>1</td>
            <td>null</td>
            <td>null</td>
            <td>2020-01-11 18:34:49</td>
        </tr>
        <tr>
            <td>10</td>
            <td>104</td>
            <td>1</td>
            <td>2, 6</td>
            <td>1, 4</td>
            <td>2020-01-11 18:34:49</td>
        </tr>
    </tbody>
</table>




```sql
%%sql
SELECT * 
FROM pizza_runner.runner_orders
```

     * postgresql://postgres:***@localhost/postgres
    10 rows affected.
    




<table>
    <thead>
        <tr>
            <th>order_id</th>
            <th>runner_id</th>
            <th>pickup_time</th>
            <th>distance</th>
            <th>duration</th>
            <th>cancellation</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>1</td>
            <td>2020-01-01 18:15:34</td>
            <td>20km</td>
            <td>32 minutes</td>
            <td></td>
        </tr>
        <tr>
            <td>2</td>
            <td>1</td>
            <td>2020-01-01 19:10:54</td>
            <td>20km</td>
            <td>27 minutes</td>
            <td></td>
        </tr>
        <tr>
            <td>3</td>
            <td>1</td>
            <td>2020-01-03 00:12:37</td>
            <td>13.4km</td>
            <td>20 mins</td>
            <td>None</td>
        </tr>
        <tr>
            <td>4</td>
            <td>2</td>
            <td>2020-01-04 13:53:03</td>
            <td>23.4</td>
            <td>40</td>
            <td>None</td>
        </tr>
        <tr>
            <td>5</td>
            <td>3</td>
            <td>2020-01-08 21:10:57</td>
            <td>10</td>
            <td>15</td>
            <td>None</td>
        </tr>
        <tr>
            <td>6</td>
            <td>3</td>
            <td>null</td>
            <td>null</td>
            <td>null</td>
            <td>Restaurant Cancellation</td>
        </tr>
        <tr>
            <td>7</td>
            <td>2</td>
            <td>2020-01-08 21:30:45</td>
            <td>25km</td>
            <td>25mins</td>
            <td>null</td>
        </tr>
        <tr>
            <td>8</td>
            <td>2</td>
            <td>2020-01-10 00:15:02</td>
            <td>23.4 km</td>
            <td>15 minute</td>
            <td>null</td>
        </tr>
        <tr>
            <td>9</td>
            <td>2</td>
            <td>null</td>
            <td>null</td>
            <td>null</td>
            <td>Customer Cancellation</td>
        </tr>
        <tr>
            <td>10</td>
            <td>1</td>
            <td>2020-01-11 18:50:20</td>
            <td>10km</td>
            <td>10minutes</td>
            <td>null</td>
        </tr>
    </tbody>
</table>




```sql
%%sql
SELECT * 
FROM pizza_runner.pizza_names
```

     * postgresql://postgres:***@localhost/postgres
    2 rows affected.
    




<table>
    <thead>
        <tr>
            <th>pizza_id</th>
            <th>pizza_name</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Meatlovers</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Vegetarian</td>
        </tr>
    </tbody>
</table>




```sql
%%sql
SELECT * 
FROM pizza_runner.pizza_recipes
```

     * postgresql://postgres:***@localhost/postgres
    2 rows affected.
    




<table>
    <thead>
        <tr>
            <th>pizza_id</th>
            <th>toppings</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>1, 2, 3, 4, 5, 6, 8, 10</td>
        </tr>
        <tr>
            <td>2</td>
            <td>4, 6, 7, 9, 11, 12</td>
        </tr>
    </tbody>
</table>




```sql
%%sql
SELECT * 
FROM pizza_runner.pizza_toppings
```

     * postgresql://postgres:***@localhost/postgres
    12 rows affected.
    




<table>
    <thead>
        <tr>
            <th>topping_id</th>
            <th>topping_name</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Bacon</td>
        </tr>
        <tr>
            <td>2</td>
            <td>BBQ Sauce</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Beef</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Cheese</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Chicken</td>
        </tr>
        <tr>
            <td>6</td>
            <td>Mushrooms</td>
        </tr>
        <tr>
            <td>7</td>
            <td>Onions</td>
        </tr>
        <tr>
            <td>8</td>
            <td>Pepperoni</td>
        </tr>
        <tr>
            <td>9</td>
            <td>Peppers</td>
        </tr>
        <tr>
            <td>10</td>
            <td>Salami</td>
        </tr>
        <tr>
            <td>11</td>
            <td>Tomatoes</td>
        </tr>
        <tr>
            <td>12</td>
            <td>Tomato Sauce</td>
        </tr>
    </tbody>
</table>



# DATA CLEANING


```sql
%%sql
DROP TABLE customer_orders
```

     * postgresql://postgres:***@localhost/postgres
    Done.
    




    []




```sql
%%sql
SELECT order_id, customer_id, pizza_id, 
  CASE 
    WHEN exclusions = 'null'THEN ''
    ELSE exclusions
    END AS exclusions,
  CASE 
    WHEN extras IS NULL or extras = 'null' THEN ''
    ELSE extras 
    END AS extras, 
  order_time
INTO customer_orders 
FROM pizza_runner.customer_orders;
```

     * postgresql://postgres:***@localhost/postgres
    14 rows affected.
    




    []




```sql
%%sql 
SELECT * 
FROM customer_orders
```

     * postgresql://postgres:***@localhost/postgres
    14 rows affected.
    




<table>
    <thead>
        <tr>
            <th>order_id</th>
            <th>customer_id</th>
            <th>pizza_id</th>
            <th>exclusions</th>
            <th>extras</th>
            <th>order_time</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>101</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-01 18:05:02</td>
        </tr>
        <tr>
            <td>2</td>
            <td>101</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-01 19:00:52</td>
        </tr>
        <tr>
            <td>3</td>
            <td>102</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-02 23:51:23</td>
        </tr>
        <tr>
            <td>3</td>
            <td>102</td>
            <td>2</td>
            <td></td>
            <td></td>
            <td>2020-01-02 23:51:23</td>
        </tr>
        <tr>
            <td>4</td>
            <td>103</td>
            <td>1</td>
            <td>4</td>
            <td></td>
            <td>2020-01-04 13:23:46</td>
        </tr>
        <tr>
            <td>4</td>
            <td>103</td>
            <td>1</td>
            <td>4</td>
            <td></td>
            <td>2020-01-04 13:23:46</td>
        </tr>
        <tr>
            <td>4</td>
            <td>103</td>
            <td>2</td>
            <td>4</td>
            <td></td>
            <td>2020-01-04 13:23:46</td>
        </tr>
        <tr>
            <td>5</td>
            <td>104</td>
            <td>1</td>
            <td></td>
            <td>1</td>
            <td>2020-01-08 21:00:29</td>
        </tr>
        <tr>
            <td>6</td>
            <td>101</td>
            <td>2</td>
            <td></td>
            <td></td>
            <td>2020-01-08 21:03:13</td>
        </tr>
        <tr>
            <td>7</td>
            <td>105</td>
            <td>2</td>
            <td></td>
            <td>1</td>
            <td>2020-01-08 21:20:29</td>
        </tr>
        <tr>
            <td>8</td>
            <td>102</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-09 23:54:33</td>
        </tr>
        <tr>
            <td>9</td>
            <td>103</td>
            <td>1</td>
            <td>4</td>
            <td>1, 5</td>
            <td>2020-01-10 11:22:59</td>
        </tr>
        <tr>
            <td>10</td>
            <td>104</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-11 18:34:49</td>
        </tr>
        <tr>
            <td>10</td>
            <td>104</td>
            <td>1</td>
            <td>2, 6</td>
            <td>1, 4</td>
            <td>2020-01-11 18:34:49</td>
        </tr>
    </tbody>
</table>




```sql
%%sql
DROP TABLE runner_orders
```

     * postgresql://postgres:***@localhost/postgres
    Done.
    




    []




```sql
%%sql
SELECT order_id, runner_id, 
    CASE 
        WHEN pickup_time = 'null' THEN ''
        ELSE pickup_time
        END AS pickup_time,
    CASE 
        WHEN distance = 'null' THEN ''
        WHEN distance LIKE '%km' THEN TRIM('km' from distance)
        ELSE distance
        END AS distance, 
    CASE 
        WHEN duration = 'null' THEN ''
        WHEN duration LIKE '%mins' THEN TRIM('mins' from duration) 
        WHEN duration LIKE '%minute' THEN TRIM('minute' from duration)        
        WHEN duration LIKE '%minutes' THEN TRIM('minutes' from duration)       
        ELSE duration
        END AS duration,
    CASE 
        WHEN cancellation IS NULL OR cancellation = 'null' THEN ''
        ELSE cancellation
        END AS cancellation
INTO runner_orders
FROM pizza_runner.runner_orders
```

     * postgresql://postgres:***@localhost/postgres
    10 rows affected.
    




    []




```sql
%%sql
SELECT * 
FROM runner_orders
```

     * postgresql://postgres:***@localhost/postgres
    10 rows affected.
    




<table>
    <thead>
        <tr>
            <th>order_id</th>
            <th>runner_id</th>
            <th>pickup_time</th>
            <th>distance</th>
            <th>duration</th>
            <th>cancellation</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>1</td>
            <td>2020-01-01 18:15:34</td>
            <td>20</td>
            <td>32 </td>
            <td></td>
        </tr>
        <tr>
            <td>2</td>
            <td>1</td>
            <td>2020-01-01 19:10:54</td>
            <td>20</td>
            <td>27 </td>
            <td></td>
        </tr>
        <tr>
            <td>3</td>
            <td>1</td>
            <td>2020-01-03 00:12:37</td>
            <td>13.4</td>
            <td>20 </td>
            <td></td>
        </tr>
        <tr>
            <td>4</td>
            <td>2</td>
            <td>2020-01-04 13:53:03</td>
            <td>23.4</td>
            <td>40</td>
            <td></td>
        </tr>
        <tr>
            <td>5</td>
            <td>3</td>
            <td>2020-01-08 21:10:57</td>
            <td>10</td>
            <td>15</td>
            <td></td>
        </tr>
        <tr>
            <td>6</td>
            <td>3</td>
            <td></td>
            <td></td>
            <td></td>
            <td>Restaurant Cancellation</td>
        </tr>
        <tr>
            <td>7</td>
            <td>2</td>
            <td>2020-01-08 21:30:45</td>
            <td>25</td>
            <td>25</td>
            <td></td>
        </tr>
        <tr>
            <td>8</td>
            <td>2</td>
            <td>2020-01-10 00:15:02</td>
            <td>23.4 </td>
            <td>15 </td>
            <td></td>
        </tr>
        <tr>
            <td>9</td>
            <td>2</td>
            <td></td>
            <td></td>
            <td></td>
            <td>Customer Cancellation</td>
        </tr>
        <tr>
            <td>10</td>
            <td>1</td>
            <td>2020-01-11 18:50:20</td>
            <td>10</td>
            <td>10</td>
            <td></td>
        </tr>
    </tbody>
</table>




```sql
%%sql
ALTER TABLE runner_orders
ALTER COLUMN pickup_time TYPE TIMESTAMP 
    USING CASE WHEN pickup_time = '' THEN NULL ELSE pickup_time::TIMESTAMP END,
ALTER COLUMN distance TYPE FLOAT 
        USING CASE WHEN distance = '' THEN NULL ELSE distance::double precision END,
ALTER COLUMN duration TYPE INT
        USING CASE WHEN duration = '' THEN NULL ELSE duration::integer END
```

     * postgresql://postgres:***@localhost/postgres
    Done.
    




    []




```sql
%%sql
SELECT *
FROM runner_orders
```

     * postgresql://postgres:***@localhost/postgres
    10 rows affected.
    




<table>
    <thead>
        <tr>
            <th>order_id</th>
            <th>runner_id</th>
            <th>pickup_time</th>
            <th>distance</th>
            <th>duration</th>
            <th>cancellation</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>1</td>
            <td>2020-01-01 18:15:34</td>
            <td>20.0</td>
            <td>32</td>
            <td></td>
        </tr>
        <tr>
            <td>2</td>
            <td>1</td>
            <td>2020-01-01 19:10:54</td>
            <td>20.0</td>
            <td>27</td>
            <td></td>
        </tr>
        <tr>
            <td>3</td>
            <td>1</td>
            <td>2020-01-03 00:12:37</td>
            <td>13.4</td>
            <td>20</td>
            <td></td>
        </tr>
        <tr>
            <td>4</td>
            <td>2</td>
            <td>2020-01-04 13:53:03</td>
            <td>23.4</td>
            <td>40</td>
            <td></td>
        </tr>
        <tr>
            <td>5</td>
            <td>3</td>
            <td>2020-01-08 21:10:57</td>
            <td>10.0</td>
            <td>15</td>
            <td></td>
        </tr>
        <tr>
            <td>6</td>
            <td>3</td>
            <td>None</td>
            <td>None</td>
            <td>None</td>
            <td>Restaurant Cancellation</td>
        </tr>
        <tr>
            <td>7</td>
            <td>2</td>
            <td>2020-01-08 21:30:45</td>
            <td>25.0</td>
            <td>25</td>
            <td></td>
        </tr>
        <tr>
            <td>8</td>
            <td>2</td>
            <td>2020-01-10 00:15:02</td>
            <td>23.4</td>
            <td>15</td>
            <td></td>
        </tr>
        <tr>
            <td>9</td>
            <td>2</td>
            <td>None</td>
            <td>None</td>
            <td>None</td>
            <td>Customer Cancellation</td>
        </tr>
        <tr>
            <td>10</td>
            <td>1</td>
            <td>2020-01-11 18:50:20</td>
            <td>10.0</td>
            <td>10</td>
            <td></td>
        </tr>
    </tbody>
</table>



# PIZZA METRICS

## 1.How many pizzas were ordered?


```sql
%%sql
SELECT COUNT(order_id)
FROM customer_orders 
```

     * postgresql://postgres:***@localhost/postgres
    1 rows affected.
    




<table>
    <thead>
        <tr>
            <th>count</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>14</td>
        </tr>
    </tbody>
</table>



## 2.How many unique customer orders were made?


```sql
%%sql
SELECT COUNT(DISTINCT(order_id))
FROM customer_orders 
```

     * postgresql://postgres:***@localhost/postgres
    1 rows affected.
    




<table>
    <thead>
        <tr>
            <th>count</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>10</td>
        </tr>
    </tbody>
</table>



## 3.How many successful orders were delivered by each runner?


```sql
%%sql 
SELECT runner_id, COUNT(order_id)
FROM runner_orders
WHERE distance IS NOT NULL
GROUP BY runner_id
ORDER BY runner_id
```

     * postgresql://postgres:***@localhost/postgres
    3 rows affected.
    




<table>
    <thead>
        <tr>
            <th>runner_id</th>
            <th>count</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>4</td>
        </tr>
        <tr>
            <td>2</td>
            <td>3</td>
        </tr>
        <tr>
            <td>3</td>
            <td>1</td>
        </tr>
    </tbody>
</table>



## 4.How many of each type of pizza was delivered?


```sql
%%sql 
SELECT p.pizza_name, 
    COUNT(p.pizza_name) AS delivered_pizza_count
FROM customer_orders c
    JOIN runner_orders r
    ON c.order_id = r.order_id
    JOIN pizza_runner.pizza_names p
    ON c.pizza_id = p.pizza_id
WHERE r.cancellation = ''
GROUP BY p.pizza_name
ORDER BY delivered_pizza_count DESC
```

     * postgresql://postgres:***@localhost/postgres
    2 rows affected.
    




<table>
    <thead>
        <tr>
            <th>pizza_name</th>
            <th>delivered_pizza_count</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Meatlovers</td>
            <td>9</td>
        </tr>
        <tr>
            <td>Vegetarian</td>
            <td>3</td>
        </tr>
    </tbody>
</table>



## 5.How many Vegetarian and Meatlovers were ordered by each customer?


```sql
%%sql
SELECT c.customer_id, SUM(CASE WHEN c.pizza_id = 1 THEN 1 ELSE 0 END) AS meatlovers, 
    SUM(CASE WHEN c.pizza_id = 2 THEN 1 ELSE 0 END) AS vegeterians
FROM customer_orders c
GROUP BY c.customer_id
ORDER BY c.customer_id
```

     * postgresql://postgres:***@localhost/postgres
    5 rows affected.
    




<table>
    <thead>
        <tr>
            <th>customer_id</th>
            <th>meatlovers</th>
            <th>vegeterians</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>101</td>
            <td>2</td>
            <td>1</td>
        </tr>
        <tr>
            <td>102</td>
            <td>2</td>
            <td>1</td>
        </tr>
        <tr>
            <td>103</td>
            <td>3</td>
            <td>1</td>
        </tr>
        <tr>
            <td>104</td>
            <td>3</td>
            <td>0</td>
        </tr>
        <tr>
            <td>105</td>
            <td>0</td>
            <td>1</td>
        </tr>
    </tbody>
</table>



## 6.What was the maximum number of pizzas delivered in a single order?


```sql
%%sql
WITH pizza_count_cte AS
(
 SELECT c.order_id, COUNT(c.pizza_id) AS pizza_per_order
     FROM customer_orders c
     JOIN runner_orders r
     ON c.order_id = r.order_id
 WHERE cancellation = ''
 GROUP BY c.order_id
)

SELECT MAX(pizza_per_order) AS pizza_count
FROM pizza_count_cte
```

     * postgresql://postgres:***@localhost/postgres
    1 rows affected.
    




<table>
    <thead>
        <tr>
            <th>pizza_count</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>3</td>
        </tr>
    </tbody>
</table>



## 7.For each customer, how many delivered pizzas had at least 1 change and how many had no changes?


```sql
%%sql
SELECT c.customer_id, 
SUM(CASE WHEN c.exclusions <> '' OR c.extras <> '' THEN 1 ELSE 0 END) AS at_least_1_change,
    SUM(CASE WHEN c.exclusions = '' AND c.extras = '' THEN 1 ELSE 0 END) AS no_change           
FROM customer_orders c
    JOIN runner_orders r
    ON c.order_id = r.order_id 
    
WHERE r.cancellation = ''
GROUP BY customer_id
ORDER BY customer_id
```

     * postgresql://postgres:***@localhost/postgres
    5 rows affected.
    




<table>
    <thead>
        <tr>
            <th>customer_id</th>
            <th>at_least_1_change</th>
            <th>no_change</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>101</td>
            <td>0</td>
            <td>2</td>
        </tr>
        <tr>
            <td>102</td>
            <td>0</td>
            <td>3</td>
        </tr>
        <tr>
            <td>103</td>
            <td>3</td>
            <td>0</td>
        </tr>
        <tr>
            <td>104</td>
            <td>2</td>
            <td>1</td>
        </tr>
        <tr>
            <td>105</td>
            <td>1</td>
            <td>0</td>
        </tr>
    </tbody>
</table>



## 8.How many pizzas were delivered that had both exclusions and extras?


```sql
%%sql
SELECT COUNT(c.order_id) AS pizza_counts
FROM customer_orders c
    JOIN runner_orders r
    ON c.order_id = r.order_id 
WHERE c.exclusions NOT LIKE '' AND c.extras NOT LIKE '' AND r.cancellation = ''
```

     * postgresql://postgres:***@localhost/postgres
    1 rows affected.
    




<table>
    <thead>
        <tr>
            <th>pizza_counts</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
        </tr>
    </tbody>
</table>



## 9.What was the total volume of pizzas ordered for each hour of the day?


```sql
%%sql
SELECT EXTRACT(HOUR FROM order_time)AS hour_of_day,
    COUNT(order_id) AS pizza_count
FROM customer_orders
GROUP BY hour_of_day
ORDER BY hour_of_day
```

     * postgresql://postgres:***@localhost/postgres
    6 rows affected.
    




<table>
    <thead>
        <tr>
            <th>hour_of_day</th>
            <th>pizza_count</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>11</td>
            <td>1</td>
        </tr>
        <tr>
            <td>13</td>
            <td>3</td>
        </tr>
        <tr>
            <td>18</td>
            <td>3</td>
        </tr>
        <tr>
            <td>19</td>
            <td>1</td>
        </tr>
        <tr>
            <td>21</td>
            <td>3</td>
        </tr>
        <tr>
            <td>23</td>
            <td>3</td>
        </tr>
    </tbody>
</table>



## 10. What was the volume of orders for each day of the week?


```sql
%%sql
SELECT TO_CHAR(order_time, 'Day') AS day_of_week,
    COUNT(order_id) AS total_pizzas_ordered
FROM customer_orders
GROUP BY day_of_week
```

     * postgresql://postgres:***@localhost/postgres
    4 rows affected.
    




<table>
    <thead>
        <tr>
            <th>day_of_week</th>
            <th>total_pizzas_ordered</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Saturday </td>
            <td>5</td>
        </tr>
        <tr>
            <td>Thursday </td>
            <td>3</td>
        </tr>
        <tr>
            <td>Friday   </td>
            <td>1</td>
        </tr>
        <tr>
            <td>Wednesday</td>
            <td>5</td>
        </tr>
    </tbody>
</table>



# RUNNER AND CUSTOMER EXPERIENCE

## 1.How many runners signed up for each 1 week period? (i.e. week starts 2021-01-01)


```sql
%%sql
SELECT 
    TO_CHAR(registration_date, 'WW') AS registration_week, 
    COUNT(runner_id)
FROM pizza_runner.runners
GROUP BY TO_CHAR(registration_date, 'WW')
ORDER BY registration_week
```

     * postgresql://postgres:***@localhost/postgres
    3 rows affected.
    




<table>
    <thead>
        <tr>
            <th>registration_week</th>
            <th>count</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>01</td>
            <td>2</td>
        </tr>
        <tr>
            <td>02</td>
            <td>1</td>
        </tr>
        <tr>
            <td>03</td>
            <td>1</td>
        </tr>
    </tbody>
</table>



## 2.What was the average time in minutes it took for each runner to arrive at the Pizza Runner HQ to pickup the order?


```sql
%%sql
WITH time_taken AS (
    SELECT p.runner_id, r.pickup_time, c.order_time, 
        EXTRACT(MINUTE FROM AGE(r.pickup_time,c.order_time)) AS pickup_minutes
FROM runner_orders r
    JOIN pizza_runner.runners p
    ON r.runner_id = p.runner_id
    JOIN customer_orders c
    ON r.order_id = c.order_id
WHERE r.cancellation = ''
GROUP BY p.runner_id, r.pickup_time, c.order_time
ORDER BY p.runner_id
)

SELECT runner_id, ROUND(AVG(pickup_minutes)::NUMERIC, 2) AS avg_pickup_duration
FROM time_taken
GROUP BY runner_id
```

     * postgresql://postgres:***@localhost/postgres
    3 rows affected.
    




<table>
    <thead>
        <tr>
            <th>runner_id</th>
            <th>avg_pickup_duration</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>14.00</td>
        </tr>
        <tr>
            <td>2</td>
            <td>19.67</td>
        </tr>
        <tr>
            <td>3</td>
            <td>10.00</td>
        </tr>
    </tbody>
</table>



## 3. Is there any relationship between the number of pizzas and how long the order takes to prepare?


```sql
%%sql
WITH prep_time AS (
SELECT c.order_id, COUNT(c.order_id) AS pizza_order, r.pickup_time, c.order_time,
    EXTRACT(MINUTE FROM AGE(r.pickup_time,c.order_time)) AS prep_minutes
FROM runner_orders r
    JOIN pizza_runner.runners p
    ON r.runner_id = p.runner_id
    JOIN customer_orders c
    ON r.order_id = c.order_id
WHERE r.cancellation = ''
GROUP BY c.order_id, r.pickup_time, c.order_time
)

SELECT pizza_order, ROUND(AVG(prep_minutes), 0) AS avg_prep_time
FROM prep_time
GROUP BY pizza_order
```

     * postgresql://postgres:***@localhost/postgres
    3 rows affected.
    




<table>
    <thead>
        <tr>
            <th>pizza_order</th>
            <th>avg_prep_time</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>3</td>
            <td>29</td>
        </tr>
        <tr>
            <td>2</td>
            <td>18</td>
        </tr>
        <tr>
            <td>1</td>
            <td>12</td>
        </tr>
    </tbody>
</table>



## 4. What was the average distance travelled for each customer?


```sql
%%sql
SELECT c.customer_id, ROUND(AVG(r.distance)::numeric, 0) AS avg_distance
FROM customer_orders c
    JOIN runner_orders r
    ON r.order_id = c.order_id
WHERE r.cancellation = ''
GROUP BY c.customer_id
ORDER BY avg_distance
```

     * postgresql://postgres:***@localhost/postgres
    5 rows affected.
    




<table>
    <thead>
        <tr>
            <th>customer_id</th>
            <th>avg_distance</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>104</td>
            <td>10</td>
        </tr>
        <tr>
            <td>102</td>
            <td>17</td>
        </tr>
        <tr>
            <td>101</td>
            <td>20</td>
        </tr>
        <tr>
            <td>103</td>
            <td>23</td>
        </tr>
        <tr>
            <td>105</td>
            <td>25</td>
        </tr>
    </tbody>
</table>



## 5.What was the difference between the longest and shortest delivery times for all orders?


```sql
%%sql
SELECT MAX(r.duration) - MIN(r.duration)
FROM customer_orders c
    JOIN runner_orders r
    ON r.order_id = c.order_id
WHERE r.cancellation = ''
```

     * postgresql://postgres:***@localhost/postgres
    1 rows affected.
    




<table>
    <thead>
        <tr>
            <th>?column?</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>30</td>
        </tr>
    </tbody>
</table>



## 6. What was the average speed for each runner for each delivery and do you notice any trend for these values?


```sql
%%sql
SELECT  order_id, runner_id,
   ROUND((distance/ duration * 60)::NUMERIC, 2) AS avg_speed
FROM runner_orders
WHERE duration IS NOT NULL
GROUP BY order_id, runner_id, distance, duration
ORDER BY order_id, runner_id
```

     * postgresql://postgres:***@localhost/postgres
    8 rows affected.
    




<table>
    <thead>
        <tr>
            <th>order_id</th>
            <th>runner_id</th>
            <th>avg_speed</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>1</td>
            <td>37.50</td>
        </tr>
        <tr>
            <td>2</td>
            <td>1</td>
            <td>44.44</td>
        </tr>
        <tr>
            <td>3</td>
            <td>1</td>
            <td>40.20</td>
        </tr>
        <tr>
            <td>4</td>
            <td>2</td>
            <td>35.10</td>
        </tr>
        <tr>
            <td>5</td>
            <td>3</td>
            <td>40.00</td>
        </tr>
        <tr>
            <td>7</td>
            <td>2</td>
            <td>60.00</td>
        </tr>
        <tr>
            <td>8</td>
            <td>2</td>
            <td>93.60</td>
        </tr>
        <tr>
            <td>10</td>
            <td>1</td>
            <td>60.00</td>
        </tr>
    </tbody>
</table>



## 7. What is the successful delivery percentage for each runner?


```sql
%%sql
SELECT runner_id, ROUND(100* SUM(CASE WHEN distance IS NOT NULL THEN 1
                        ELSE 0 END)/COUNT(*),0) AS successful_delivery_perc
FROM runner_orders
GROUP BY runner_id
```

     * postgresql://postgres:***@localhost/postgres
    3 rows affected.
    




<table>
    <thead>
        <tr>
            <th>runner_id</th>
            <th>successful_delivery_perc</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>3</td>
            <td>50</td>
        </tr>
        <tr>
            <td>2</td>
            <td>75</td>
        </tr>
        <tr>
            <td>1</td>
            <td>100</td>
        </tr>
    </tbody>
</table>



# INGREDIENT OPTIMIZATION

## 1. What are the standard ingredients for each pizza?


```sql
%%sql
WITH cte_toppings AS (
SELECT
pt.topping_name,
pr.pizza_id,
        pn.pizza_name
FROM pizza_runner.pizza_recipes pr
    JOIN pizza_runner.pizza_toppings pt ON pt.topping_id = ANY(string_to_array(pr.toppings, ',')::INT[])
    JOIN pizza_runner.pizza_names pn ON pn.pizza_id = pr.pizza_id
    ORDER BY pn.pizza_name)
SELECT
ct.pizza_name,
    ct.topping_name
FROM cte_toppings ct
```

     * postgresql://postgres:***@localhost/postgres
    14 rows affected.
    




<table>
    <thead>
        <tr>
            <th>pizza_name</th>
            <th>topping_name</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Meatlovers</td>
            <td>Bacon</td>
        </tr>
        <tr>
            <td>Meatlovers</td>
            <td>BBQ Sauce</td>
        </tr>
        <tr>
            <td>Meatlovers</td>
            <td>Beef</td>
        </tr>
        <tr>
            <td>Meatlovers</td>
            <td>Cheese</td>
        </tr>
        <tr>
            <td>Meatlovers</td>
            <td>Chicken</td>
        </tr>
        <tr>
            <td>Meatlovers</td>
            <td>Mushrooms</td>
        </tr>
        <tr>
            <td>Meatlovers</td>
            <td>Pepperoni</td>
        </tr>
        <tr>
            <td>Meatlovers</td>
            <td>Salami</td>
        </tr>
        <tr>
            <td>Vegetarian</td>
            <td>Cheese</td>
        </tr>
        <tr>
            <td>Vegetarian</td>
            <td>Mushrooms</td>
        </tr>
        <tr>
            <td>Vegetarian</td>
            <td>Onions</td>
        </tr>
        <tr>
            <td>Vegetarian</td>
            <td>Peppers</td>
        </tr>
        <tr>
            <td>Vegetarian</td>
            <td>Tomatoes</td>
        </tr>
        <tr>
            <td>Vegetarian</td>
            <td>Tomato Sauce</td>
        </tr>
    </tbody>
</table>



## 2. What was the most commonly added extra?


```sql
%%sql
WITH ct_extras AS (
SELECT
        pizza_id,
        unnest(string_to_array(NULLIF(extras, ''), ','))::INT AS extras
FROM customer_orders
)

SELECT extras,
   pt.topping_name,
    COUNT(extras) AS extras_count
FROM ct_extras ce
   JOIN pizza_runner.pizza_toppings pt 
    ON pt.topping_id = ce.extras
GROUP BY extras, pt.topping_name
ORDER BY extras_count DESC
```

     * postgresql://postgres:***@localhost/postgres
    3 rows affected.
    




<table>
    <thead>
        <tr>
            <th>extras</th>
            <th>topping_name</th>
            <th>extras_count</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Bacon</td>
            <td>4</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Cheese</td>
            <td>1</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Chicken</td>
            <td>1</td>
        </tr>
    </tbody>
</table>



## 3. What was the most common exclusion?


```sql
%%sql
WITH ct_exclusions AS (
SELECT
        pizza_id,
        unnest(string_to_array(NULLIF(exclusions, ''), ','))::INT AS exclusions
FROM customer_orders
)

SELECT exclusions,
   pt.topping_name,
    COUNT(exclusions) AS exclusions_count
FROM ct_exclusions ce
   JOIN pizza_runner.pizza_toppings pt 
    ON pt.topping_id = ce.exclusions
GROUP BY exclusions, pt.topping_name
ORDER BY exclusions_count DESC
```

     * postgresql://postgres:***@localhost/postgres
    3 rows affected.
    




<table>
    <thead>
        <tr>
            <th>exclusions</th>
            <th>topping_name</th>
            <th>exclusions_count</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>4</td>
            <td>Cheese</td>
            <td>4</td>
        </tr>
        <tr>
            <td>6</td>
            <td>Mushrooms</td>
            <td>1</td>
        </tr>
        <tr>
            <td>2</td>
            <td>BBQ Sauce</td>
            <td>1</td>
        </tr>
    </tbody>
</table>



## 4. Generate an order item for each record in the customers_orders


```sql
%%sql
SELECT c.order_id,
    c.pizza_id,
    pn.pizza_name,
    c.exclusions,
    c.extras,
    CASE WHEN c.pizza_id = 1 AND c.exclusions = '' AND c.extras = '' THEN 'Meat Lovers'
        WHEN c.pizza_id = 2 AND c.exclusions = '' AND c.extras = '' THEN 'Vegetarian'
        WHEN c.pizza_id = 1 AND c.exclusions = '4' AND c.extras = '' THEN 'Meat Lovers - Exclude Cheese'
        WHEN c.pizza_id = 2 AND c.exclusions = '4' AND c.extras = '' THEN 'Vegetarian - Exclude Cheese'
        WHEN c.pizza_id = 1 AND c.exclusions = '' AND c.extras = '1' THEN 'Meat Lovers - Extra Bacon'
        WHEN c.pizza_id = 2 AND c.exclusions = '' AND c.extras = '1' THEN 'Vegetarian - Extra Bacon'
        WHEN c.pizza_id = 1 AND c.exclusions = '4' AND c.extras = '1, 5' THEN 'Meat Lovers - Exclude Cheese - Extra Bacon and Chicken'
        WHEN c.pizza_id = 1 AND c.exclusions = '2, 6' AND c.extras = '1, 4' THEN 'Meat Lovers - Exclude BBQ Sauce and Mushroom - Extra Bacon and Cheese'
        END AS order_item
FROM customer_orders c
JOIN pizza_runner.pizza_names pn ON c.pizza_id = pn.pizza_id
```

     * postgresql://postgres:***@localhost/postgres
    14 rows affected.
    




<table>
    <thead>
        <tr>
            <th>order_id</th>
            <th>pizza_id</th>
            <th>pizza_name</th>
            <th>exclusions</th>
            <th>extras</th>
            <th>order_item</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>10</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td>2, 6</td>
            <td>1, 4</td>
            <td>Meat Lovers - Exclude BBQ Sauce and Mushroom - Extra Bacon and Cheese</td>
        </tr>
        <tr>
            <td>10</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td></td>
            <td></td>
            <td>Meat Lovers</td>
        </tr>
        <tr>
            <td>9</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td>4</td>
            <td>1, 5</td>
            <td>Meat Lovers - Exclude Cheese - Extra Bacon and Chicken</td>
        </tr>
        <tr>
            <td>8</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td></td>
            <td></td>
            <td>Meat Lovers</td>
        </tr>
        <tr>
            <td>5</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td></td>
            <td>1</td>
            <td>Meat Lovers - Extra Bacon</td>
        </tr>
        <tr>
            <td>4</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td>4</td>
            <td></td>
            <td>Meat Lovers - Exclude Cheese</td>
        </tr>
        <tr>
            <td>4</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td>4</td>
            <td></td>
            <td>Meat Lovers - Exclude Cheese</td>
        </tr>
        <tr>
            <td>3</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td></td>
            <td></td>
            <td>Meat Lovers</td>
        </tr>
        <tr>
            <td>2</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td></td>
            <td></td>
            <td>Meat Lovers</td>
        </tr>
        <tr>
            <td>1</td>
            <td>1</td>
            <td>Meatlovers</td>
            <td></td>
            <td></td>
            <td>Meat Lovers</td>
        </tr>
        <tr>
            <td>7</td>
            <td>2</td>
            <td>Vegetarian</td>
            <td></td>
            <td>1</td>
            <td>Vegetarian - Extra Bacon</td>
        </tr>
        <tr>
            <td>6</td>
            <td>2</td>
            <td>Vegetarian</td>
            <td></td>
            <td></td>
            <td>Vegetarian</td>
        </tr>
        <tr>
            <td>4</td>
            <td>2</td>
            <td>Vegetarian</td>
            <td>4</td>
            <td></td>
            <td>Vegetarian - Exclude Cheese</td>
        </tr>
        <tr>
            <td>3</td>
            <td>2</td>
            <td>Vegetarian</td>
            <td></td>
            <td></td>
            <td>Vegetarian</td>
        </tr>
    </tbody>
</table>



## 5. Generate an alphabetically ordered comma separated ingredient list for each pizza order from the customer_orders table and add a 2x in front of any relevant ingredients


```sql
%%sql
WITH cte_toppings AS (
    SELECT
        pt.topping_name,
        pr.pizza_id,
        pn.pizza_name
    FROM pizza_runner.pizza_recipes pr
    JOIN pizza_runner.pizza_toppings pt ON pt.topping_id = ANY(string_to_array(pr.toppings, ',')::INT[])
    JOIN pizza_runner.pizza_names pn ON pn.pizza_id = pr.pizza_id
    ORDER BY pn.pizza_name),
topping_group AS (
SELECT
    pizza_id,
    STRING_AGG(topping_name, ',') AS toppings
FROM cte_toppings
GROUP BY pizza_id)
SELECT
    c.order_id,
    c.customer_id,
    c.pizza_id,
    c.exclusions,
    c.extras,
    c.order_time,
    CASE
        WHEN ct.pizza_id = 1 THEN CONCAT(ct.pizza_name, ':', ' ', '2x', ' ', tg.toppings)
        WHEN ct.pizza_id = 2 THEN CONCAT(ct.pizza_name,':', ' ', '2x', ' ', tg.toppings)
    END AS ingredient_list
FROM cte_toppings ct
LEFT JOIN topping_group tg ON tg.pizza_id = ct.pizza_id
LEFT JOIN customer_orders c ON tg.pizza_id = c.pizza_id
GROUP BY c.order_id, c.exclusions, c.customer_id, c.pizza_id, 
         c.extras,c.order_time, ct.pizza_id, ct.pizza_name, tg.toppings  
```

     * postgresql://postgres:***@localhost/postgres
    13 rows affected.
    




<table>
    <thead>
        <tr>
            <th>order_id</th>
            <th>customer_id</th>
            <th>pizza_id</th>
            <th>exclusions</th>
            <th>extras</th>
            <th>order_time</th>
            <th>ingredient_list</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>3</td>
            <td>102</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-02 23:51:23</td>
            <td>Meatlovers: 2x Bacon,BBQ Sauce,Beef,Cheese,Chicken,Mushrooms,Pepperoni,Salami</td>
        </tr>
        <tr>
            <td>8</td>
            <td>102</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-09 23:54:33</td>
            <td>Meatlovers: 2x Bacon,BBQ Sauce,Beef,Cheese,Chicken,Mushrooms,Pepperoni,Salami</td>
        </tr>
        <tr>
            <td>10</td>
            <td>104</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-11 18:34:49</td>
            <td>Meatlovers: 2x Bacon,BBQ Sauce,Beef,Cheese,Chicken,Mushrooms,Pepperoni,Salami</td>
        </tr>
        <tr>
            <td>5</td>
            <td>104</td>
            <td>1</td>
            <td></td>
            <td>1</td>
            <td>2020-01-08 21:00:29</td>
            <td>Meatlovers: 2x Bacon,BBQ Sauce,Beef,Cheese,Chicken,Mushrooms,Pepperoni,Salami</td>
        </tr>
        <tr>
            <td>4</td>
            <td>103</td>
            <td>1</td>
            <td>4</td>
            <td></td>
            <td>2020-01-04 13:23:46</td>
            <td>Meatlovers: 2x Bacon,BBQ Sauce,Beef,Cheese,Chicken,Mushrooms,Pepperoni,Salami</td>
        </tr>
        <tr>
            <td>2</td>
            <td>101</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-01 19:00:52</td>
            <td>Meatlovers: 2x Bacon,BBQ Sauce,Beef,Cheese,Chicken,Mushrooms,Pepperoni,Salami</td>
        </tr>
        <tr>
            <td>3</td>
            <td>102</td>
            <td>2</td>
            <td></td>
            <td></td>
            <td>2020-01-02 23:51:23</td>
            <td>Vegetarian: 2x Cheese,Mushrooms,Onions,Peppers,Tomatoes,Tomato Sauce</td>
        </tr>
        <tr>
            <td>9</td>
            <td>103</td>
            <td>1</td>
            <td>4</td>
            <td>1, 5</td>
            <td>2020-01-10 11:22:59</td>
            <td>Meatlovers: 2x Bacon,BBQ Sauce,Beef,Cheese,Chicken,Mushrooms,Pepperoni,Salami</td>
        </tr>
        <tr>
            <td>7</td>
            <td>105</td>
            <td>2</td>
            <td></td>
            <td>1</td>
            <td>2020-01-08 21:20:29</td>
            <td>Vegetarian: 2x Cheese,Mushrooms,Onions,Peppers,Tomatoes,Tomato Sauce</td>
        </tr>
        <tr>
            <td>6</td>
            <td>101</td>
            <td>2</td>
            <td></td>
            <td></td>
            <td>2020-01-08 21:03:13</td>
            <td>Vegetarian: 2x Cheese,Mushrooms,Onions,Peppers,Tomatoes,Tomato Sauce</td>
        </tr>
        <tr>
            <td>1</td>
            <td>101</td>
            <td>1</td>
            <td></td>
            <td></td>
            <td>2020-01-01 18:05:02</td>
            <td>Meatlovers: 2x Bacon,BBQ Sauce,Beef,Cheese,Chicken,Mushrooms,Pepperoni,Salami</td>
        </tr>
        <tr>
            <td>10</td>
            <td>104</td>
            <td>1</td>
            <td>2, 6</td>
            <td>1, 4</td>
            <td>2020-01-11 18:34:49</td>
            <td>Meatlovers: 2x Bacon,BBQ Sauce,Beef,Cheese,Chicken,Mushrooms,Pepperoni,Salami</td>
        </tr>
        <tr>
            <td>4</td>
            <td>103</td>
            <td>2</td>
            <td>4</td>
            <td></td>
            <td>2020-01-04 13:23:46</td>
            <td>Vegetarian: 2x Cheese,Mushrooms,Onions,Peppers,Tomatoes,Tomato Sauce</td>
        </tr>
    </tbody>
</table>



## 6. What is the total quantity of each ingredient used in all delivered pizzas sorted by most frequent first?


```sql
%%sql
WITH ct_toppings AS ( 
SELECT pizza_id,
    unnest(string_to_array(NULLIF(pr.toppings, ''), ','))::INT AS toppings
FROM pizza_runner.pizza_recipes pr
)

SELECT toppings, pt.topping_name, COUNT(toppings) AS qty_ingredient
FROM ct_toppings ct
    JOIN pizza_runner.pizza_toppings pt 
    ON pt.topping_id = ct.toppings
    JOIN customer_orders c 
    ON ct.pizza_id = c.pizza_id
    LEFT JOIN runner_orders r 
    ON r.order_id = c.order_id
WHERE r.cancellation = ''
GROUP BY toppings, topping_name
ORDER BY qty_ingredient desc;
```

     * postgresql://postgres:***@localhost/postgres
    12 rows affected.
    




<table>
    <thead>
        <tr>
            <th>toppings</th>
            <th>topping_name</th>
            <th>qty_ingredient</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>6</td>
            <td>Mushrooms</td>
            <td>12</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Cheese</td>
            <td>12</td>
        </tr>
        <tr>
            <td>8</td>
            <td>Pepperoni</td>
            <td>9</td>
        </tr>
        <tr>
            <td>10</td>
            <td>Salami</td>
            <td>9</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Bacon</td>
            <td>9</td>
        </tr>
        <tr>
            <td>2</td>
            <td>BBQ Sauce</td>
            <td>9</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Chicken</td>
            <td>9</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Beef</td>
            <td>9</td>
        </tr>
        <tr>
            <td>11</td>
            <td>Tomatoes</td>
            <td>3</td>
        </tr>
        <tr>
            <td>9</td>
            <td>Peppers</td>
            <td>3</td>
        </tr>
        <tr>
            <td>12</td>
            <td>Tomato Sauce</td>
            <td>3</td>
        </tr>
        <tr>
            <td>7</td>
            <td>Onions</td>
            <td>3</td>
        </tr>
    </tbody>
</table>



# PRICING AND RATINGS

## 1.If a Meat Lovers pizza costs  12 and Vegetarian costs  10 and there were no charges for changes - how much money has Pizza Runner made so far if there are no delivery fees?


```sql
%%sql
SELECT SUM(CASE WHEN c.pizza_id = 1 THEN 12 
    ELSE 10
    END) AS total_pizza_price
FROM customer_orders c
    JOIN runner_orders r
    ON c.order_id = r.order_id
WHERE r.cancellation = ''
```

     * postgresql://postgres:***@localhost/postgres
    1 rows affected.
    




<table>
    <thead>
        <tr>
            <th>total_pizza_price</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>138</td>
        </tr>
    </tbody>
</table>



## 2. What if there was an additional 1 charge for any pizza extras?


```sql
%%sql
SELECT SUM(CASE WHEN c.pizza_id = 1 THEN 12 + (CASE WHEN c.extras IS NOT NULL THEN 1 ELSE 0 END)
    ELSE 10 + (CASE WHEN c.extras IS NOT NULL THEN 1 ELSE 0 END)
    END) AS pizza_price
FROM customer_orders c
    JOIN runner_orders r
    ON c.order_id = r.order_id
WHERE r.cancellation = ''
```

     * postgresql://postgres:***@localhost/postgres
    1 rows affected.
    




<table>
    <thead>
        <tr>
            <th>pizza_price</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>150</td>
        </tr>
    </tbody>
</table>



## 3. The Pizza Runner team now wants to add an additional ratings system that allows customers to rate their runner, how would you design an additional table for this new dataset - generate a schema for this new table and insert your own data for ratings for each successful customer order between 1 to 5.


```sql
%%sql
DROP TABLE IF EXISTS ratings;
CREATE TABLE ratings (
order_id int,
rating int);

INSERT INTO ratings VALUES 
(1, 4), (2, 2), (3, 4), (4, 5), (5,2), (7, 4), (8, 3), (10, 5);

SELECT * FROM ratings
```

     * postgresql://postgres:***@localhost/postgres
    Done.
    Done.
    8 rows affected.
    8 rows affected.
    




<table>
    <thead>
        <tr>
            <th>order_id</th>
            <th>rating</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>4</td>
        </tr>
        <tr>
            <td>2</td>
            <td>2</td>
        </tr>
        <tr>
            <td>3</td>
            <td>4</td>
        </tr>
        <tr>
            <td>4</td>
            <td>5</td>
        </tr>
        <tr>
            <td>5</td>
            <td>2</td>
        </tr>
        <tr>
            <td>7</td>
            <td>4</td>
        </tr>
        <tr>
            <td>8</td>
            <td>3</td>
        </tr>
        <tr>
            <td>10</td>
            <td>5</td>
        </tr>
    </tbody>
</table>



## 4.Using your newly generated table - can you join all of the information together to form a table which has the following information for successful deliveries?


```sql
%%sql
SELECT c.customer_id, c.order_id, r.runner_id, c.order_time,
        r.pickup_time, EXTRACT(MINUTE FROM AGE(r.pickup_time,c.order_time)) AS prep_time,
        r.duration AS delivery_duration, ROUND(((r.distance/r.duration)* 60)::NUMERIC, 2) AS Avg_speed,
        count(c.pizza_id) AS pizza_counts
FROM customer_orders c
    JOIN runner_orders r
    ON c.order_id = r.order_id
    JOIN ratings rt
    ON c.order_id = rt.order_id
WHERE r.cancellation = ''
GROUP BY c.customer_id, c.order_id, r.runner_id, c.order_time,
       r.pickup_time, prep_time, delivery_duration, Avg_speed
ORDER BY c.customer_id
```

     * postgresql://postgres:***@localhost/postgres
    8 rows affected.
    




<table>
    <thead>
        <tr>
            <th>customer_id</th>
            <th>order_id</th>
            <th>runner_id</th>
            <th>order_time</th>
            <th>pickup_time</th>
            <th>prep_time</th>
            <th>delivery_duration</th>
            <th>avg_speed</th>
            <th>pizza_counts</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>101</td>
            <td>1</td>
            <td>1</td>
            <td>2020-01-01 18:05:02</td>
            <td>2020-01-01 18:15:34</td>
            <td>10</td>
            <td>32</td>
            <td>37.50</td>
            <td>1</td>
        </tr>
        <tr>
            <td>101</td>
            <td>2</td>
            <td>1</td>
            <td>2020-01-01 19:00:52</td>
            <td>2020-01-01 19:10:54</td>
            <td>10</td>
            <td>27</td>
            <td>44.44</td>
            <td>1</td>
        </tr>
        <tr>
            <td>102</td>
            <td>3</td>
            <td>1</td>
            <td>2020-01-02 23:51:23</td>
            <td>2020-01-03 00:12:37</td>
            <td>21</td>
            <td>20</td>
            <td>40.20</td>
            <td>2</td>
        </tr>
        <tr>
            <td>102</td>
            <td>8</td>
            <td>2</td>
            <td>2020-01-09 23:54:33</td>
            <td>2020-01-10 00:15:02</td>
            <td>20</td>
            <td>15</td>
            <td>93.60</td>
            <td>1</td>
        </tr>
        <tr>
            <td>103</td>
            <td>4</td>
            <td>2</td>
            <td>2020-01-04 13:23:46</td>
            <td>2020-01-04 13:53:03</td>
            <td>29</td>
            <td>40</td>
            <td>35.10</td>
            <td>3</td>
        </tr>
        <tr>
            <td>104</td>
            <td>5</td>
            <td>3</td>
            <td>2020-01-08 21:00:29</td>
            <td>2020-01-08 21:10:57</td>
            <td>10</td>
            <td>15</td>
            <td>40.00</td>
            <td>1</td>
        </tr>
        <tr>
            <td>104</td>
            <td>10</td>
            <td>1</td>
            <td>2020-01-11 18:34:49</td>
            <td>2020-01-11 18:50:20</td>
            <td>15</td>
            <td>10</td>
            <td>60.00</td>
            <td>2</td>
        </tr>
        <tr>
            <td>105</td>
            <td>7</td>
            <td>2</td>
            <td>2020-01-08 21:20:29</td>
            <td>2020-01-08 21:30:45</td>
            <td>10</td>
            <td>25</td>
            <td>60.00</td>
            <td>1</td>
        </tr>
    </tbody>
</table>



## 5. If a Meat Lovers pizza was 12 and Vegetarian 10 fixed prices with no cost for extras and each runner is paid 0.30 per kilometre traveled - how much money does Pizza Runner have left over after these deliveries?


```sql
%%sql
SELECT SUM(CASE WHEN c.pizza_id = 1 THEN 12  - (r.distance*0.30)
           ELSE 10 - (r.distance*0.30) 
           END) AS pizza_price
FROM customer_orders c
    JOIN runner_orders r
    ON c.order_id = r.order_id
WHERE r.cancellation = ''
```

     * postgresql://postgres:***@localhost/postgres
    1 rows affected.
    




<table>
    <thead>
        <tr>
            <th>pizza_price</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>73.38000000000001</td>
        </tr>
    </tbody>
</table>


