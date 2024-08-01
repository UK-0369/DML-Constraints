# DML-Constraints
CREATE DATABASE Sales;
USE Sales;
CREATE TABLE Orders (
    Order_Id INT PRIMARY KEY,
    Customer_name VARCHAR(255) NOT NULL,
    Product_Category VARCHAR(255) NOT NULL,
    Ordered_item VARCHAR(255) UNIQUE NOT NULL,
    Contact_No VARCHAR(20) NOT NULL
);
ALTER TABLE Orders
ADD order_quantity INT;
RENAME TABLE Orders TO sales_orders;
INSERT INTO sales_orders (Order_Id, Customer_name, Product_Category, Ordered_item, Contact_No, order_quantity) VALUES

(1, 'Unnikrishnan', 'Electronics', 'Smart watch', '123-456-7890', 2),
(2, 'Abijith', 'Electronics', 'Laptop', '234-567-8901', 5),
(3, 'Harikrishnan', 'Electronics', 'Tablet', '345-678-9012', 1),
(4, 'Walter White', 'Furniture', 'Desk', '456-789-0123', 4),
(5, 'Hank', 'Clothing', 'Jacket', '567-890-1234', 3),
(6, 'Jessie', 'Appliances', 'Microwave', '678-901-2345', 1),
(7, 'Sadie', 'Electronics', 'Smartwatch', '789-012-3456', 6),
(8, 'Jake', 'Furniture', 'Bookshelf', '890-123-4567', 2),
(9, 'Skylar', 'Appliances', 'Blender', '901-234-5678', 1),
(10, 'Marie', 'Clothing', 'Shoes', '012-345-6789', 4);
SELECT Customer_name, Ordered_item
FROM sales_orders;
UPDATE sales_orders
SET Ordered_item = 'iphone'
WHERE Order_Id = 2;
DROP TABLE sales_orders;
