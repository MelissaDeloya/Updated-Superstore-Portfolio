# Updated-Superstore-Portfolio
CREATE TABLE ecom_data (
    user_id VARCHAR(50),
    session_duration INT,
    purchase_flag BIT,
    amount_spent DECIMAL(10, 2),
    item_name VARCHAR(50)
);

INSERT INTO ecom_data (user_id, session_duration, purchase_flag, amount_spent, item_name)
VALUES
    ('aBcDeF123456', 3, 1, 25.50, 'Wireless Earbuds'),
    ('gHiJkL789012', 4, 0, 0.00, NULL),
    ('mNoPqR345678', 6, 1, 75.20, 'Smartphone Case'),
    ('sTuVwX901234', 2, 0, 0.00, NULL),
    ('yZaBcD567890', 5, 1, 10.75, 'Portable Charger'),
    ('eFgHiJ123456', 4, 0, 0.00, NULL),
    ('kLmNoP789012', 1, 1, 50.00, 'Bluetooth Speaker'),
    ('qRsTuV345678', 2, 0, 0.00, NULL),
    ('wXyZaB901234', 3, 1, 20.90, 'Fitness Tracker'),
    ('zN53qR345321', 6, 1, 75.20, 'Smartphone Case'),
    ('QrSFgH561764', 1, 1, 50.00, 'Bluetooth Speaker'),
    ('cDeFgH567890', 4, 1, 150.75, 'Smartwatch');
    


Superstore 
--Sum of session
SELECT SUM(session_duration)
FROM ecom_data;

--Select the SUM of minutes that all users spent shopping for each item.
SELECT SUM (session_duration), item_name
FROM ecom_data 
GROUP BY item_name

SELECT * FROM movies;

CREATE TABLE movies (
	id INTEGER PRIMARY KEY,
	title TEXT,
	released INTEGER
);

INSERT INTO movies VALUES (1, "Tenet", 2020);
INSERT INTO movies VALUES (2, "Wonder Woman 1984", 2020);
INSERT INTO movies VALUES (3, "Soul", 2020);
INSERT INTO movies VALUES (4, "The Midnight Sky", 2020);
INSERT INTO movies VALUES (5, "Godzilla vs. Kong", 2021);
INSERT INTO movies VALUES (6, "A Quiet Place Part II", 2021);

SELECT * FROM movies
WHERE released >= 2021
ORDER BY released asc;

CREATE TABLE superstore (
    item_id INTEGER PRIMARY KEY,
    item_name TEXT,
    category TEXT,
    price DECIMAL(10, 2),
    stock_quantity INTEGER,
    average_rating DECIMAL(3, 2)
);

INSERT INTO superstore (item_id, item_name, category, price, stock_quantity, average_rating)
VALUES
    (1, 'Stainless Steel Cookware Set', 'Kitchen Supplies', 89.99, 50, 4.6),
    (2, 'Memory Foam Mattress', 'Furnishings', 499.99, 30, 4.8),
    (3, 'Smart LED TV', 'Electronics', 549.00, 20, 4.5),
    (4, 'Robot Vacuum Cleaner', 'Appliances', 199.50, 40, 4.3),
    (5, 'Wireless Bluetooth Speaker', 'Electronics', 39.99, 60, 4.2),
    (6, 'Non-Stick Baking Set', 'Kitchen Supplies', 29.95, 80, 4.4),
    (7, 'Cotton Bedding Set', 'Furnishings', 89.00, 25, 4.7),
    (8, 'Smart Home Security Camera', 'Electronics', 79.95, 15, 4.1),
    (9, 'Air Purifier', 'Appliances', 129.50, 35, 4.6),
    (10, 'Premium Coffee Maker', 'Kitchen Supplies', 79.99, 50, 4.9),
    (11, 'Ergonomic Office Chair', 'Furnishings', 189.00, 20, 4.5),
    (12, 'Wireless Earbuds', 'Electronics', 49.99, 75, 4.3),
    (13, 'Slow Cooker', 'Appliances', 49.95, 30, 4.7),
    (14, 'Cutlery Set', 'Kitchen Supplies', 34.50, 40, 4.4),
    (15, 'Cozy Throw Blanket', 'Furnishings', 24.99, 100, 4.2);

-- Items by price
SELECT item_name , price
FROM superstore
ORDER BY price desc;

--Statistic of item prices - average 
SELECT AVG(price), item_name
FROM superstore
GROUP BY item_name
ORDER BY price desc;

--Statistic about the price for items in the category of "Kitchen Supplies" -- Max Price
SELECT MAX(price), item_name
FROM superstore 
WHERE category = "Kitchen Supplies" ;

--How many air purifiers are in stock?
SELECT SUM(stock_quantity)
FROM superstore
WHERE item_name = "Air Purifier";
