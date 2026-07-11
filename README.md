# 🛒 E-Commerce REST API

A professional RESTful E-Commerce API built with **Node.js**, **Express.js**, **MongoDB**, and **Mongoose**.

This project provides a complete backend for an e-commerce application, allowing clients to manage product categories, products, shopping carts, and orders through RESTful API endpoints.

The API follows a clean project structure, uses MongoDB for persistent storage, includes centralized error handling, request validation, and environment-based configuration.

---

# 🚀 Features

- RESTful API architecture
- Category Management (CRUD)
- Product Management (CRUD)
- Shopping Cart Management
- Order Management
- MongoDB database integration
- Mongoose ODM
- Environment variable configuration
- Centralized error handling
- Express middleware
- NoSQL Injection protection using express-mongo-sanitize

---

# 🛠 Tech Stack

- Node.js
- Express.js
- MongoDB
- Mongoose
- dotenv
- Nodemon
- Express Mongo Sanitize

---

# 📦 Prerequisites

Before running this project, make sure you have installed:

- Node.js (v18 or later recommended)
- npm
- MongoDB Community Server or MongoDB Atlas
- Git

---

# ⚙️ Installation

## 1. Clone the repository

```bash
git clone https://github.com/your-username/ecommerce-api.git
```

## 2. Navigate to the project

```bash
cd ecommerce-api
```

## 3. Install dependencies

```bash
npm install
```

## 4. Configure environment variables

Create a `.env` file in the project root.

Example:

```env
PORT=3000
NODE_ENV=development
MONGO_URI=mongodb://127.0.0.1:27017/ecommerce-api
```

You can also copy the example file:

```bash
cp .env.example .env
```

Then update the values as needed.

---

## 5. Seed the database

Run the seed script:

```bash
npm run seed
```

---

## 6. Start the development server

```bash
npm run dev
```

The API will be available at:

```
http://localhost:3000
```

---

# 🔐 Environment Variables

| Variable | Description | Example |
|-----------|-------------|----------|
| PORT | Port number used by the Express server | 3000 |
| NODE_ENV | Current application environment | development |
| MONGO_URI | MongoDB connection string | mongodb://127.0.0.1:27017/ecommerce-api |

---

# 📚 API Endpoints

## Categories

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | /api/categories | Get all categories |
| GET | /api/categories/:id | Get category by ID |
| POST | /api/categories | Create a category |
| PATCH | /api/categories/:id | Update a category |
| DELETE | /api/categories/:id | Delete a category |

---

## Products

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | /api/products | Get all products |
| GET | /api/products/:id | Get product by ID |
| POST | /api/products | Create a product |
| PATCH | /api/products/:id | Update a product |
| DELETE | /api/products/:id | Delete a product |

---

## Shopping Cart

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | /api/cart | Get current cart |
| DELETE | /api/cart | Clear cart |
| POST | /api/cart/items | Add item to cart |
| PATCH | /api/cart/items/:productId | Update cart item quantity |
| DELETE | /api/cart/items/:productId | Remove item from cart |

---

## Orders

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | /api/orders | Get all orders |
| GET | /api/orders/:id | Get order by ID |
| POST | /api/orders | Create a new order |
| PATCH | /api/orders/:id/status | Update order status |

---

# 📁 Project Structure

```
ecommerce-api/
│
├── config/
│   └── Application configuration
│
├── controllers/
│   └── Business logic for each API
│
├── db/
│   └── MongoDB connection
│
├── middleware/
│   └── Custom middleware and error handler
│
├── models/
│   └── Mongoose schemas and models
│
├── routes/
│   └── Express route definitions
│
├── utils/
│   └── Utility classes and helper functions
│
├── app.js
├── seed.js
├── package.json
├── .env.example
└── README.md
```

---

# 📂 Folder Description

| Folder | Purpose |
|----------|---------|
| config | Stores application configuration values |
| controllers | Contains the business logic for each endpoint |
| db | Handles MongoDB database connection |
| middleware | Contains custom middleware and global error handling |
| models | Defines MongoDB schemas using Mongoose |
| routes | Defines all Express API routes |
| utils | Helper classes and reusable utilities |

---

# ▶️ Available Scripts

Install dependencies

```bash
npm install
```

Run development server

```bash
npm run dev
```

Run production server

```bash
npm start
```

Seed database

```bash
npm run seed
```

---

# 🧪 Testing

All endpoints can be tested using:

- Postman
- Thunder Client
- Insomnia

---

# 📌 Built With

- Node.js
- Express.js
- MongoDB
- Mongoose

---

# 👩‍💻 Author

Developed as part of the DECI Web Development Program.

---

# 📄 License

This project is created for educational purposes.
