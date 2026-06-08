# 🏦 Banking Management System

A Java desktop application for managing bank clients and accounts, featuring a clean Swing GUI with full CRUD operations and persistent data storage.

## Features

- **Client Management** — Register new clients with name, CNIC, and phone number; view, search, and remove clients
- **Account Management** — Open multiple accounts per client with auto-generated account numbers (`AC000001`, etc.)
- **Transactions** — Deposit and withdraw funds with balance validation
- **Search** — Look up clients by CNIC
- **Dashboard** — At-a-glance stats: total clients, accounts, and funds held
- **Persistence** — Data is automatically saved to a `.dat` file on every change and reloaded on startup

## Project Structure

```
Banking_System/
├── Main.java         # Entry point — launches the GUI
├── BankGUI.java      # Swing GUI (sidebar navigation, all panels)
├── Bank.java         # Core logic — manages clients/accounts, file I/O
├── Client.java       # Client entity with a list of accounts
├── Account.java      # Account entity with deposit/withdraw methods
├── Person.java       # Personal details (name, CNIC, phone)
└── HBL.dat           # Serialized data file (auto-generated at runtime)
```

## Class Overview

| Class | Role |
|---|---|
| `Person` | Stores personal info (name, CNIC, phone) |
| `Account` | Holds balance; handles deposits and withdrawals |
| `Client` | Wraps a `Person` with a list of `Account`s |
| `Bank` | Top-level manager; serializes state to disk |
| `BankGUI` | Full Swing UI with card-layout navigation |
| `Main` | Calls `BankGUI.main()` |

## Requirements

- Java 11 or higher (uses switch expressions — Java 14+ recommended)
- No external dependencies — standard library only

## How to Run

**Compile:**
```bash
cd Banking_System
javac *.java
```

**Run:**
```bash
java Main
```

You'll be prompted to enter a bank name on first launch. A `.dat` file will be created in the same directory to persist data between sessions.

## Screenshots

<img width="958" height="539" alt="image" src="https://github.com/user-attachments/assets/d5576d8e-a1fa-4452-a8a3-12fd41f9824f" />


## Notes

- Account numbers are auto-generated in the format `AC000001`.
- Client IDs are auto-generated in the format `CL000001`.
- Data is persisted via Java object serialization — do not manually edit the `.dat` file.
- The app saves automatically on every operation; there is no manual save step.

## Course Info

Developed as part of **CYS-244** (2025).
