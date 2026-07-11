# 🛒 E-Commerce REST API

> A scalable, modular, and RESTful backend API for managing products, categories, shopping carts, and orders using **Node.js**, **Express.js**, **MongoDB**, and **Mongoose**.

![Node.js](https://img.shields.io/badge/Node.js-20.x-339933?logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-Backend-000000?logo=express)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-47A248?logo=mongodb&logoColor=white)
![Mongoose](https://img.shields.io/badge/Mongoose-ODM-880000)
![License](https://img.shields.io/badge/License-Educational-blue)

---

# 📑 Table of Contents

- [Project Overview](#-project-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Architecture](#-project-architecture)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Environment Variables](#-environment-variables)
- [API Endpoints](#-api-endpoints)
- [Example Request & Response](#-example-request--response)
- [HTTP Status Codes](#-http-status-codes)
- [Project Structure](#-project-structure)
- [Folder Description](#-folder-description)
- [Available Scripts](#-available-scripts)
- [Security Features](#-security-features)
- [Testing](#-testing)
- [Future Improvements](#-future-improvements)
- [Author](#-author)
- [License](#-license)

---

# 📖 Project Overview

This project is a professional RESTful E-Commerce API that provides the backend functionality required for an online shopping application.

The API allows clients to:

- Manage product categories
- Manage products
- Create and manage shopping carts
- Create and manage customer orders

The application follows RESTful API best practices, uses MongoDB for persistent data storage, and follows a clean modular architecture that separates routing, business logic, database models, and middleware.

---

# ✨ Features

- RESTful API Architecture
- Complete CRUD Operations
- Category Management
- Product Management
- Shopping Cart Management
- Order Management
- MongoDB Database Integration
- Mongoose ODM
- Environment Variable Configuration
- Global Error Handling
- Modular Project Structure
- Express Middleware
- MongoDB Sanitization
- Clean and Maintainable Code

---

# 🛠 Tech Stack

| Technology | Purpose |
|------------|---------|
| Node.js | JavaScript Runtime |
| Express.js | Web Framework |
| MongoDB | NoSQL Database |
| Mongoose | MongoDB ODM |
| dotenv | Environment Variables |
| Nodemon | Development Server |
| express-mongo-sanitize | Security Middleware |

---

# 🏗 Project Architecture

The project follows a layered architecture to keep responsibilities separated.

```text
                Client
                   │
                   ▼
              Express Routes
                   │
                   ▼
              Controllers
                   │
                   ▼
               Mongoose Models
                   │
                   ▼
                MongoDB
```

### Layer Responsibilities

- **Routes** receive HTTP requests.
- **Controllers** contain business logic.
- **Models** define MongoDB schemas.
- **Database** manages persistent storage.
- **Middleware** handles validation, sanitization, and error handling.
- **Utilities** contain reusable helper functions.

This architecture improves scalability, readability, and maintainability.

---

# 📦 Prerequisites

Before running this project, make sure you have installed:

- Node.js (v18 or later)
- npm
- MongoDB Community Server or MongoDB Atlas
- Git

---

# ⚙ Installation

## 1. Clone the Repository

```bash
git clone 
```

---

## 2. Navigate to the Project Folder

```bash
cd ecommerce-api
```

---

## 3. Install Dependencies

```bash
npm install
```

---

## 4. Configure Environment Variables

Create a `.env` file in the project root.

Example:

```env
PORT=3000
NODE_ENV=development
MONGO_URI=mongodb://127.0.0.1:27017/ecommerce-api
```

---

## 5. Seed the Database

Run:

```bash
npm run seed
```

This will populate MongoDB with sample data.

---

## 6. Start the Development Server

```bash
npm run dev
```

The server will start on:

```
http://localhost:5000
```

---

# 🔐 Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| PORT | Express server port | 3000 |
| NODE_ENV | Application environment | development |
| MONGO_URI | MongoDB connection string | mongodb://127.0.0.1:27017/ecommerce-api |

---

# 📚 API Endpoints

## 📁 Categories

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | `/api/categories` | Retrieve all categories |
| GET | `/api/categories/:id` | Retrieve a category by ID |
| POST | `/api/categories` | Create a new category |
| PATCH | `/api/categories/:id` | Update an existing category |
| DELETE | `/api/categories/:id` | Delete a category |

---

## 📦 Products

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | `/api/products` | Retrieve all products |
| GET | `/api/products/:id` | Retrieve a product by ID |
| POST | `/api/products` | Create a new product |
| PATCH | `/api/products/:id` | Update a product |
| DELETE | `/api/products/:id` | Delete a product |

---

## 🛒 Shopping Cart

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | `/api/cart` | Retrieve the shopping cart |
| DELETE | `/api/cart` | Clear the shopping cart |
| POST | `/api/cart/items` | Add an item to the cart |
| PATCH | `/api/cart/items/:productId` | Update item quantity |
| DELETE | `/api/cart/items/:productId` | Remove an item from the cart |

---

## 📋 Orders

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | `/api/orders` | Retrieve all orders |
| GET | `/api/orders/:id` | Retrieve an order by ID |
| POST | `/api/orders` | Create a new order |
| PATCH | `/api/orders/:id/status` | Update order status |
| DELETE | `/api/orders` | Cancel all orders at once |
| DELETE | `/api/orders/:id` | Remove an order |


---

# 📨 Example Request & Response

## Create Product

### Request

**POST** `/api/products`

```json
{
  "name": "Wireless Mouse",
  "price": 29.99,
  "category": "Electronics"
}
```

### Successful Response

```json
{
  "success": true,
  "message": "Product created successfully.",
  "data": {
    "_id": "665adf4d4e32b8b7ef8d1234",
    "name": "Wireless Mouse",
    "price": 29.99,
    "category": "Electronics"
  }
}
```

---

# 🚦 HTTP Status Codes

| Status Code | Meaning |
|-------------|---------|
| 200 | Request completed successfully |
| 201 | Resource created successfully |
| 400 | Bad request |
| 404 | Resource not found |
| 500 | Internal server error |

---

# 📁 Project Structure

```text
ecommerce-api/
│
├── config/
│   └── Application configuration
│
├── controllers/
│   ├── categoryController.js
│   ├── productController.js
│   ├── cartController.js
│   └── orderController.js
│
├── db/
│   └── MongoDB connection
│
├── middleware/
│   ├── errorHandler.js
│   └── validateRequest.js
│
├── models/
│   ├── Category.js
│   ├── Product.js
│   ├── Cart.js
│   └── Order.js
│
├── routes/
│   ├── categoryRoutes.js
│   ├── productRoutes.js
│   ├── cartRoutes.js
│   └── orderRoutes.js
│
├── utils/
│   └── Helper functions
│
├── seed.js
├── app.js
├── package.json
├── .env.example
└── README.md
```

---

# 📂 Folder Description

| Folder | Description |
|---------|-------------|
| config | Stores application configuration |
| controllers | Contains the business logic |
| db | MongoDB connection setup |
| middleware | Custom middleware and global error handling |
| models | Mongoose schemas and models |
| routes | Express API routes |
| utils | Helper functions and utilities |

---

# ▶ Available Scripts

Install dependencies

```bash
npm install
```

Run the development server

```bash
npm run dev
```

Run the production server

```bash
npm start
```

Seed the database

```bash
npm run seed
```

---

# 🔒 Security Features

This project includes several security and best-practice features:

- MongoDB NoSQL Injection Protection using `express-mongo-sanitize`
- Environment Variables using `dotenv`
- Global Error Handling Middleware
- Mongoose Schema Validation
- Clean RESTful API Design
- Separation of Concerns
- Modular Code Organization

---

# 🧪 Testing

The API can be tested using:

- Postman
- Thunder Client
- Insomnia

Each endpoint returns meaningful HTTP status codes and JSON responses.

---

# 🚀 Future Improvements

Potential future enhancements include:

- JWT Authentication
- User Accounts
- Admin Dashboard
- Product Reviews
- Wishlist
- Image Uploads
- Payment Gateway Integration
- API Documentation using Swagger/OpenAPI
- Unit and Integration Testing
- Docker Support

---

# 💡 Design Principles

The project follows modern backend development principles:

- RESTful API Design
- Modular Architecture
- Separation of Concerns
- Reusable Middleware
- Persistent Database Storage
- Environment-Based Configuration
- Maintainable and Scalable Codebase

---

# 👩‍💻 Author

**Haneen Ali**

Developed as part of the **Digital Egypt Cubs Initiative (DECI)** Web Development Program.

This project demonstrates backend development skills using modern JavaScript technologies and follows industry best practices for building scalable REST APIs.

---

# 📄 License

This project was developed for educational purposes as part of the DECI Web Development curriculum.

---

⭐ **Thank you for reviewing this project!**
