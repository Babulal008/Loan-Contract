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
🛠 Functions
issueLoan(address borrower, uint256 loanAmount)
Issues a loan with a fixed 8% interest rate.

Only the contract owner can call this function.

Calculates the total due including interest.

repayLoan(uint256 amount)
Borrower can repay the loan in parts.

Ensures repayment does not exceed the remaining amount.

Emits a LoanRepaid event.

getOutstandingBalance()
Returns the remaining balance the borrower needs to repay.

getLoanDetails(address borrower)
Returns full details of the loan, including principal, interest rate, total due, paid amount, and due date.

📣 Events
LoanIssued(address borrower, uint256 amount, uint256 interestRate, uint256 dueAmount)
Emitted when a new loan is issued.

LoanRepaid(address borrower, uint256 amountPaid, uint256 remainingAmount)
Emitted when a borrower makes a repayment.

🖥️ Frontend Integration
To interact with the smart contract from a frontend application, the following tools and features are recommended:

🔑 Prerequisites
🦊 Ethereum Wallet: Use MetaMask or any Ethereum-compatible wallet.

🔌 Web3 Libraries: Use Web3.js or Ethers.js for blockchain interaction.

🎯 Frontend Features
Issue Loan
Admin inputs the borrower’s address and loan amount, then calls the issueLoan function.

Repay Loan
Borrower enters the amount to repay and invokes repayLoan.

View Loan Details
Borrower checks the principal, interest, total due, amount paid, and due date.

Check Outstanding Balance
