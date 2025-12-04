# Cash Flow Minimizer System

## 📌 Project Overview
The Cash Flow Minimizer System is a C++ implementation designed to reduce the number and value of inter-bank or inter-entity transactions. The system computes net balances, identifies creditors and debtors, and settles payments using an optimized matching algorithm based on **dual max-heaps**. Transactions are automatically routed through an intermediary bank such as the **World Bank**, which supports all payment transfers.
This project demonstrates efficient settlement minimization, graph reduction, and constrained matching, achieving significant reduction in total settlements and improving overall transaction efficiency.

---

## 🔧 Key Concepts & Technical Approach

### ✔ Net Balance Computation
- Each entity’s **net position** is calculated from initial transactions.
- Positive balance → **Creditor**  
- Negative balance → **Debtor**

### ✔ Max-Heap Settlement Algorithm (O(n log n))
Two priority queues (max-heaps) are used:
- **Creditor heap**: highest positive balances first  
- **Debtor heap**: highest negative balances first  

At each step:
1. Extract the top creditor & debtor.
2. Settle the minimum of the two amounts.
3. Push any remaining balance back into the respective heap.
This greedy approach ensures **minimal number of settlement edges**.

## Features
- Minimizes number of transactions and total transaction volume.
- Supports heterogeneous payment-type compatibility; inserts intermediary transfers when needed. :contentReference[oaicite:7]{index=7}
- Uses max-heaps for efficient selection of largest creditors/debtors (polynomial / scalable).

---

## 📂 Repository Structure
```
cash-flow-minimiser/
│── src/
│   └── main.cpp                # Core C++ implementation
│── results/
│   └── result.png             # Actual output generated from your program
│── README.md                   # Project documentation
│── .gitignore                  # Optional but recommended
```
## Results
The results show:
- Reduced number of transaction edges  
- Guaranteed payment compatibility  
- Correct flow balancing between debtors and creditors 
