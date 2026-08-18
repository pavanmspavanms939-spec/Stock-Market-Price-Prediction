# 📈 StockPulse — AI-Powered Market Intelligence & Paper Trading

**StockPulse** is a Flask-based web application designed to provide stock-market information, portfolio management, and risk-free paper trading using virtual capital.

The platform allows users to monitor selected stocks, view market prices, simulate BUY/SELL transactions, manage virtual holdings, and track portfolio performance without using real money.

> **StockPulse — Learn. Analyze. Trade.**

---

## 🎯 Project Overview

StockPulse provides an interactive environment for users who want to practice stock-market trading without financial risk.

Each new user receives **$100,000 in virtual capital**. Users can use this balance to simulate stock purchases and sales, build a virtual portfolio, and monitor their simulated profit and loss.

The application retrieves market prices using **Yahoo Finance through the `yfinance` Python library** when available. A simulated-price fallback is included so the application can continue operating when external market data is unavailable.

---

## ✨ Features

### 👤 User Features

* User registration
* User login/logout
* Session-based authentication
* Virtual trading account
* $100,000 starting balance
* Market overview dashboard
* Stock price monitoring
* Stock ticker
* Stock details
* Stock chart data
* BUY/SELL simulation
* Fractional-share trading
* Portfolio management
* Average cost calculation
* Profit/Loss calculation
* Trade history

---

### 📊 Market Dashboard

The dashboard provides:

* Stock symbols
* Current prices
* Previous/reference prices
* Percentage changes
* Gainers and losers
* Market statistics
* Interactive stock cards
* BUY and SELL actions

Supported example stocks include:

```text
AAPL
MSFT
GOOGL
AMZN
NVDA
TSLA
META
NFLX
AMD
INTC
PYPL
CRM
BABA
V
JPM
```

---

## 💼 Paper Trading

StockPulse uses virtual money instead of real money.

### BUY Workflow

```text
Select Stock
     ↓
Choose BUY
     ↓
Enter Number of Shares
     ↓
Calculate Total Cost
     ↓
Check Virtual Balance
     ↓
Execute Simulated Trade
     ↓
Update Portfolio
     ↓
Record Trade
```

### SELL Workflow

```text
Select Stock
     ↓
Choose SELL
     ↓
Enter Number of Shares
     ↓
Check Available Holdings
     ↓
Execute Simulated Trade
     ↓
Update Balance
     ↓
Update Portfolio
     ↓
Record Trade
```

---

## 📈 Portfolio Management

The portfolio API calculates:

* Number of shares
* Average purchase price
* Current market price
* Cost basis
* Market value
* Profit/Loss
* Profit/Loss percentage
* Available cash balance

Example:

```text
Stock: AAPL
Shares: 10
Average Cost: $180.00
Current Price: $190.00
Cost Basis: $1,800
Market Value: $1,900
P&L: +$100
```

---

## 👨‍💼 Admin Panel

StockPulse includes an administrator dashboard.

Administrators can:

* Log in securely through the admin interface
* View registered users
* Add users
* Delete users
* View user balances
* View user portfolios
* View trade counts
* Monitor recent trades
* Modify virtual account balances
* Manage administrator sessions

### Admin workflow

```text
Admin Login
     ↓
Admin Dashboard
     ↓
Users / Trades
     ↓
Monitor Accounts
     ↓
Manage Virtual Balances
```

---

## 🧠 Market Data

StockPulse uses the `yfinance` library to retrieve stock information from Yahoo Finance when available.

```text
Stock Symbol
     ↓
yfinance
     ↓
Market Data
     ↓
Flask API
     ↓
Web Dashboard
```

If external market data cannot be retrieved, the application uses a deterministic simulated-price fallback for development purposes.

---

## 🗄️ Database

The application uses **SQLite**.

### Users

Stores:

* User ID
* Username
* Email
* Password hash
* Virtual balance
* Account creation time

### Holdings

Stores:

* User ID
* Stock symbol
* Number of shares
* Average cost

### Trades

Stores:

* User ID
* Stock symbol
* BUY/SELL action
* Number of shares
* Price
* Total transaction value
* Timestamp

### Database relationship

```text
Users
  │
  ├──────── Holdings
  │
  └──────── Trades
```

---

## 🛠️ Technologies Used

### Backend

* Python
* Flask
* Flask-CORS

### Frontend

* HTML5
* CSS3
* JavaScript
* Chart.js

### Database

* SQLite

### Market Data

* yfinance
* Yahoo Finance

### Security

* Flask sessions
* SHA-256 password hashing
* Login-required decorators
* Admin authorization

---

## 📂 Project Structure

```text
Stock_market_price_prediction/
│
├── app.py
│
├── instance/
│   └── stockapp.db
│
├── stockpulse.db
│
├── static/
│   ├── script.js
│   └── style.css
│
└── templates/
    ├── admin.html
    ├── admin_login.html
    ├── base_styles.html
    ├── dashboard.html
    ├── home.html
    ├── login.html
    ├── predict.html
    ├── register.html
    └── stock_detail.html
```

---

## ⚙️ Requirements

Recommended:

```text
Python 3.10+
Flask
Flask-CORS
yfinance
```

Install the dependencies with:

```bash
pip install flask flask-cors yfinance
```

If the project is expanded, a `requirements.txt` file should be added:

```text
Flask
Flask-CORS
yfinance
```

---

## 🚀 Installation

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd Stock_market_price_prediction
```

### 2. Create a virtual environment

Windows:

```bash
python -m venv venv
```

Activate it:

```bash
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install flask flask-cors yfinance
```

### 4. Run the application

```bash
python app.py
```

The application will run at:

```text
http://127.0.0.1:5000
```

You can also access it from another device on the same network using the host machine's local IP address because the application is configured to run on:

```text
0.0.0.0:5000
```

---

## 👤 Demo User

The application creates a demo account during database initialization.

```text
Username: demo
Password: demo123
```

Starting virtual balance:

```text
$100,000
```

---

## 🔐 Administrator

The current development version contains administrator credentials in the source code.

```text
Username: admin
Password: admin123
OTP: 123456
```

⚠️ **Security warning:** These credentials are intended only for development/testing. Do not use these credentials in a production deployment.

Use environment variables, secure password storage, and a proper authentication/OTP system before deployment.

---

## 🔄 Application Architecture

```text
                   STOCKPULSE
                       │
          ┌────────────┴────────────┐
          ↓                         ↓
       FRONTEND                  FLASK
    HTML/CSS/JS                    │
          │                        │
          └──────────────┬─────────┘
                         ↓
                    REST APIs
                         │
             ┌───────────┴───────────┐
             ↓                       ↓
          SQLite                 yfinance
             │                       │
             ↓                       ↓
       Users/Trades/             Market Data
        Holdings
```

---

## 📊 Main Pages

### Home

Introduces StockPulse and its paper-trading features.

### Register

Allows new users to create an account.

### Login

Authenticates registered users.

### Dashboard

Displays market information and simulated trading options.

### Prediction

Provides the project's prediction/analysis interface.

### Stock Details

Displays information for a selected stock.

### Admin Login

Provides administrator authentication.

### Admin Dashboard

Provides user and trading management.

---

## 🔮 Future Enhancements

The project can be improved with:

* Machine Learning-based price prediction
* LSTM/GRU time-series models
* Technical indicator calculations
* RSI analysis
* MACD analysis
* Moving averages
* Bollinger Bands
* Buy/Sell signals
* Advanced portfolio analytics
* Real-time WebSocket market updates
* Watchlists
* Price alerts
* Email notifications
* Mobile Android application
* PostgreSQL/MySQL support
* Secure JWT authentication
* Two-factor authentication
* Docker deployment
* Cloud deployment
* Advanced admin analytics
* CSV/PDF portfolio reports

---

## ⚠️ Disclaimer

StockPulse is an **educational paper-trading application**.

It does not execute real stock-market transactions and does not provide professional financial advice.

Market prices may come from external data services or simulated fallback values.

Users should not treat application predictions, signals, or simulated results as financial advice.

---

## 🎓 Educational Purpose

This project demonstrates practical concepts including:

* Python programming
* Flask web development
* REST APIs
* SQLite database management
* User authentication
* Session management
* CRUD operations
* Financial data retrieval
* Paper trading
* Portfolio calculations
* Frontend development
* JavaScript API integration
* Admin dashboard development

---

## 👨‍💻 Author

**Pavan**

MCA Student

Areas of Interest:

* Software Development
* Python
* Machine Learning
* Data Science
* Web Development
* Database Management
* Application Development

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

### StockPulse

**Learn. Analyze. Trade — Without the Risk.**
