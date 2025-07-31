# 🏦 Bank Transfer Concurrency – Bug Bounty Exam

## 📌 Task Overview
This challenge tests your ability to identify and fix concurrency issues in financial transactions. You are required to **replicate the bug** and **implement a fix** in any programming language of your choice.

---

## 🐞 Problem Description
We have a simple `BankAccount` class:

```java
class BankAccount {
    int balance;

    void transfer(BankAccount to, int amount) {
        if (this.balance >= amount) {
            this.balance -= amount;
            to.balance += amount;
        }
    }
}
```

### 🔎 Issue
When multiple transfers happen simultaneously, **race conditions** can occur:

- Balances can go **negative**
- Money can be **lost** due to incorrect concurrent updates

---

## ✅ Expected Behavior
- **Initial State:**
  - Account A = 1000
  - Account B = 1000
- **Two simultaneous transfers** of 100 each from A → B
- **Expected Output:**
  - Account A = 800
  - Account B = 1200

### ❌ Buggy Output
Due to the concurrency issue, final balances may incorrectly show:
- Account A = 800
- Account B = 1100

---

## 🔨 Rules
- Write **two solutions**:
  1. **Exploit** – Code that demonstrates the concurrency issue
  2. **Fix** – A corrected version that ensures thread safety
- Solutions can be written in **any programming language**
- **Upload** both solutions to a **public GitHub repo**
- **Add** me as a collaborator for review:
  - 📧 **balabagnojether@gmail.com**

---

## 🧑‍💻 Example Topics to Consider
- Multithreading
- Locks / Mutex
- Atomic Operations
- Transactional safety

---

## 🚀 Submission
1. Fork or create a new public repository
2. Include:
   - `exploit.<language>` → Shows race condition
   - `fix.<language>` → Implements concurrency-safe transfer
3. Add this `README.md`
4. Invite collaborator → **balabagnojether@gmail.com**

---

## ✅ Goal
Your fixed solution must **pass** this scenario:

- Account A = 1000  
- Account B = 1000  
- Two simultaneous transfers of 100  
- **Final balances must be:**  
  - A = 800  
  - B = 1200

---

🔒 *This exercise evaluates your understanding of thread safety and secure financial transaction handling.*
