<div align="center">

# 🤖 OpenAI ChatGPT Clone — Real-Time Conversational Backend

<p align="center">
  <strong>Production-ready, real-time AI chatbot backend architecture mirroring ChatGPT with WebSocket bi-directional streaming, authenticated user sessions, and persistent conversation history.</strong>
</p>

<p align="center">
  <a href="#-overview">Overview</a> •
  <a href="#-key-features">Key Features</a> •
  <a href="#-tech-stack--architecture">Tech Stack</a> •
  <a href="#-project-structure">Project Structure</a> •
  <a href="#-getting-started">Getting Started</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Category-AI%20Chatbots%20%26%20Conversational%20Tools-059669?style=for-the-badge" alt="Category: AI Chatbots & Conversational Tools" />
  <img src="https://img.shields.io/badge/Tech%20Stack-Node.js%20%7C%20Express%20%7C%20MongoDB-10b981?style=for-the-badge" alt="Tech Stack: Node.js | Express | MongoDB" />
  <img src="https://img.shields.io/badge/Status-Production%20Ready-8b5cf6?style=for-the-badge" alt="Status: Production Ready" />
  <img src="https://img.shields.io/badge/License-MIT-f59e0b?style=for-the-badge" alt="License: MIT" />
</p>

</div>

---

## 📌 Overview

**OpenAI-ChatGPT-Clone-Node** is a robust backend microservice designed for conversational AI applications. Built with Express 5, Socket.IO, and MongoDB, it handles authenticated user registration, JWT session verification across both HTTP REST requests and WebSocket handshakes, and persistent storage of multi-turn AI chat dialogues.

---

## ✨ Key Features

- 💬 **Full-Duplex WebSockets**: Real-time streaming conversation channel powered by Socket.IO for low-latency AI responses.
- 🔐 **Dual-Layer JWT Security**: Authenticates standard HTTP endpoints as well as WebSocket connection handshakes with `jsonwebtoken`.
- 🗄️ **Persistent Chat Histories**: MongoDB collections linking user accounts to historical conversation threads and timestamps.
- ⚡ **Express 5 Foundation**: Utilizes the modern Express 5 framework with promise-based routing and centralized error handling.
- 🛡️ **Password Hashing**: Secure salted credential storage using `bcrypt` and `bcryptjs`.

---

## 🛠️ Tech Stack & Architecture

| Layer | Technologies |
|---|---|
| **Runtime & Server** | Node.js, Express.js 5 |
| **Real-Time Protocol** | Socket.IO (WebSockets with fallback) |
| **Database** | MongoDB, Mongoose ODM |
| **Security & Auth** | JSON Web Tokens (`jsonwebtoken`), `bcrypt` / `bcryptjs`, `cookie-parser` |
| **Environment** | `dotenv`, Nodemon |

---

## 📂 Project Structure

```text
OpenAI-ChatGPT-Clone-Node/
├── src/
│   ├── controllers/
│   │   ├── auth.controller.js     # User registration, login, and cookies
│   │   └── chat.controller.js     # Chat retrieval and thread management
│   ├── db/
│   │   └── db.js                  # Mongoose MongoDB connection
│   ├── middlewares/
│   │   └── auth.middleware.js     # Express JWT route guard
│   ├── models/
│   │   ├── chat.model.js          # Chat history schema
│   │   └── user.model.js          # User profile & credentials schema
│   ├── routes/
│   │   ├── auth.route.js          # /auth/register, /auth/login
│   │   └── chats.routes.js        # /chats endpoints
│   ├── sockets/
│   │   └── sockte.server.js       # Authenticated Socket.IO server logic
│   └── app.js                     # Express app configuration
├── server.js                      # HTTP & Socket.IO server bootstrap
├── package.json
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v18+)
- [MongoDB](https://www.mongodb.com/) running locally or Atlas connection string

### Installation & Run

1. **Install dependencies**:
   ```bash
   npm install
   ```

2. **Configure environment variables**:
   Create a `.env` file in the root directory:
   ```env
   PORT=3000
   MONGODB_URI=mongodb://localhost:27017/chatgpt-clone
   JWTSECRET=your_super_secret_jwt_key
   ```

3. **Start the development server**:
   ```bash
   npm run dev
   ```
   *The server starts listening on `http://localhost:3000` with WebSocket support enabled.*

---

## 👤 Author
- **Nikhil** ([GitHub](https://github.com/nikhilcodeworks))

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for more information.
