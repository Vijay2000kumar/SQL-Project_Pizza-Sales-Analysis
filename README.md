# Pizza Orders SQL Analysis

## Project Overview

This project involves analyzing pizza orders using SQL. The data is organized across multiple tables, each capturing different aspects of the orders, including order details, pizza types, and pricing.

## Datasets Schema

### 1. Table: `order_details`
This table contains details about each order, including the unique order details ID, the order ID it belongs to, the pizza ID, and the quantity of each pizza ordered.

| Column             | Description                             |
|--------------------|-----------------------------------------|
| `order_details_id` | Unique identifier for the order detail. |
| `order_id`         | Identifier for the order.               |
| `pizza_id`         | Identifier for the pizza.               |
| `quantity`         | Quantity of the pizza ordered.          |

**Sample Data:**

| order_details_id | order_id | pizza_id       | quantity |
|------------------|----------|----------------|----------|
| 1                | 1        | hawaiian_m     | 1        |
| 2                | 2        | classic_dlx_m  | 1        |
| 3                | 2        | five_cheese_l  | 1        |
| 4                | 2        | ital_supr_l    | 1        |
| 5                | 2        | mexicana_m     | 1        |
| 6                | 2        | thai_ckn_l     | 1        |
| 7                | 3        | ital_supr_m    | 1        |
| 8                | 3        | prsc_argla_l   | 1        |
| 9                | 4        | ital_supr_m    | 1        |
| 10               | 5        | ital_supr_m    | 1        |
| 11               | 6        | bbq_ckn_s      | 1        |
| 12               | 6        | the_greek_s    | 1        |
| 13               | 7        | spinach_supr_s | 1        |
| 14               | 8        | spinach_supr_s | 1        |
| 15               | 9        | classic_dlx_s  | 1        |
| 16               | 9        | green_garden_s | 1        |
| 17               | 9        | ital_cpcllo_l  | 1        |
| 18               | 9        | ital_supr_l    | 1        |
| 19               | 9        | ital_supr_s    | 1        |
| 20               | 9        | mexicana_s     | 1        |
| 21               | 9        | spicy_ital_l   | 1        |
| 22               | 9        | spin_pesto_l   | 1        |

### 2. Table: `order_id`
This table captures the order timing details, including the order ID, date, and time of the order.

| Column   | Description               |
|----------|---------------------------|
| `order_id` | Unique identifier for the order. |
| `date`      | Date when the order was placed.  |
| `time`      | Time when the order was placed.  |

**Sample Data:**

| order_id | date       | time     |
|----------|------------|----------|
| 1        | 01-01-2015 | 11:38:36 |
| 2        | 01-01-2015 | 11:57:40 |
| 3        | 01-01-2015 | 12:12:28 |
| 4        | 01-01-2015 | 12:16:31 |
| 5        | 01-01-2015 | 12:21:30 |
| 6        | 01-01-2015 | 12:29:36 |
| 7        | 01-01-2015 | 12:50:37 |
| 8        | 01-01-2015 | 12:51:37 |
| 9        | 01-01-2015 | 12:52:01 |
| 10       | 01-01-2015 | 13:00:15 |
| 11       | 01-01-2015 | 13:02:59 |
| 12       | 01-01-2015 | 13:04:41 |
| 13       | 01-01-2015 | 13:11:55 |
| 14       | 01-01-2015 | 13:14:19 |
| 15       | 01-01-2015 | 13:33:00 |
| 16       | 01-01-2015 | 13:34:07 |
| 17       | 01-01-2015 | 13:53:00 |
| 18       | 01-01-2015 | 13:57:08 |
| 19       | 01-01-2015 | 13:59:09 |
| 20       | 01-01-2015 | 14:03:08 |
| 21       | 01-01-2015 | 14:14:29 |
| 22       | 01-01-2015 | 14:16:26 |

### 3. Table: `pizzatype_id`
This table describes the various types of pizzas available, including the pizza type ID, name, category, and ingredients.

| Column          | Description                               |
|-----------------|-------------------------------------------|
| `pizza_type_id` | Unique identifier for the pizza type.     |
| `name`          | Name of the pizza.                        |
| `category`      | Category of the pizza (e.g., Chicken, Classic, Supreme). |
| `ingredients`   | Ingredients used in the pizza.            |

**Sample Data:**

| pizza_type_id | name                          | category | ingredients                                                 |
|---------------|-------------------------------|----------|-------------------------------------------------------------|
| bbq_ckn       | The Barbecue Chicken Pizza    | Chicken  | Barbecued Chicken, Red Peppers, Green Peppers, Tomatoes, Red Onions, Barbecue Sauce |
| cali_ckn      | The California Chicken Pizza  | Chicken  | Chicken, Artichoke, Spinach, Garlic, Jalapeno Peppers, Fontina Cheese, Gouda Cheese |
| ckn_alfredo   | The Chicken Alfredo Pizza     | Chicken  | Chicken, Red Onions, Red Peppers, Mushrooms, Asiago Cheese, Alfredo Sauce |
| ckn_pesto     | The Chicken Pesto Pizza       | Chicken  | Chicken, Tomatoes, Red Peppers, Spinach, Garlic, Pesto Sauce |
| southw_ckn    | The Southwest Chicken Pizza   | Chicken  | Chicken, Tomatoes, Red Peppers, Red Onions, Jalapeno Peppers, Corn, Cilantro, Chipotle Sauce |
| thai_ckn      | The Thai Chicken Pizza        | Chicken  | Chicken, Pineapple, Tomatoes, Red Peppers, Thai Sweet Chilli Sauce |
| big_meat      | The Big Meat Pizza            | Classic  | Bacon, Pepperoni, Italian Sausage, Chorizo Sausage |
| classic_dlx   | The Classic Deluxe Pizza      | Classic  | Pepperoni, Mushrooms, Red Onions, Red Peppers, Bacon |
| hawaiian      | The Hawaiian Pizza            | Classic  | Sliced Ham, Pineapple, Mozzarella Cheese |
| ital_cpcllo   | The Italian Capocollo Pizza   | Classic  | Capocollo, Red Peppers, Tomatoes, Goat Cheese, Garlic, Oregano |
| napolitana    | The Napolitana Pizza          | Classic  | Tomatoes, Anchovies, Green Olives, Red Onions, Garlic |
| pep_msh_pep   | The Pepperoni, Mushroom, and Peppers Pizza | Classic | Pepperoni, Mushrooms, Green Peppers |
| pepperoni     | The Pepperoni Pizza           | Classic  | Mozzarella Cheese, Pepperoni |
| the_greek     | The Greek Pizza               | Classic  | Kalamata Olives, Feta Cheese, Tomatoes, Garlic, Beef Chuck Roast, Red Onions |
| brie_carre    | The Brie Carre Pizza          | Supreme  | Brie Carre Cheese, Prosciutto, Caramelized Onions, Pears, Thyme, Garlic |
| calabrese     | The Calabrese Pizza           | Supreme  | ‘Nduja Salami, Pancetta, Tomatoes, Red Onions, Friggitello Peppers, Garlic |
| ital_supr     | The Italian Supreme Pizza     | Supreme  | Calabrese Salami, Capocollo, Tomatoes, Red Onions, Green Olives, Garlic |
| peppr_salami  | The Pepper Salami Pizza       | Supreme  | Genoa Salami, Capocollo, Pepperoni, Tomatoes, Asiago Cheese, Garlic |
| prsc_argla    | The Prosciutto and Arugula Pizza | Supreme | Prosciutto di San Daniele, Arugula, Mozzarella Cheese |
| sicilian      | The Sicilian Pizza            | Supreme  | Coarse Sicilian Salami, Tomatoes, Green Olives, Luganega Sausage, Onions, Garlic |
| soppressata   | The Soppressata Pizza         | Supreme  | Soppressata Salami, Fontina Cheese, Mozzarella Cheese, Mushrooms, Garlic |

### 4. Table: `pizza_id`
This table lists individual pizzas, including the pizza ID, type ID, size, and price.

| Column        | Description                       |
|---------------|-----------------------------------|
| `pizza_id`    | Unique identifier for the pizza.  |
| `pizza_type_id` | Identifier for the type of pizza. |
| `size`        | Size of the pizza (S, M, L).      |
| `price`       | Price of the pizza.               |

**Sample Data:**

| pizza_id     | pizza_type_id | size | price |
|--------------|---------------|------|-------|
| bbq_ckn_s    | bbq_ckn       | S    | 12.75 |
| bbq_ckn_m    | bbq_ckn       | M    | 16.75 |
| bbq_ckn_l    | bbq_ckn       | L    | 20.75 |
| cali_ckn_s   | cali_ckn      | S    | 12.75 |
| cali_ckn_m   | cali_ckn      | M    | 16.75 |
| cali_ckn_l   | cali_ckn      | L    | 20.75 |
| ckn_alfredo_s| ckn_alfredo   | S    | 12.75 |
| ckn_alfredo_m| ckn_alfredo   | M    | 16.75 |
| ckn_alfredo_l| ckn_alfredo   | L    | 20.75 |
| ckn_pesto_s  | ckn_pesto     | S    | 12.75 |
| ckn_pesto_m  | ckn_pesto     | M    | 16.75 |
| ckn_pesto_l  | ckn_pesto     | L    | 20.75 |
| southw_ckn_s | southw_ckn    | S    | 12.75 |
| southw_ckn_m | southw_ckn    | M    | 16.75 |
| southw_ckn_l | southw_ckn    | L    | 20.75 |
| thai_ckn_s   | thai_ckn      | S    | 12.75 |
| thai_ckn_m   | thai_ckn      | M    | 16.75 |
| thai_ckn_l   | thai_ckn      | L    | 20.75 |

## SQL Queries

### Basic Queries
1. **Retrieve the total number of orders placed:**
2. **Calculate the total revenue generated from pizza sales.**
3. **Identify the highest-priced pizza.**
4. **Identify the most common pizza size ordered.**
5. **List the top 5 most ordered pizza types along with their quantities.**

###Intermediate:
1. **Join the necessary tables to find the total quantity of each pizza category ordered.**
2. **Determine the distribution of orders by hour of the day.**
3. **Join relevant tables to find the category-wise distribution of pizzas.:**
4. **Group the orders by date and calculate the average number of pizzas ordered per day.**
5. **Determine the top 3 most ordered pizza types based on revenue.**

###Advanced:
1. Calculate the percentage contribution of each pizza type to total revenue.

2. Analyze the cumulative revenue generated over time.

3. Determine the top 3 most ordered pizza types based on revenue for each pizza category.

   
