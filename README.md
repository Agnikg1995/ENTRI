-- 1. Create Sales database and Orders table
CREATE DATABASE IF NOT EXISTS Sales;
USE Sales;

CREATE TABLE IF NOT EXISTS Orders (
    Order_Id INT AUTO_INCREMENT PRIMARY KEY,
    Customer_name VARCHAR(255) NOT NULL,
    Product_Category VARCHAR(255) NOT NULL,
    Ordered_item VARCHAR(255) NOT NULL,
    Contact_No VARCHAR(20) NOT NULL,
    UNIQUE (Order_Id)
);

-- 2. Add a new column named “order_quantity1” to the orders table
ALTER TABLE Orders
ADD COLUMN order_quantity1 INT;

-- 3. Rename the orders table to the sales_orders table
ALTER TABLE Orders
RENAME TO sales_orders;

-- 4. Insert 10 rows into the sales_orders table
INSERT INTO sales_orders (Customer_name, Product_Category, Ordered_item, Contact_No, order_quantity) 
VALUES 
('John Doe', 'Electronics', 'Smartphone', '1234567890', 1),
('Jane Smith', 'Clothing', 'T-shirt', '9876543210', 2),
('Alice Johnson', 'Books', 'Novel', '5555555555', 3),
('Bob Brown', 'Electronics', 'Laptop', '6666666666', 1),
('Emma Davis', 'Home Appliances', 'Refrigerator', '7777777777', 1),
('Michael Wilson', 'Toys', 'Action Figure', '8888888888', 5),
('Sarah Lee', 'Clothing', 'Jeans', '9999999999', 2),
('David Martin', 'Books', 'Textbook', '1111111111', 1),
('Olivia Garcia', 'Electronics', 'Headphones', '2222222222', 1),
('James Rodriguez', 'Home Appliances', 'Microwave', '3333333333', 1);

-- 5. Retrieve customer_name and Ordered_Item from the sales_orders table
SELECT Customer_name, Ordered_item FROM sales_orders;

-- 6. Use the update command to change the name of the product for any row
UPDATE sales_orders
SET Ordered_item = 'New Product'
WHERE Order_Id = 1;

-- 7. Delete the sales_orders table from the database
DROP TABLE IF EXISTS sales_orders;
# ENTRI
