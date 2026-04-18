# Zerodha Clone - Frontend (Marketing Website)

This is the public-facing marketing website for the Zerodha Clone project. It is built using **React.js** and focuses on high-quality UI/UX to explain the platform's services and attract new users.

---

## 🚀 Overview
The frontend application serves as the landing portal. It includes various informational pages such as products overview, pricing details, and support documentation. It provides a professional image for the platform before a user logs in to the main trading dashboard.

---

## 🛠️ Tech Stack
- **Framework**: React.js (v18+)
- **Routing**: React Router DOM (v6+)
- **HTTP Client**: Axios (for newsletter/signup integrations)
- **Styling**: Standard CSS with a focus on matching Zerodha's clean design.

---

## 📂 Project Structure

```text
frontend/
├── public/            # Static assets (images, icons)
├── src/
│   ├── landing_page/  # All components for the marketing site
│   │   ├── home/      # Hero section, stats, ecosystem
│   │   ├── about/     # Team and company history
│   │   ├── pricing/   # Brokerage and charge details
│   │   ├── products/  # App descriptions (Kite, Console)
│   │   ├── signup/    # User registration area
│   │   ├── support/   # Help topics and ticket sections
│   │   ├── Navbar.js  # Main navigation (Sticky)
│   │   └── Footer.js  # Comprehensive site footer
│   ├── index.js       # App entry point and Route definitions
│   └── index.css      # Global styling rules
└── package.json       # Dependencies and scripts
```

---

## ⚙️ Setup & Running

### 1. Prerequisites
- Node.js installed.

### 2. Installation
```bash
# Navigate to the frontend directory
cd frontend

# Install dependencies
npm install
```

### 3. Start Development Server
```bash
# Start the app
npm start
```
The application will run on [http://localhost:3000](http://localhost:3000).

---

## 🗺️ Routing (Pages)

| Route | Page Component | Purpose |
| :--- | :--- | :--- |
| `/` | `HomePage` | Main landing page (Ecosystem focus). |
| `/about` | `AboutPage` | Information about Zerodha's philosophy. |
| `/product` | `ProductPage` | Details about Kite, Console, Coin, etc. |
| `/pricing` | `PricingPage` | Free equity delivery and flat ₹20 trades info. |
| `/support` | `SupportPage` | Help articles and search functionality. |
| `/signup` | `Signup` | Initial user onboarding portal. |
| `*` | `NotFound` | 404 Error page for invalid links. |

---

## ✨ Features
- **Responsive Layout**: Works seamlessly on desktop and mobile screens.
- **Sticky Navigation**: Easy access to the menu from any part of the page.
- **Brand Consistency**: Uses the same fonts, colors, and spacing as the official Zerodha website.
- **Modular Components**: Every page section (Hero, Stats, Team) is a separate React component for easy maintenance.

---

## 📝 Usage for Developers
- New sections should be added inside `src/landing_page/`.
- Styling for specific pages should ideally be kept in localized CSS files or handled through a central design system in `index.css`.
