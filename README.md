# Zerodha Clone - Full Stack Project

A high-fidelity clone of the Zerodha trading platform built using the **MERN Stack** (MongoDB, Express, React, Node.js). This project consists of three main modules: a marketing landing page, a functional trading dashboard, and a robust backend API.

## 🚀 Project Overview

The project is architected into three independent sub-applications:

1.  **Frontend (Landing Page)**: A professional marketing website showcasing Zerodha's products, pricing, and services.
2.  **Dashboard (Trading App)**: A feature-rich user interface for managing portfolios, watching stocks, and placing orders.
3.  **Backend (API)**: A Node.js and Express server that handles data persistence and business logic using MongoDB.

---

## 🛠️ Technology Stack

-   **Frontend & Dashboard**: React.js, React Router, Axios, Chart.js, Material UI.
-   **Backend**: Node.js, Express.js.
-   **Database**: MongoDB via Mongoose.
-   **Authentication**: Passport.js (Local Strategy).

---

## 📂 Directory Structure

```text
ZERODHA PROJECT/
├── backend/        # Node.js API server
├── frontend/       # React app for landing pages
└── dashboard/      # React app for the trading dashboard
```

---

## ⚙️ Installation & Setup

### Prerequisites
- Node.js installed on your system.
- MongoDB Atlas account or local MongoDB instance.

### 1. Backend Setup
1. Navigate to the `backend` folder.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the `backend` directory and add your MongoDB connection string:
   ```env
   MONGO_URL=your_mongodb_connection_string
   PORT=3002
   ```
4. Start the server:
   ```bash
   npm start
   ```
   *The backend will run on [http://localhost:3002](http://localhost:3002)*

### 2. Frontend Setup (Landing Page)
1. Navigate to the `frontend` folder.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the app:
   ```bash
   npm start
   ```
   *The frontend will run on [http://localhost:3000](http://localhost:3000)*

### 3. Dashboard Setup (Trading UI)
1. Navigate to the `dashboard` folder.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the app:
   ```bash
   npm start
   ```
   *The dashboard will run on [http://localhost:3001](http://localhost:3001)* (React will automatically prompt to use another port if 3000 is occupied).

### 4. Data Seeding (Optional)
If your database is empty, you can seed it with initial sample holdings and positions:
1. In `backend/index.js`, uncomment the routes for `/addHoldings` and `/addPositions`.
2. Visit `http://localhost:3002/addHoldings` and `http://localhost:3002/addPositions` in your browser.
3. Once the data is added, comment the routes back for security.

---

## ✨ Key Features

-   **Interactive Dashboard**: Real-time feel with Watchlists and stock performance charts.
-   **Portfolio Management**: Track `Holdings` (long-term) and `Positions` (short-term).
-   **Order System**: Buy/Sell stocks with a functional order recording system.
-   **Data Visualization**: Integrated `Chart.js` for representing stock price trends.
-   **Responsive Design**: Clean and professional UI mirroring the actual Zerodha platform.

---

## 📝 API Endpoints

-   `GET /allHoldings`: Fetch all current holdings.
-   `GET /allPositions`: Fetch active trading positions.
-   `POST /newOrder`: Place and record a new stock order.

---

## 🤝 Contributing
Feel free to fork this project and contribute by adding more features like real-time WebSocket integration or advanced technical indicators!
