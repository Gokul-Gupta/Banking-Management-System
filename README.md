# 🏦 Java Banking Management System

A console-based Banking Management System built with **Core Java** and **SQLite** via JDBC.

---

## 📁 Project Structure

```
BankingSystem/
├── src/
│   └── banking/
│       ├── Main.java                  ← Entry point
│       ├── model/
│       │   ├── User.java              ← User entity
│       │   └── Transaction.java       ← Transaction entity
│       ├── dao/
│       │   ├── UserDAO.java           ← DB operations for users
│       │   └── TransactionDAO.java    ← DB operations for transactions
│       ├── service/
│       │   └── BankingService.java    ← Business logic
│       ├── ui/
│       │   └── ConsoleUI.java         ← Console formatting
│       └── util/
│           ├── DatabaseConnection.java ← JDBC connection manager
│           └── AccountNumberGenerator.java ← Utility helpers
├── lib/
│   └── sqlite-jdbc-3.xx.x.jar         ← SQLite JDBC driver (add manually)
├── bin/                               ← Compiled classes (auto-generated)
├── .vscode/
│   ├── launch.json
│   └── settings.json
└── README.md
```

---

## ⚙️ Setup Instructions

### 1. Prerequisites
- Java JDK 17 or higher
- VS Code with **Extension Pack for Java** installed
- SQLite JDBC driver

### 2. Download SQLite JDBC Driver
Download from: https://github.com/xerial/sqlite-jdbc/releases

Place the `.jar` file inside the `lib/` folder and rename it to `sqlite-jdbc.jar`.

> The project is configured to pick up all `.jar` files from the `lib/` directory automatically.

### 3. Open in VS Code
```bash
code BankingSystem
```

### 4. Run the Application
- Open `src/banking/Main.java`
- Press **F5** or click **Run** → **Start Debugging**
- Or use the Run button at the top right of the editor

---

## 🚀 Features

| Feature | Description |
|---|---|
| Create Account | Register with name, phone, PIN, initial deposit |
| Login | Authenticate with Account No + PIN |
| Deposit | Add funds to account |
| Withdraw | Withdraw with minimum balance check (₹500) |
| Transfer | Transfer between accounts (atomic) |
| Transaction History | Full history with color coding |
| Change PIN | Secure PIN update |
| Admin Panel | View all accounts & transactions |

---

## 🔐 Admin Credentials (Default)
- **Username:** `admin`
- **Password:** `admin123`

> Change these in `Main.java` before production use.

---

## 🗄️ Database

The app auto-creates `banking.db` (SQLite file) on first run in the project root.

**Tables:**
- `users` — account_no, name, phone, pin, balance, created_at
- `transactions` — transaction_id, account_no, type, amount, balance_after, description, date

---

## 📌 Notes

- Minimum balance: ₹500.00
- PIN: 4–6 numeric digits
- Phone: 10 numeric digits
- Account number format: `ACCxxxxxxxx` (auto-generated)
