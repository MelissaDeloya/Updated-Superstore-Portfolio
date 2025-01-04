Superstore 

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

-- Query #1 
item_name	price
Smart LED TV	549
Memory Foam Mattress	499.99
Robot Vacuum Cleaner	199.5
Ergonomic Office Chair	189
Air Purifier	129.5
Stainless Steel Cookware Set	89.99
Cotton Bedding Set	89
Premium Coffee Maker	79.99
Smart Home Security Camera	79.95
Wireless Earbuds	49.99
Slow Cooker	49.95
Wireless Bluetooth Speaker	39.99
Cutlery Set	34.5
Non-Stick Baking Set	29.95
Cozy Throw Blanket	24.99

--Statistic of item prices - average 
SELECT AVG(price), item_name
FROM superstore
GROUP BY item_name
ORDER BY price desc;

-- Query #2 
AVG(price)	item_name
549	Smart LED TV
499.99	Memory Foam Mattress
199.5	Robot Vacuum Cleaner
189	Ergonomic Office Chair
129.5	Air Purifier
89.99	Stainless Steel Cookware Set
89	Cotton Bedding Set
79.99	Premium Coffee Maker
79.95	Smart Home Security Camera
49.99	Wireless Earbuds
49.95	Slow Cooker
39.99	Wireless Bluetooth Speaker
34.5	Cutlery Set
29.95	Non-Stick Baking Set
24.99	Cozy Throw Blanket

--Statistic about the price for items in the category of "Kitchen Supplies" -- Max Price
SELECT MAX(price), item_name
FROM superstore 
WHERE category = "Kitchen Supplies" ;

--Query #3 
MAX(price)	item_name
89.99	Stainless Steel Cookware Set

--How many air purifiers are in stock?
SELECT SUM(stock_quantity)
FROM superstore
WHERE item_name = "Air Purifier";

-- Query #4 
SUM(stock_quantity)
35
