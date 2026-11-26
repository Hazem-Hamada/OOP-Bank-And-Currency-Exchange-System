# 🏦 OOP Bank & Currency Exchange Management System

> **"An enterprise-style C++ console application engineered with a strict 3-Tier Layered Architecture, Role-Based Access Control, Audit Logging, and Data Encryption."**

---

## 📌 Overview
This project is the capstone system of **Course 11 (OOP as it Should Be – Applications)** from the Software Engineering Foundations Roadmap. Unlike procedural implementations, this system is architected from the ground up using **Object-Oriented Programming** principles to enforce a clean separation between the **Presentation Layer (UI)**, **Business Logic Layer**, and **Data Persistence Layer**.

The application integrates a full-featured **Banking Management System** (across 10 progressive system extensions) alongside an integrated **Currency Exchange Subsystem**, powered by custom-built reusable C++ utility libraries.

---

## 🏗️ System Architecture

The codebase is organized into distinct architectural layers to maximize maintainability and scalability:

### 1. Business Logic & Domain Layer
* **`clsPerson`:** Base entity encapsulating shared personal attributes and properties.
* **`clsBankClient` (Inherits from `clsPerson`):** Manages client records, account balances, CRUD operations, deposits, withdrawals, and inter-account transfers.
* **`clsUser` (Inherits from `clsPerson`):** Handles system users, Bitwise permission masks, credential verification, and password encryption/decryption.
* **`clsCurrency`:** Encapsulates currency metadata, exchange rate updates, and cross-currency conversion logic.
* **`Global.h`:** Manages active user session state (`CurrentUser`) across the application lifecycle.

### 2. Presentation Layer (UI Screen Hierarchy)
* **`clsScreen`:** Abstracted base screen class responsible for rendering standardized headers, displaying the active logged-in user and system date, and enforcing screen-level access control.
* **Authentication & Main Hub:** `clsLoginScreen`, `clsMainScreen`.
* **Client Operations:** `clsClientListScreen`, `clsAddNewClientScreen`, `clsDeleteClientScreen`, `clsUpdateClientScreen`, `clsFindClientScreen`.
* **Financial Transactions:** `clsTransactionsScreen`, `clsDepositScreen`, `clsWithdrawScreen`, `clsTotalBalancesScreen`, `clsTransfersScreen`, `clsTransferLogScreen`.
* **User & Security Administration:** `clsManageUsersScreen`, `clsListUsersScreen`, `clsAddNewUserScreen`, `clsDeleteUserScreen`, `clsUpdateUserScreen`, `clsFindUserScreen`, `clsLoginRegisterScreen`.
* **Currency Exchange Module:** `clsCurrencyExchangeMainScreen`, `clsCurrenciesListScreen`, `clsFindCurrencyScreen`, `clsUpdateCurrencyRateScreen`, `clsCurrencyCalculatorScreen`.

### 3. Core Reusable Utility Libraries
* **`clsUtil`:** General-purpose utilities including randomized data generation, array/text shuffling, and encryption algorithms.
* **`clsInputValidate`:** Defensive input validation engine guarding against type mismatches, out-of-bounds numbers, and invalid date ranges.
* **`clsDate` & `clsPeriod`:** Custom date arithmetic, system timestamps, and period overlap calculations.
* **`clsString`:** Dual-paradigm string tokenization, sanitization, and formatting library.

---

## 🔐 Key Features & Security Engineering

* **Strict Separation of Concerns:** Zero UI (`cout`/`cin`) logic inside core domain classes (`clsBankClient`, `clsUser`, `clsCurrency`), enabling seamless future migration to GUI or Web APIs.
* **Authentication & Brute-Force Protection:** Enforces credential verification on startup and automatically locks the system after **3 consecutive failed login attempts**.
* **Bitwise Role-Based Access Control (RBAC):** Granular user permissions managed efficiently via Bitwise flags (`&`, `|`), restricting unauthorized access to screens and audit logs.
* **Encryption at Rest:** User passwords are encrypted before serialization to flat-file storage (`Users`) and decrypted dynamically during authentication.
* **Comprehensive Audit Trails:**
  * **Login Register (`LoginRegister`):** Logs every successful login with timestamp, username, encrypted password, and permission level.
  * **Transfer Logs (`TransfersLog`):** Records source/destination accounts, transferred amounts, post-transfer balances, timestamps, and executing user.
* **Currency Exchange & Calculator:** Supports live rate updates, search by currency code or country, and automated cross-currency conversions (via USD base or direct rates).

---

## 🚀 Getting Started

### Prerequisites
* A C++ compiler supporting **C++11 or higher** (MSVC / Visual Studio, GCC, or Clang).

### Running the Project
1. Clone the repository:
   ```bash
   git clone [https://github.com/Hazem-Hamada/OOP-Bank-And-Currency-Exchange-System.git](https://github.com/Hazem-Hamada/OOP-Bank-And-Currency-Exchange-System.git)
