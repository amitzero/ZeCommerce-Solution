# Database Schema Planning

## Overview

The database schema will be designed to support all the functionalities of the ZeCommerce platform. It will include tables for users, products, orders, payments, and more. We will use **PostgreSQL** as the database due to its robustness, scalability, and support for complex queries.

## Tables

1. **Users**
   - id (Primary Key): Unique identifier for each user.
   - name: Full name of the user.
   - email: Email address of the user.
   - password: Hashed password for authentication.
   - address: Shipping address of the user.
   - phone_number: Contact number of the user.
   - created_at: Timestamp when the user was created.
   - updated_at: Timestamp when the user was last updated.

2. **Products**
   - id (Primary Key): Unique identifier for each product.
   - name: Name of the product.
   - description: Detailed description of the product.
   - price: Price of the product.
   - stock: Number of items available in stock.
   - category_id (Foreign Key): Identifier for the product category.
   - created_at: Timestamp when the product was created.
   - updated_at: Timestamp when the product was last updated.

3. **Orders**
   - id (Primary Key): Unique identifier for each order.
   - user_id (Foreign Key): Identifier for the user who placed the order.
   - total_amount: Total amount for the order.
   - status: Current status of the order (e.g., pending, shipped, delivered).
   - created_at: Timestamp when the order was created.
   - updated_at: Timestamp when the order was last updated.

4. **Order_Items**
   - id (Primary Key): Unique identifier for each order item.
   - order_id (Foreign Key): Identifier for the order.
   - product_id (Foreign Key): Identifier for the product.
   - quantity: Quantity of the product ordered.
   - price: Price of the product at the time of order.
   - created_at: Timestamp when the order item was created.
   - updated_at: Timestamp when the order item was last updated.

5. **Payments**
   - id (Primary Key): Unique identifier for each payment.
   - order_id (Foreign Key): Identifier for the order.
   - payment_method: Method of payment (e.g., credit card, PayPal).
   - amount: Amount paid.
   - status: Current status of the payment (e.g., pending, completed).
   - created_at: Timestamp when the payment was created.
   - updated_at: Timestamp when the payment was last updated.

6. **Categories**
   - id (Primary Key): Unique identifier for each category.
   - name: Name of the category.
   - created_at: Timestamp when the category was created.
   - updated_at: Timestamp when the category was last updated.

## Relationships

- A user can have multiple orders.
- An order can have multiple order items.
- A product can belong to multiple categories.
- A category can have multiple products.
