# ⚡ QuickCom – Local Quick Commerce Platform

QuickCom is a **full-stack quick commerce application** built with **React + Vite (TypeScript)** on the frontend, **Node.js + Express** on the backend, and **PostgreSQL** as the database.

The database runs locally using **Docker**, while the client and server run normally using **npm**. The application also uses **WebSockets (Socket.IO)** for real-time order and delivery updates.

---

## 🧱 Tech Stack

### Frontend

- React + TypeScript
- Vite
- shadcn/ui + Tailwind CSS
- React Router
- TanStack Query

### Backend

- Node.js
- Express
- Prisma ORM
- PostgreSQL
- Socket.IO (WebSockets)

### Infrastructure

- Docker (PostgreSQL only)
- Nginx (for production deployment)

---

## 📁 Project Structure

```txt
quick/
 ├─ client/        # React (Vite) frontend
 ├─ server/        # Node.js + Express backend
 ├─ prisma/        # Prisma schema & migrations
 ├─ docker-compose.yml
 ├─ .env
 └─ README.md
```

---

## ⚙️ Prerequisites

Make sure you have the following installed:

- Node.js (v18 or higher recommended)
- npm
- Docker & Docker Compose

Check versions:

```bash
node -v
npm -v
docker -v
docker compose version
```

---

## 🐘 Database Setup (PostgreSQL with Docker)

### 1️⃣ Start the database

From the project root:

```bash
docker compose up -d
```

This will:

- Pull `postgres:15-alpine`
- Start the database on port **5433**

Verify:

```bash
docker ps
```

---

### 2️⃣ Environment Variables

Create a `.env` file in the **server directory** (or project root if shared):

```env
DATABASE_URL="postgresql://postgres:postgres@localhost:5433/delivery_db"
```

---

### 3️⃣ Run Prisma Migrations

From the **server** directory:

```bash
npx prisma migrate dev
```

(Optional) Open Prisma Studio:

```bash
npx prisma studio
```

---

## 🖥️ Backend Setup

From the **server** directory:

```bash
npm install
npm run dev
```

Backend runs on:

```
http://localhost:3000
```

WebSocket server runs on the **same backend instance**.

---

## 🌐 Frontend Setup

From the **client** directory:

```bash
npm install
npm run dev
```

Frontend runs on:

```
http://localhost:5173
```

---

## 🔐 Demo Login Credentials

Use the following credentials to test the application:

### 👤 Customer

```
Email:    customer@gmail.com
Password: customer
```

### 🚴 Delivery Partner

```
Email:    delivery@gmail.com
Password: delivery
```

---

## 👥 User Roles

- **Customer** – Browse products, place orders, track status
- **Delivery Partner** – Accept and deliver orders

---

## 🔌 Real-Time Features (WebSockets)

- Live order status updates
- Delivery status tracking
- Customer ↔ Delivery Partner notifications
- City-based event rooms

---

## 📦 Core Features

- Product browsing & cart
- Order placement & cancellation
- Real-time order tracking
- Delivery partner dashboard
- Role-based access control

---

## 🛠 Common Commands

```bash
# Start database
docker compose up -d

# Stop database
docker compose down

# Backend
npm run dev

# Frontend
npm run dev

# Prisma
npx prisma migrate dev
npx prisma studio
```

---

## 📄 License

MIT License
