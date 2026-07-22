<div align="center">

# 🛍️ Ecommerce API

### A RESTful backend for managing an online store — categories, products, carts, and orders.

<p>
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express.js" />
  <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB" />
  <img src="https://img.shields.io/badge/Mongoose-880000?style=for-the-badge&logo=mongoose&logoColor=white" alt="Mongoose" />
</p>

</div>

---

## Table of Contents

- About
- Features
- Prerequisites
- Installation
- Environment Variables
- API Endpoints
- Project Structure

## 📖 About

**Ecommerce API** is a RESTful backend service built to power an online store. It handles everything from browsing product categories to managing a shopping cart and placing orders — with clean, predictable endpoints and centralized error handling.

This project includes the following REST APIs:

- Categories API
- Products API
- Shopping Cart API
- Orders API

### Tech Stack

- Node.js
- Express.js
- MongoDB
- Mongoose

**Technology Details:**

| Layer | Technology |
|---|---|
| Runtime | Node.js |
| Framework | Express.js |
| Database | MongoDB |
| ODM | Mongoose |

---

## ✨ Features

- 🗂️ **Categories API** — create, read, update, and delete product categories
- 📦 **Products API** — full CRUD for products, linked to categories
- 🛒 **Cart API** — add, update, remove items, view, and clear the cart
- 🧾 **Orders API** — checkout from cart, track order status, view and manage orders
- 🛡️ Centralized error handling with consistent error responses
- 🧼 Input sanitization against NoSQL injection (`express-mongo-sanitize`)
- 🌱 Database seeding script for quick local setup

---

## ✅ Prerequisites

Make sure you have the following installed before you begin:

| Requirement | Notes |
|---|---|
| **Node.js** | v18 or higher recommended |
| **MongoDB** | Local instance, or a free [MongoDB Atlas](https://www.mongodb.com/atlas) cluster |
| **npm** | Comes bundled with Node.js |

---

## 🚀 Installation

Follow these steps in order to get the project running locally.

**1. Clone the repository**

```bash
git clone https://github.com/7aneen3li/Ecommerce-API.git
cd Ecommerce-API
```

**2. Install dependencies**

```bash
npm install
```

**3. Set up environment variables**

Copy the example file and fill in your own values:

```bash
cp .env.example .env
```

See the [Environment Variables](#-environment-variables) section below for what each variable means.

**4. Seed the database** *(optional but recommended)*

```bash
npm run seed
```

**5. Run the development server**

```bash
npm run dev
```

The API will be live at: http://localhost:5000
> Other available scripts: `npm start` (runs the server without auto-reload).

---

## 🔐 Environment Variables

Create a `.env` file in the project root with the following variables:

| Variable | Description | Example |
|---|---|---|
| `PORT` | The port the server listens on | `5000` |
| `NODE_ENV` | The environment the app is running in | `development` |
| `MONGO_URI` | Your MongoDB connection string (local or Atlas) | `mongodb://127.0.0.1:27017/ecommerce-api` |

---

## 📡 API Endpoints

All endpoints are prefixed with `/api`.

### 🗂️ Categories — `/api/categories`

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/categories` | Get all categories |
| `POST` | `/api/categories` | Create a new category |
| `GET` | `/api/categories/:id` | Get a single category by ID |
| `PATCH` | `/api/categories/:id` | Update a category by ID |
| `DELETE` | `/api/categories/:id` | Delete a category by ID |

### 📦 Products — `/api/products`

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/products` | Get all products |
| `POST` | `/api/products` | Create a new product |
| `GET` | `/api/products/:id` | Get a single product by ID |
| `PATCH` | `/api/products/:id` | Update a product by ID |
| `DELETE` | `/api/products/:id` | Delete a product by ID |

### 🛒 Cart — `/api/cart`

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/cart` | Get the current cart |
| `DELETE` | `/api/cart` | Clear the entire cart |
| `POST` | `/api/cart/items` | Add an item to the cart |
| `PATCH` | `/api/cart/items/:productId` | Update the quantity of an item in the cart |
| `DELETE` | `/api/cart/items/:productId` | Remove an item from the cart |

### 🧾 Orders — `/api/orders`

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/orders` | Get all orders |
| `POST` | `/api/orders` | Create a new order (checkout from cart) |
| `DELETE` | `/api/orders` | Delete all orders |
| `GET` | `/api/orders/:id` | Get a single order by ID |
| `DELETE` | `/api/orders/:id` | Delete a single order by ID |
| `PATCH` | `/api/orders/:id/status` | Update the status of an order |

---

## 🗄️ Project Structure

```text
ECOMMERCE-API/
├── config/
│ └── app.config.js # App-wide configuration (port, env, etc.)
├── controllers/ # Request handlers — business logic for each resource
│ ├── cart.controller.js
│ ├── category.controller.js
│ ├── order.controller.js
│ └── product.controller.js
├── db/
│ └── connectDB.js # MongoDB connection setup
├── middleware/
│ └── errorHandler.js # Centralized error-handling middleware
├── models/ # Mongoose schemas
│ ├── cart.model.js
│ ├── category.model.js
│ ├── order.model.js
│ └── product.model.js
├── postman/ # Postman collection & environment for API testing
│ ├── E-Commerce API.postman_collection.json
│ └── E-Commerce API Dev.postman_environment.json
├── routes/ # Route definitions, mapped to controllers
│ ├── cart.routes.js
│ ├── category.routes.js
│ ├── order.routes.js
│ └── product.routes.js
├── utils/
│ ├── AppError.js # Custom error class
│ └── asyncHandler.js # Wrapper to catch async errors
├── .env.example # Template for required environment variables
├── app.js # Application entry point
├── seed.js # Database seeding script
└── package.json
```

---

<div align="center">

Built as a graduation project — the first entry in a growing portfolio. 🎓

</div>
