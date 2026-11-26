# 🏦 OOP Bank & Currency Exchange Management System

> **"An enterprise-style C++ console application engineered with a strict 3-Tier Layered Architecture, Role-Based Access Control, Audit Logging, and Data Encryption."**

---

---

## 🔗 Quick Access
* 📂 **[Browse Full Source Code (36+ Classes & Headers)](https://github.com/Hazem-Hamada/OOP-Bank-And-Currency-Exchange-System/tree/main/OOP-Bank-System-Source-Code/OOP%20Bank%20%26%20Currency%20Exchange%20System/TheProgrammingWay)**
* 📄 **[View Application Entry Point (`TheProgrammingWay.cpp`)](https://github.com/Hazem-Hamada/OOP-Bank-And-Currency-Exchange-System/blob/main/OOP-Bank-System-Source-Code/OOP%20Bank%20%26%20Currency%20Exchange%20System/TheProgrammingWay/TheProgrammingWay.cpp)**

## 📌 Overview
This project is the capstone system of **Course 11 (OOP as it Should Be – Applications)** from the Software Engineering Foundations Roadmap. Unlike procedural implementations, this system is architected from the ground up using **Object-Oriented Programming** principles to enforce a clean separation between the **Presentation Layer (UI)**, **Business Logic Layer**, and **Data Persistence Layer**.

The application integrates a full-featured **Banking Management System** (across 10 progressive system extensions) alongside an integrated **Currency Exchange Subsystem**, powered by custom-built reusable C++ utility libraries.

---
<img width="2880" height="1676" alt="image" src="https://github.com/user-attachments/assets/94e982af-da1e-4d04-a6fc-784d36079e84" />

<img width="1820" height="1115" alt="image" src="https://github.com/user-attachments/assets/5cc11e1a-d654-43da-a963-2f5521e9cca7" />


## 🏗️ System Architecture

The codebase is organized into distinct architectural layers to maximize maintainability and scalability:

### 1. Business Logic & Domain Layer
* **`clsPerson`:** Base entity encapsulating shared personal attributes and properties.
* **`clsBankClient` (Inherits from `clsPerson`):** Manages client records, account balances, CRUD operations, deposits, withdrawals, and inter-account transfers.
* **`clsUser` (Inherits from `clsPerson`):** Handles system users, Bitwise permission masks, credential verification, and password encryption/decryption.
* **`clsCurrency`:** Encapsulates currency metadata, exchange rate updates, and cross-currency conversion logic.
* **`Global.h`:** Manages active user session state (`CurrentUser`) across the application lifecycle.

* <img width="1832" height="1198" alt="image" src="https://github.com/user-attachments/assets/2608d7eb-11c2-40ee-accc-8ddc1f3879c6" />
<img width="1684" height="1261" alt="image" src="https://github.com/user-attachments/assets/9fc63246-5e81-4e17-bb36-7730f0d9485c" />



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
<img width="1849" height="1018" alt="image" src="https://github.com/user-attachments/assets/5e0eb932-0d30-415b-9216-30c07e502c4f" />
<img width="1844" height="1016" alt="image" src="https://github.com/user-attachments/assets/8e0f4baf-aaf8-40fd-9c50-8229af8739b6" />
<img width="1857" height="1013" alt="image" src="https://github.com/user-attachments/assets/623c2bf5-f628-45f5-a705-99ffc164d1d7" />


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
