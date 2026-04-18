# Zerodha Clone - Backend API

This is the backend service for the Zerodha Clone project. It is built using **Node.js** and **Express.js**, with **MongoDB** (via Mongoose) as the primary database.

## 🚀 Overview
The backend provides a RESTful API for managing stock portfolios, active positions, and user orders. It handles data validation through Mongoose schemas and ensures data persistence in MongoDB.

---

## 🛠️ Tech Stack
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB
- **ODM**: Mongoose
- **Middleware**: CORS, Body-Parser
- **Auth**: Passport.js (Local Strategy)
- **Dev Tools**: Nodemon

---

## 📂 Project Structure

```text
backend/
├── index.js           # Main entry point and API routes
├── model/             # Mongoose models (linking schemas to collections)
│   ├── HoldingsModel.js
│   ├── PositionsModel.js
│   └── OrdersModel.js
├── schemas/           # Data structure definitions
│   ├── HoldingsSchema.js
│   ├── PositionsSchema.js
│   └── OrdersSchema.js
└── .env               # Environment variables (DB URL, Port)
```

---

## ⚙️ Setup & Configuration

### 1. Prerequisites
- Node.js installed.
- Access to a MongoDB database (Atlas or Local).

### 2. Environment Variables
Create a `.env` file in the `backend/` directory with the following:
```env
MONGO_URL=your_mongodb_connection_string
PORT=3002
```

### 3. Running the Server
```bash
# Install dependencies
npm install

# Start in Production mode
npm start

# Start in Development mode (with auto-reload)
npm run dev
```
The server will be available at `http://localhost:3002`.

---

## 🛰️ API Endpoints

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/allHoldings` | Fetches all stocks in the user's permanent holdings. |
| `GET` | `/allPositions` | Fetches active trading positions. |
| `POST` | `/newOrder` | Adds a new buy/sell order to the historical log. |
| `GET` | `/addHoldings` | *(Dev only)* Seeds initial sample data for holdings. |
| `GET` | `/addPositions` | *(Dev only)* Seeds initial sample data for positions. |

---

## 💾 Data Models

### Holdings
- `name`: Stock symbol (e.g., "RELIANCE")
- `qty`: Number of shares
- `avg`: Average buy price
- `price`: Current market price
- `net`: Net change percentage
- `day`: Day change percentage

### Orders
- `name`: Stock symbol
- `qty`: Quantity traded
- `price`: Execution price
- `mode`: "BUY" or "SELL"

---

## 🔒 Security Note
Ensure that the `.env` file is never committed to version control to protect your MongoDB credentials. Use `cors` to restrict access from unauthorized origins if deploying to production.
