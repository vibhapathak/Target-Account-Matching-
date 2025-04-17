# 🚀 Target Account Matching API  
*A RESTful API for account-based targeting with match scores and status updates.*

## 📌 Overview

This project was made with the goal to build a REST API service that supports:

- 🔐 User login and token generation  
- 📊 Fetching company match scores  
- ✏️ Updating target statuses for accounts

---

## ⚙️ Features

- **User Authentication** via `/login`
- **Company Match Scores API** via `/accounts`
- **Target Status Update** for specific accounts via `/accounts/:id/status`
- JSON-based responses for seamless frontend integration

---

## 🛠️ Tech Stack

- **Node.js**
- **Express.js**
- **JWT** for authentication
- **Body-parser** for JSON parsing (if needed)
- **In-memory/static JSON data** (can be swapped with DB later)

---

## 🔐 API Endpoints

### 1. `POST /login`
Logs in a user and returns a token.

#### Request:
```json
{
  "username": "user1",
  "password": "pass123"
}
```

#### Response:
```json
{
  "message": "Login successful",
  "token": "xyz"
}
```

---

### 2. `GET /accounts`
Returns a list of companies along with their match scores.

#### Response:
```json
[
  {
    "id": 1,
    "companyName": "TechCorp",
    "matchScore": 86,
    "accountStatus": "Target"
  },
  ...
]
```

> 🛡️ Requires Bearer Token Authorization.

---

### 3. `POST /accounts/:id/status`
Updates the target status of a company.

#### Request:
```json
{
  "status": "Target"
}
```

#### Response:
```json
{
  "message": "Status updated successfully"
}
```

> 🛡️ Requires Bearer Token Authorization.

---

## ▶️ How to Run Locally

```bash
git clone https://github.com/your-username/target-account-matching-api.git
cd target-account-matching-api
npm install
cd server
run: node server.js
Open another Terminal
run: npm run dev
```

API will run on `http://localhost:3000/` by default.

---

## 🧪 Sample Users

```json
[
  { "username": "user1", "password": "pass123" },
  { "username": "admin", "password": "adminpass" }
]
```


## 📄 License

This project is licensed under the [MIT License](LICENSE).
