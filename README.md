# 💰 LoanContract

**LoanContract** is a Solidity-based smart contract designed for issuing and repaying loans on the Ethereum blockchain. It allows an owner to issue loans with a predefined interest rate, track repayment progress, and manage loan details transparently. Borrowers can view their loan status, make repayments, and check outstanding balances at any time.

---

## 📖 Features

- ✅ **Issue Loans**  
  The contract owner can issue loans to borrowers with a fixed interest rate of 8%.

- 💸 **Repay Loans**  
  Borrowers can repay loans before the due date in multiple installments. The contract ensures repayments don’t exceed the remaining balance.

- 📊 **View Loan Details**  
  Borrowers can view their loan’s principal, interest rate, due amount, repaid amount, and due date.

- 🧮 **Outstanding Balance**  
  Borrowers can check how much they still need to repay.

---

## 🧱 Smart Contract Overview

### 🔷 Loan Struct

The `Loan` struct stores all loan-related details:

```solidity
struct Loan {
    uint256 amount;         // Principal loan amount
    uint256 interestRate;   // Interest rate in percentage (8%)
    uint256 dueAmount;      // Total due amount (principal + interest)
    uint256 dueDate;        // Repayment deadline (30 days from issuance)
    uint256 amountPaid;     // Total repaid amount
}
