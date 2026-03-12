# FastAPI Assignment 3 – Day 4
The objective of this assignment was to practice **CRUD operations using FastAPI** and test the APIs using **Swagger UI**.

# Question 1 – Add New Products (POST)

Endpoint used:

POST /products

Two new products were added using the POST API.

Products added:

1. Laptop Stand  
   Price: 1299  
   Category: Electronics  

2. Sticky Notes  
   Price: 49  
   Category: Stationery  

The API automatically generated new product IDs and returned **201 Created**.

A duplicate product test was also performed to verify that the API correctly returns **400 Bad Request**.

---

# Question 2 – Update Product Details (PUT)

Endpoint used:

PUT /products/{product_id}

The product **USB Hub (ID: 3)** was updated.

Updates performed:

1. Stock status updated to `true`
2. Price updated from `799` to `699`
3. Both fields updated together using query parameters

Error handling was tested using:

PUT /products/99

which returned **404 Product not found**.

---

# Question 3 – Delete Product (DELETE)

Endpoint used:

DELETE /products/{product_id}

Product **Pen Set (ID: 4)** was deleted from the catalog.

Verification steps:

1. DELETE request successfully removed the product
2. GET /products confirmed the product was removed
3. Attempting to delete the same product again returned **404 Not Found**

---

# Question 4 – Full CRUD Lifecycle

A complete CRUD workflow was tested using a new product.

Steps performed:

1. Added product **Smart Watch**
2. Verified product using GET /products
3. Updated price using PUT
4. Verified update using GET /products/{id}
5. Deleted the product using DELETE
6. Confirmed removal using GET /products

This tested the full lifecycle of an API resource.

---

# Question 5 – Inventory Audit Endpoint

A new endpoint was created:

GET /products/audit

This endpoint returns an inventory summary including:

- Total number of products
- Number of products in stock
- Names of products that are out of stock
- Total stock value (price × 10 units)
- Most expensive product

This endpoint provides a quick overview of the store inventory.

# Tools Used

- Python
- FastAPI
- Swagger UI
- Uvicorn
