# Zerodha Clone - Trading Dashboard

The **Dashboard** is the core functional module of the Zerodha Clone project. It provides an interactive interface for users to track stocks, manage their portfolio, and execute trades in real-time.

---

## 🚀 Overview
Unlike the static marketing frontend, the Dashboard is a dynamic Single Page Application (SPA) that actively communicates with the Backend API to provide live feedback on investments and market trends.

---

## 🛠️ Tech Stack
- **Framework**: React.js (v18+)
- **UI Library**: Material UI (MUI) for icons, tooltips, and layouts.
- **Charts**: `Chart.js` via `react-chartjs-2` for portfolio and stock visualization.
- **State Management**: React Context API (`GeneralContext`).
- **HTTP Client**: Axios (for Backend API calls).

---

## 📂 Project Structure

```text
dashboard/
├── public/              # Static assets
├── src/
│   ├── components/      # UI Modules
│   │   ├── WatchList.js      # Left-side stock tracker
│   │   ├── Holdings.js       # Permanent stock portfolio
│   │   ├── Positions.js      # Active intra-day trades
│   │   ├── Orders.js         # Transaction history
│   │   ├── Summary.js        # Main portfolio overview
│   │   ├── BuyActionWindow.js # Order placement modal
│   │   └── GeneralContext.js # Global state & modal management
│   ├── data/            # Local mock data for testing
│   ├── index.js         # Application entry
│   └── index.css        # Dashboard-specific styles
└── package.json         # Dependencies
```

---

## 🔄 Workflow: Frontend & Backend Interaction

The Dashboard acts as the bridge between the user and the MongoDB database. Here is how the data flows:

### 1. Data Loading (Read)
When a user opens the **Holdings** or **Positions** tabs:
- The component uses `useEffect` to trigger an **Axios GET** request to the Backend.
- `GET http://localhost:3002/allHoldings` or `allPositions`.
- The Backend fetches data from MongoDB and sends it back as JSON.
- React updates the state and renders the tables and charts (`Holdings.js` -> `VerticalGraph.js`).

### 2. Order Execution (Write)
When a user wants to buy a stock:
1.  **WatchList**: User hovers over a stock in the sidebar and clicks the **"Buy"** button.
2.  **Context**: `GeneralContext` triggers the `openBuyWindow` function, passing the stock's UID.
3.  **UI**: The `BuyActionWindow` popup appears on the screen.
4.  **API Call**: When the user clicks "Buy" in the modal, an **Axios POST** request is sent.
    - `POST http://localhost:3002/newOrder` with payload `{ name, qty, price, mode: "BUY" }`.
5.  **Database**: The Backend saves this order into the `orders` collection in MongoDB.

### 3. Real-time Visualization
- **Doughnut Charts**: Used in `WatchList` to show the price distribution of tracked stocks.
- **Vertical Bars**: Used in `Holdings` to show individual stock performance vs. investment value.

---

## ⚙️ Setup & Running

### 1. Installation
```bash
cd dashboard
npm install
```

### 2. Start Project
```bash
npm start
```
*Note: If the landing page (frontend) is already running on port 3000, React will ask to run the Dashboard on port 3001. Type 'Y' to confirm.*

---

## ✨ Features
- **Dynamic Watchlist**: Hover effects with quick-action buttons (Buy, Sell, Analytics).
- **Comprehensive Summary**: High-level view of account balance and total P&L.
- **Material UI Integration**: Professional tooltips, smooth transitions, and premium icons.
- **Responsive Tables**: Clean alignment of financial data (Qty, Avg Cost, LTP, P&L).
