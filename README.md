# Task_07
. Creating the Legacy Database (Before Normalization)

I created a database called LegacyDB.

Inside it, I made a single table legacy_customers which stored customer details, product details, and order information together.

I inserted some sample data (Alice bought Laptop & Mouse, Bob bought Mobile).

At this stage, there was data duplication (Alice’s email repeated twice).

2. Reviewing the Problems

Since all data was in one table:

Customer details repeated for multiple orders.

Product names and prices were repeated too.

This was a 1st Normal Form (1NF) violation because it lacked separation of entities.

3. Designing the New Normalized Database

I created a new database NewDB with proper normalization:

customers → stores unique customer names and emails.

products → stores unique product names and prices.

orders → connects customers to products with an order date (foreign keys used).

This structure satisfies 3rd Normal Form (3NF) because each table handles one type of entity and dependencies are clear.

4. Migrating the Data

I inserted unique customers into the customers table using a SELECT DISTINCT query.

I inserted unique products into the products table.

Finally, I populated the orders table by joining legacy_customers with the new tables so each order linked to the right customer and product.

5. Verifying Results

I selected data from all three new tables:

customers showed unique customers (Alice, Bob).

products showed unique products (Laptop, Mobile, Mouse).

orders showed orders with correct foreign key mapping.

Compared to the legacy table, the new schema removed duplication and improved clarity.
