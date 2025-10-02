
# Bank Transaction Fraud Detection Using Graph Analytics

## Introduction

This project presents an advanced forensic analytics system that leverages **graph-based techniques** to detect fraudulent transactions, money laundering activities, and suspicious financial behavior in banking networks. By representing **accounts as nodes** and **transactions as edges**, the system uncovers hidden fraud rings, circular money flows, and structuring patterns with high accuracy.

---

## System Overview

* **Data Preprocessing Pipeline**

  * Automated removal of null values and duplicate records.
* **Multi-layered Outlier Detection**

  * Based on the Interquartile Range (IQR) methodology.
* **Relative Size Factor (RSF) Analysis**

  * Detects accounts with disproportionately large transactions.
* **Balance Reconciliation Engine**

  * Flags discrepancies between reported balances and actual transactions.
* **Graph Network Construction**

  * Intelligent node–edge mapping for transaction visualization.
* **Pattern Recognition Algorithms**

  * Detect smurfing, round-tripping, and circular money flows.
* **Interactive Visualization**

  * Normal transactions in **blue**; fraudulent transactions in **red**.

**Performance:** Achieved a **6.67% fraud detection rate** — 3,614 suspicious transactions identified from a dataset of 54,222 total records.

---

## Fraud Detection Methods

### 1. Outlier Analysis

* **Technique:** Interquartile Range (IQR).
* **Findings:** Identified unusually high-value transactions.
* **Key Patterns:** Transaction types `'Dt'` and `'Wl'`, primarily from **'RET'** and **'EU'** senders.

---

### 2. Relative Size Factor (RSF)

* **Concept:** Measures whether a sender makes disproportionately large individual transactions.
* **Threshold:** RSF > 2 indicates suspicious activity.
* **Focus:** `'ArRC'` transactions from **'EU'** senders to **'operator'** receivers.
* **Stats:**

  * Mean amount: **19,114.41**
  * Median amount: **2,819.34**

---

### 3. Balance Inconsistency Detection

* **Objective:** Detect discrepancies between transaction amounts and reported account balances.
* **Findings:**

  * Mean discrepancy: **96,458.23**
  * Median discrepancy: **64,311.20**
* **Implication:** Suggests possible manipulation or data integrity issues.

---

### 4. Graph-Based Pattern Detection

* **Network Construction:** Nodes = accounts, Edges = transactions.
* **Techniques:**

  * **Smurfing Detection:** Accounts making >10 small transactions below average.
  * **Cycle Detection:** Identifies **circular money flows** and **fraud rings**.
  * **Centrality Analysis:** Detects highly connected or influential suspicious accounts.

---

## Technologies Used

* **Programming Language:** Python
* **Libraries:**

  * **Pandas, NumPy** → Data manipulation
  * **NetworkX** → Graph construction & analytics
  * **Matplotlib, Seaborn** → Visualization
* **Environment:** Jupyter Notebook

---

## Dataset

* **Format:** Structured CSV file containing:

  * Sender/receiver IDs, account numbers, transaction amounts, transaction types, timestamps, and balances.
* **Size:** 54,222 transactions analyzed.

---

## Key Findings

* **Total Fraudulent Transactions:** 3,614 (≈6.67%).
* **Primary Involvement:** **'EU' (Enterprise User)** accounts were most frequently associated with fraudulent activity.
* **Balance Discrepancies:** Concentrated in **'EU'** senders, suggesting potential manipulation.
* **High RSF Transactions:** Mostly found in `'ArRC'` type transactions.
* **Graph Analysis:** Successfully identified **smurfing**, **round-tripping**, and **circular transaction patterns**.

---

## Disclaimer

This project is intended solely for **educational and research purposes**. The fraud detection methods described are based on statistical techniques and graph analysis. In practice, real-world fraud detection systems require **more advanced validation, regulatory compliance, and domain expertise**.

---

