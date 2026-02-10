# 🔐 Password Strength Analyzer (Python)

A **terminal-based Password Strength Analyzer written in Python** that evaluates password security using **character analysis, scoring logic, and entropy calculation**. The tool helps users understand how strong their passwords are and provides **actionable suggestions** to improve weak passwords.

> ⚠️ This project is for **educational and security-awareness purposes only**.

---

## 🚀 Features

* Secure password input using `getpass` (input hidden)
* Length-based scoring (8+ / 12+ characters)
* Checks for:

  * Lowercase letters
  * Uppercase letters
  * Numbers
  * Special characters
* Detects **common weak patterns** (e.g., `123`, `password`, `qwerty`)
* **Entropy calculation (in bits)** using character set size
* Classifies password strength as:

  * ❌ WEAK
  * ⚠️ MEDIUM
  * ✅ STRONG
* Provides **clear improvement suggestions**

---

## 🧠 How It Works

### 1️⃣ Scoring Logic

The password earns points based on:

* Length (up to 3 points)
* Character variety (lowercase, uppercase, digits, symbols)
* Penalty for common patterns

### 2️⃣ Entropy Calculation

Entropy is calculated using the formula:

```
Entropy = Password Length × log₂(Character Set Size)
```

Higher entropy means the password is harder to crack using brute-force attacks.

---

## 🛠️ Tech Stack

* **Language:** Python 🐍
* **Standard Libraries Used:**

  * `re` – pattern matching
  * `math` – entropy calculation
  * `getpass` – secure password input

---

## 📂 Project Structure

```
password-strength-analyzer/
│
├── password_analyzer.py   # Main analyzer script
├── README.md              # Documentation
```

---

## ▶️ How to Run

1. Clone the repository:

```bash
git clone https://github.com/your-username/password-strength-analyzer.git
```

2. Navigate to the project directory:

```bash
cd password-strength-analyzer
```

3. Run the program:

```bash
python password_analyzer.py
```

4. Enter your password securely (input will be hidden)

---

## 📸 Sample Output

```
🔐 Password Strength Analyzer (Terminal Version)
---------------------------------------------
Enter password (input hidden):

Results:
Strength : STRONG
Entropy  : 72.4 bits

Great! Your password looks strong.
```

---

## 🎯 Learning Outcomes

* Understanding **password entropy & strength metrics**
* Using **regular expressions** for security validation
* Implementing **secure input handling** in Python
* Applying **cybersecurity best practices**

---



## 📜 Disclaimer

This tool does **not store, log, or transmit passwords**. All analysis is done locally.

---

## 👤 Author

**Greeshmanth Nimmala**
Cybersecurity Enthusiast | Python Developer


---

⭐ If you find this project useful, consider giving it a star!
