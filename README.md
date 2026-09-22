# 🛒 Project 7 — E-commerce REST API Testing with Postman

![JavaScript](https://img.shields.io/badge/JavaScript-ES2022%2B-yellow)
![Postman](https://img.shields.io/badge/Postman-v10%2B-orange)
![REST API](https://img.shields.io/badge/API-REST-blue)
![Test Cases](https://img.shields.io/badge/Test%20Cases-48-green)
![Requests](https://img.shields.io/badge/API%20Requests-60-purple)
![E2E](https://img.shields.io/badge/E2E%20Workflows-4-red)

A comprehensive **Postman API testing project** created to demonstrate practical QA Automation skills through functional, negative, integration, and end-to-end testing of an e-commerce REST API.
> **Note:** This project is part of my personal QA Automation portfolio.

---

## 📑 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Collection Structure](#-collection-structure)
- [Test Coverage](#-test-coverage)
- [How to Run](#how-to-run-section)
- [Conclusion](#-conclusion)


---

## 📄 Overview

**ShiftLeft-REST-API** is a Postman-based API automation project focused on testing an e-commerce REST API.

The collection covers three core API services:

* 👤 **User Service**
* 🏷️ **Product Service**
* 🛒 **Order Service**

In addition, the project contains dedicated **End-to-End workflows** that combine multiple services and validate complete business scenarios.

---

## ✨ Features

* 🛠️ **Comprehensive API Validation** — Positive, negative, boundary, business-rule, response and JSON Schema validation.
* 🔢 **Dynamic Test Data Generation** — Unique test data generated at runtime using JavaScript and timestamps.
* 🔗 **Request Chaining & Variables** — Postman variables used to store and reuse dynamic IDs and data across requests and workflows.
* 📜 **Pre-request & Post-response Scripts** — JavaScript scripts used for test data generation, request setup, response validation and variable management.
* 🔄 **End-to-End Workflows** — Multi-step business scenarios combining User, Product and Order services.
* 🌐 **Environment-Based Configuration** — API configuration managed through Postman environment and collection variables.

---

## 🧰 Tech Stack

| Tool / Technology | Purpose |
|-------------------|---------|
| 🧪 **Postman v10+** | API testing and collection execution |
| 📜 **JavaScript ES2022+** | Test assertions and request scripting |
| 🔌 **REST API** | System under test |
| 📦 **JSON** | Request and response payloads |
| 📐 **JSON Schema** | Response structure and data validation |


---

## 📦 Collection Structure

The Postman collection is organized into service-level test suites and dedicated end-to-end workflows.

Each service is further divided by HTTP operation, while E2E scenarios contain multiple sequential steps that validate complete business workflows.

<details>
<summary>📂 Expand full collection structure</summary>

```text
🏗️ ShiftLeft-REST-API
│
└── tests
    │
    ├── 👤 User Service
    │   │
    │   ├── UserGetTests
    │   │   ├── Test case 1: Get all users
    │   │   ├── Test case 2: Get user with valid ID
    │   │   ├── Test case 3: Get user with non existing ID
    │   │   ├── Test case 4: Get user with invalid ID format
    │   │   ├── Test case 5: Search user by role
    │   │   └── Test case 6: Search users using multiple filter criteria
    │   │
    │   ├── UserPostTests
    │   │   ├── Test case 7: Create user with valid details
    │   │   ├── Test case 8: Create user with non existing role
    │   │   ├── Test case 9: Create user with invalid email format
    │   │   └── Test case 10: Create user with empty name
    │   │
    │   ├── UserUpdateTests
    │   │   ├── Test case 11: Update user with valid details
    │   │   ├── Test case 12: Update user with empty email
    │   │   └── Test case 13: Update user with name exceeding max length
    │   │
    │   └── UserDeleteTests
    │       ├── Test case 14: Delete user with valid ID
    │       ├── Test case 15: Delete user with non existing ID
    │       └── Test case 16: Delete user with invalid ID format
    │
    ├── 🏷️ Product Service
    │   │
    │   ├── ProductGetTests
    │   │   ├── Test case 17: Get all products
    │   │   ├── Test case 18: Get product with valid ID
    │   │   ├── Test case 19: Get product with non existing ID
    │   │   └── Test case 20: Sort products by price in descending order
    │   │
    │   ├── ProductPostTests
    │   │   ├── Test case 21: Create product with valid details
    │   │   ├── Test case 22: Create product with negative price
    │   │   ├── Test case 23: Create product with empty product name
    │   │   └── Test case 24: Create product with negative stock
    │   │
    │   ├── ProductUpdateTests
    │   │   ├── Test case 25: Update product with valid details
    │   │   ├── Test case 26: Update product with negative price
    │   │   ├── Test case 27: Update product with empty name
    │   │   └── Test case 28: Update product with negative stock
    │   │
    │   └── ProductDeleteTests
    │       ├── Test case 29: Delete product with valid ID
    │       ├── Test case 30: Delete product with non existing ID
    │       └── Test case 31: Delete user with invalid ID format
    │
    ├── 🛒 Order Service
    │   │
    │   ├── OrderGetTests
    │   │   ├── Test case 32: Get all orders
    │   │   ├── Test case 33: Get order with valid ID
    │   │   ├── Test case 34: Get order with non existing ID
    │   │   └── Test case 35: Get order with invalid ID format
    │   │
    │   ├── OrderPostTests
    │   │   ├── Test case 36: Create order with valid details
    │   │   ├── Test case 37: Create order with zero quantity
    │   │   └── Test case 38: Create order with non existing status
    │   │
    │   ├── OrderUpdateTests
    │   │   ├── Test case 39: Update order with valid details
    │   │   ├── Test case 40: Update order with non existing status
    │   │   └── Test case 41: Update order with zero quantity
    │   │
    │   └── OrderDeleteTests
    │       ├── Test case 42: Delete order with valid ID
    │       ├── Test case 43: Delete order with non existing ID
    │       └── Test case 44: Delete order with invalid ID format
    │
    └── 🔄 E2E Workflow
        │
        ├── Test case 45: Complete Order Creation Flow
        │   ├── Step 1: Create user with valid details
        │   ├── Step 2: Create product with valid details
        │   ├── Step 3: Create order linking existing user and product
        │   └── Step 4: Verify order creation
        │
        ├── Test case 46: Update User Name Flow
        │   ├── Step 1: Create user with valid details
        │   ├── Step 2: Update user name with valid data
        │   └── Step 3: Verify user update details
        │
        ├── Test case 47: Place Complete Order Before User Deletion Flow
        │   ├── Step 1: Create user with valid details
        │   ├── Step 2: Create product with valid details
        │   ├── Step 3: Create order linking existing user and product
        │   ├── Step 4: Delete user with placed order
        │   └── Step 5: Verify order after user deletion
        │
        └── Test case 48: Create Order for a Product that is out of Stock
            ├── Step 1: Create user with valid details
            ├── Step 2: Create product with stock zero
            └── Step 3: Create order for out-of-stock product
```

</details>

---


## 📊 Test Coverage

The test suite covers both **CRUD operations** and a broad range of functional validation scenarios, including **positive, negative, edge/boundary, response, and JSON Schema validation**.

| Area                    | Test Cases | API Requests | Testing Coverage |
| ----------------------- | ---------: | -----------: | ------------------------------------------------------------------------------ |
| 👤 **User Service**     | 16 | 16 | CRUD · Positive · Negative · Edge/Boundary · Response & Schema Validation |
| 🏷️ **Product Service**  | 15 | 15 | CRUD · Positive · Negative · Edge/Boundary · Response & Schema Validation |
| 🛒 **Order Service**    | 13 | 13 | CRUD · Positive · Negative · Edge/Boundary · Response & Schema Validation |
| 🔄 **E2E Workflows**    | 4  | 16 | End-to-End · Cross-service · Business Rules · Response Validation |
| **Total**               | **48** | **60** | **Functional · CRUD · Positive · Negative · Edge/Boundary · E2E · Schema Validation** |

---


<a name="how-to-run-section"></a>
## ▶️ How to Run

1. **Import Files**
   - Collection: `ShiftLeft-REST-API.postman_collection`
   - Environment: `QA env.postman_environment`

2. **Set Up**
   - Select `QA` environment in Postman.

3. **Execute**
   - Run requests or folders individually or via **Collection Runner**

---


## 🏁 Conclusion

The main focus of this project was to demonstrate my practical approach to REST API automation with Postman, 
combining maintainable API tests, backend validation, and end-to-end application workflows as part of my QA Automation portfolio.

