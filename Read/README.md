# Banking & Financial Analytics Dashboard

A comprehensive **Banking & Financial Analytics Dashboard** built using **Microsoft Power BI** to analyze customer behavior, transaction activity, lending performance, credit risk indicators, and merchant/geographic performance.

This project transforms a large synthetic banking dataset into an interactive Business Intelligence solution containing six analytical dashboards designed to provide meaningful business insights and support data-driven decision-making.

---

## Project Overview

The objective of this project is to analyze a banking ecosystem across multiple dimensions:

- Customer demographics and financial profiles
- Customer credit scores
- Accounts and account balances
- Debit and credit card distribution
- Transaction volume and transaction value
- High-value transaction activity
- Loan portfolio performance
- Loan amounts and interest rates
- Risk indicators
- Merchant performance
- Geographic transaction activity

The dashboard combines **Power Query, data modeling, DAX, and Power BI visualizations** to turn raw banking data into actionable insights.

---

# Dashboard Pages

The Power BI report contains six analytical dashboards.

## 1. Executive Overview

The Executive Overview provides a high-level summary of the banking ecosystem.

### Key KPIs

- Total Customers
- Total Accounts
- Total Transaction Value
- Total Transactions
- Average Transaction Value

### Key Analysis

- Transaction value over time
- Transaction volume over time
- Top merchants by transaction value
- Transaction activity by city
- Loan penetration
- Credit card share
- High-value transaction contribution

### Dashboard Preview

![Executive Overview](screenshots/Executive_Overview.png)

---

## 2. Customer Analytics

The Customer Analytics dashboard focuses on customer demographics, credit profiles, loan participation, and account relationships.

### Key KPIs

- Total Customers
- Average Credit Score
- Customers With Loans
- Loan Customer %
- Accounts per Customer

### Key Analysis

- Customer distribution by credit score
- Customer distribution by city
- Customers with and without loans
- Loan exposure across credit-score segments
- Account balance across credit-score segments

### Dashboard Preview

![Customer Analytics](screenshots/Customer_Analytics.png)

---

## 3. Transaction Analytics

The Transaction Analytics dashboard analyzes transaction volume, transaction value, transaction sizes, and high-value activity.

### Key KPIs

- Total Transactions
- Total Transaction Value
- Average Transaction Value
- Median Transaction Value
- Maximum Transaction Value

### Key Analysis

- Transaction value over time
- Transaction volume over time
- Average transaction value over time
- Transaction amount distribution
- High-value transaction activity

### Dashboard Preview

![Transaction Analytics](screenshots/Transaction_Analytics.png)

---

## 4. Loans & Credit Analysis

The Loans & Credit Analysis dashboard focuses on the bank's lending portfolio and credit-related metrics.

### Key KPIs

- Total Loans
- Total Loan Amount
- Average Loan Amount
- Average Interest Rate
- Loan Penetration %

### Key Analysis

- Loan amount over time
- Loan distribution by loan amount
- Loan exposure by city
- Loan distribution by interest-rate segment
- Loan customers over time

### Dashboard Preview

![Loans & Credit Analysis](screenshots/Loans_&_Credit_Analysis.png)

---

## 5. Risk Analysis

The Risk Analysis dashboard provides rule-based indicators to identify potentially higher-risk customer and transaction segments.

### Key KPIs

- High Risk Customers
- High Risk Customer %
- Low Credit Score Customers
- Low Credit Score %
- High Value Transaction %

### Key Analysis

- High-risk customers by credit-score segment
- High-risk customers by city
- Low credit-score customers over time
- High-value transactions over time
- High-risk customer trends

### Dashboard Preview

![Risk Analysis](screenshots/Risk_Analysis.png)

> **Important:** This dashboard does not represent a production fraud-detection system. The dataset does not contain a confirmed fraud label, so the analysis uses rule-based risk indicators based on factors such as credit score and high-value transactions.

---

## 6. Merchant & Geographic Analysis

The Merchant & Geographic Analysis dashboard evaluates merchant performance and geographic transaction patterns.

### Key KPIs

- Total Merchants
- Transactions per Merchant
- Transaction Value per Merchant
- Transactions per City
- Transaction Value per City

### Key Analysis

- Top merchants by transaction value
- Top merchants by transaction count
- Transaction value by city
- Transaction volume by city
- Merchant transaction value over time

### Dashboard Preview

![Geographic Analysis](screenshots/Geographic_Analysis.png)

---

# Dataset

The project uses the **Synthetic Banking Dataset** containing approximately **1.26 million records** across multiple banking entities.

## Dataset Size

| Entity | Records |
|---|---:|
| Customers | 50,000 |
| Accounts | 75,000 |
| Cards | 100,000 |
| Merchants | 5,000 |
| Branches | 500 |
| Loans | 30,000 |
| Transactions | 1,000,000 |
| **Total** | **1,260,500** |

The transaction dataset was originally provided in SQL format and was converted into CSV format for use in Power BI.

## Dataset Source

Synthetic Banking Dataset by Akram Belhadi:

https://www.kaggle.com/datasets/akrambelha/synthetic-banking-dataset-csv-sql-sqlite

**License:** CC BY 4.0

---

# Data Model

The Power BI model connects customers, accounts, cards, transactions, loans, and merchants through relational relationships.

### Main Data Model

```text
                    ┌───────────────┐
                    │   Customers   │
                    └───────┬───────┘
                            │
                 ┌──────────┴──────────┐
                 │                     │
                 ▼                     ▼
          ┌─────────────┐       ┌─────────────┐
          │   Accounts  │       │    Loans    │
          └──────┬──────┘       └─────────────┘
                 │
          ┌──────┴───────┐
          │              │
          ▼              ▼
     ┌─────────┐   ┌──────────────┐
     │  Cards  │   │ Transactions │
     └─────────┘   └───────┬──────┘
                           │
                           ▼
                     ┌───────────┐
                     │ Merchants │
                     └───────────┘

                     DateTable
                         │
                         ▼
                    Transactions
