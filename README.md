# 💸 Digital Wallet System - Backend API

A backend-only RESTful API for a secure digital wallet system, enabling users to fund accounts, pay other users, purchase products, and check transaction history. Built with **Node.js**, **Express.js**, and **PostgreSQL**, with secure authentication and real-time currency conversion.

---

## 🚀 Features

* 🔐 **User Registration & Basic Authentication**
* 💰 **Wallet Funding & Peer Payments**
* 📜 **Transaction History Tracking**
* 🌍 **Currency Conversion via [CurrencyAPI](https://currencyapi.com)**
* 🛍️ **Product Catalog & Purchase Workflow**
* 🧱 **Structured PostgreSQL Database**
* ✅ **Modular MVC Architecture & Middleware**

---

## 📦 Tech Stack

* **Node.js**
* **Express.js**
* **PostgreSQL**
* **bcrypt** (password hashing)
* **dotenv** (environment variables)
* **axios / fetch** (external API requests)

---

## 📁 Project Structure

```
wallet-system/
🔹 controllers/
🔹 routes/
🔹 models/
🔹 middleware/
🔹 utils/
🔹 db/connection.js
🔹 app.js
🔹 server.js
🔹 .env
```

---

## ⚙️ Installation

```bash
git clone https://github.com/<your-username>/digital-wallet-system.git
cd digital-wallet-system
npm install
```

---

## ⚖️ Environment Variables

Create a `.env` file in the root directory and add:

```env
PORT=3000
DATABASE_URL=your_postgres_connection_string
CURRENCY_API_KEY=your_currencyapi_key
```

---

## 🔐 Authentication

All protected routes require **Basic Authentication**:

```
Authorization: Basic <base64(username:password)>
```

Passwords are securely stored using `bcrypt`.

---

## 🧪 API Endpoints

### 🔹 User Registration

`POST /register`

```json
{
  "username": "ashu",
  "password": "hunter2"
}
```

---

### 🔹 Fund Wallet

`POST /fund` *(Auth Required)*

```json
{
  "amt": 10000
}
```

---

### 🔹 Pay Another User

`POST /pay` *(Auth Required)*

```json
{
  "to": "priya",
  "amt": 100
}
```

---

### 🔹 Check Balance (with optional currency)

`GET /bal?currency=USD` *(Auth Required)*

---

### 🔹 View Transaction History

`GET /stmt` *(Auth Required)*

---

### 🔹 Add Product

`POST /product` *(Auth Required)*

```json
{
  "name": "Wireless Mouse",
  "price": 599,
  "description": "2.4 GHz wireless mouse"
}
```

---

### 🔹 List All Products

`GET /product` *(Public)*

---

### 🔹 Buy a Product

`POST /buy` *(Auth Required)*

```json
{
  "product_id": 1
}
```

---

## 🗃️ Database Schema

* `users`: id, username, password, balance
* `transactions`: id, user\_id, kind, amt, updated\_bal, timestamp
* `products`: id, name, price, description
* `purchases`: id, user\_id, product\_id, timestamp

---

## 🧹 TODOs & Future Improvements

* ✅ Unit Tests with Jest/Supertest
* ✅ Role-based access for product creation
* 🔄 Paginated transaction history
* 📛 Rate limiting & brute-force protection

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🤝 Contributions

Pull requests and stars are always welcome!
If you'd like to contribute, please fork the repo and submit a PR.

---

## 🤛 Author

**Upendra Singh**
[GitHub](https://github.com/iupendra982)
