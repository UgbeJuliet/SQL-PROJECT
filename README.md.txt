# Advanced SQL Queries Project

## Project Overview

This project is designed to strengthen SQL skills through a series of advanced database queries based on a commercial business database. The exercise focuses on data retrieval, filtering, aggregation, joins, subqueries, conditional logic, and reporting techniques commonly used in real-world business environments.

The database simulates a commercial environment containing information about customers, products, suppliers, employees, orders, and product categories.

---

## Database Schema

The project uses the following relational schema:

### Categories

```sql
CATEGORIES (
    CATEGORY_CODE,
    CATEGORY_NAME,
    DESCRIPTION
)
```

### Customers

```sql
CUSTOMERS (
    CUSTOMER_CODE,
    COMPANY,
    ADDRESS,
    CITY,
    POSTAL_CODE,
    COUNTRY,
    PHONE,
    FAX
)
```

### Orders

```sql
ORDERS (
    ORDER_NUMBER,
    CUSTOMER_CODE,
    EMPLOYEE_NUMBER,
    ORDER_DATE,
    SHIP_DATE,
    SHIPPING_COST
)
```

### Order Details

```sql
ORDER_DETAILS (
    ORDER_NUMBER,
    PRODUCT_REF,
    UNIT_PRICE,
    QUANTITY,
    DISCOUNT
)
```

### Employees

```sql
EMPLOYEES (
    EMPLOYEE_NUMBER,
    REPORTS_TO,
    LAST_NAME,
    FIRST_NAME,
    POSITION,
    TITLE,
    BIRTH_DATE,
    HIRE_DATE,
    SALARY,
    COMMISSION
)
```

### Suppliers

```sql
SUPPLIERS (
    SUPPLIER_NUMBER,
    COMPANY,
    ADDRESS,
    CITY,
    POSTAL_CODE,
    COUNTRY,
    PHONE,
    FAX
)
```

### Products

```sql
PRODUCTS (
    PRODUCT_REF,
    PRODUCT_NAME,
    SUPPLIER_NUMBER,
    CATEGORY_CODE,
    QUANTITY,
    UNIT_PRICE,
    UNITS_IN_STOCK,
    UNITS_ON_ORDER,
    UNAVAILABLE
)
```

---

## Business Rules

* **COMPANY**: Name of customer or supplier company.
* **SHIPPING_COST**: Shipping charges for an order.
* **REPORTS_TO**: Manager or supervisor employee number.
* **QUANTITY**: Packaging type (bottles, cartons, boxes, etc.).
* **UNITS_IN_STOCK**: Quantity available in inventory.
* **UNITS_ON_ORDER**: Quantity currently ordered.
* **UNAVAILABLE**:

  * `0` = Product available
  * `-1` = Product unavailable

---

## Learning Objectives

By completing this project, you will gain practical experience with:

* SQL SELECT statements
* Filtering with WHERE clauses
* Aggregate functions
* GROUP BY and HAVING
* INNER JOIN and OUTER JOIN
* Nested Subqueries
* Correlated Subqueries
* Conditional Logic using CASE
* Date Functions
* Set Operations
* Relational Division Queries
* Business Reporting Queries

---

## Tasks Completed

### 1. Employee Analysis

Display male employees whose net salary (Salary + Commission) is greater than or equal to 8000.

**Required Output**

* Employee Number
* First Name
* Last Name
* Age
* Seniority

---

### 2. Product Filtering

Retrieve products that satisfy all of the following:

* Packaged in bottle(s)
* Third character of product name is T/t
* Supplied by suppliers 1, 2, or 3
* Unit price between 70 and 200
* Units on order is not NULL

**Required Output**

* Product Number
* Product Name
* Supplier Number
* Units Ordered
* Unit Price

---

### 3. Customer and Supplier Regional Matching

Find customers living in the same region as Supplier 1 based on:

* Country
* City
* Last three digits of postal code

**Constraint**

* Use only one subquery.

---

### 4. Discount Recalculation

For orders numbered between 10998 and 11003:

Calculate a new discount rate based on order value:

| Order Amount  | Discount |
| ------------- | -------- |
| 0 - 2000      | 0%       |
| 2001 - 10000  | 5%       |
| 10001 - 40000 | 10%      |
| 40001 - 80000 | 15%      |
| Above 80000   | 20%      |

Display:

* Order Number
* New Discount Rate
* Discount Application Note

Notes:

* Orders between 10000 and 10999 → "Apply Old Discount Rate"
* Otherwise → "Apply New Discount Rate"

---

### 5. Beverage Suppliers

Identify suppliers that provide beverage products.

**Required Output**

* Supplier Number
* Company
* Address
* Phone Number

---

### 6. Berlin Customers and Dessert Orders

Display customers from Berlin who have ordered at most one dessert product.

**Required Output**

* Customer Code

---

### 7. French Customers' Monday Orders

Display French customers and the total amount of orders placed every Monday during April 1998.

Include customers who have never placed an order.

**Required Output**

* Customer Number
* Company Name
* Phone Number
* Total Amount
* Country

---

### 8. Customers Who Ordered All Products

Find customers who have ordered every product available in the database.

**Required Output**

* Customer Code
* Company Name
* Telephone Number

---

### 9. Order Count for French Customers

Display the number of orders placed by each customer residing in France.

**Required Output**

* Customer Code
* Number of Orders

---

### 10. Yearly Order Comparison

Compare the number of orders placed in:

* 1996
* 1997

Calculate the difference between both years.

**Required Output**

* Orders in 1996
* Orders in 1997
* Difference

---

## Technologies Used

* SQL
* MySQL / PostgreSQL / SQL Server (depending on implementation)
* Relational Database Concepts

---

## How to Run

1. Execute the provided database script:

```sql
commercial.sql
```

2. Open your preferred SQL environment.

3. Run each query individually.

4. Verify the output against the required columns and business rules.

---

## Skills Demonstrated

* Advanced SQL Querying
* Data Analysis
* Business Intelligence Reporting
* Database Relationships
* Aggregation and Summarization
* Conditional Data Processing
* Complex Filtering
* Relational Database Design Understanding

## Author

Advanced SQL Practice Project developed as part of database querying and business reporting exercises.
