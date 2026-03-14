# FastAPI Assignment 4 – Cart System

## Assignment Objective

The objective of this assignment is to implement a **Cart System using FastAPI**.
The API allows users to add products to a cart, view the cart, remove items, and checkout to place orders.

---

## Implemented Features

### Q1 – Add Items to Cart

Used the endpoint **POST /cart/add** to add products to the cart.

Example:

* Wireless Mouse (quantity 2)
* Notebook (quantity 1)

Subtotal calculations were verified.

---

### Q2 – View Cart

Used the endpoint **GET /cart** to check the items present in the cart.

Verified:

* item_count
* grand_total

Manual calculation:
998 + 99 = 1097

---

### Q3 – Error Handling

Tested error cases:

* Adding **USB Hub (id=3)** → Out of stock → 400 error
* Adding **product_id=99** → Product not found → 404 error

---

### Q4 – Update Existing Cart Item

Added the **Wireless Mouse again**.

Instead of creating a duplicate item, the cart updated the quantity.

New quantity:
3

New subtotal:
1497

New grand total:
1596

---

### Q5 – Remove Item and Checkout

Steps performed:

1. Removed Notebook from cart using **DELETE /cart/{product_id}**
2. Verified cart contains only Wireless Mouse
3. Performed checkout using **POST /cart/checkout**
4. Verified order created in **GET /orders**
5. Confirmed cart becomes empty after checkout

---

### Q6 – Two Customer Flow

Simulated two customers placing orders.

Customer 1:

* Added Mouse and Pen Set
* Completed checkout

Customer 2:

* Added Notebook and Mouse
* Removed Notebook
* Completed checkout

Final result:
Total orders in **GET /orders = 3**

## Conclusion

Successfully implemented and tested a **FastAPI Cart System** including cart management, checkout process, error handling, and order tracking.
