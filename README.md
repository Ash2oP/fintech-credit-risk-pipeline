# Real-Time Credit Underwriting & Fraud Detection Engine

An asynchronous backend data pipeline and machine learning inference engine designed to evaluate digital loan applications in real-time. It ingests simulated transaction histories, engineers financial features, and predicts credit default risk in milliseconds.

This project bridges Core Backend Engineering with Applied Financial Data Science.

---

## The Business Problem

Traditional banking relies on manual underwriting or rigid, rule-based credit scoring (like CIBIL), which takes days and often penalizes thin-file customers. Digital neo-banks require very quick decision-making. This system implements a machine learning pipeline to instantly approve, deny, or flag credit requests based on dynamic transaction behavior.

---

## Tech Stack

* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn
* **Backend Framework:** FastAPI
* **Database & Storage:** PostgreSQL
* **Version Control:** Git & GitHub

---

## Project Architecture

1. **Transaction Simulation:** A Python data generator creates synthetic user profiles, historical bank transactions, and loan application requests to mimic a live consumer base.
2. **The API Gateway:** FastAPI provides the `POST` endpoints where digital loan requests are submitted. It handles high-concurrency traffic simulating thousands of simultaneous users.
3. **Feature Engineering & ML Inference:** Incoming requests are parsed via Pandas. The data is passed to a pre-trained Scikit-Learn model that calculates the **Probability of Default (PoD)**. The system outputs a decision: `Auto-Approve`, `Manual Review`, or `Auto-Reject`.
4. **Relational Data Storage:** The raw application, the extracted features, and the model's final prediction are written into a structured PostgreSQL database using optimized SQL queries to maintain a clean financial ledger.

---

## Execution Roadmap

### Phase 1: Data Modeling & SQL Foundation 
* Design the synthetic transaction dataset and PostgreSQL relational schema (Users, Transactions, Loan_Applications).
* Perform Exploratory Data Analysis (EDA) to find correlations between spending behavior and default risk.
* Commit initial SQL queries and Python data generation scripts to the `/research` directory.

### Phase 2: ML Training & API Integration 
* Train and evaluate baseline classification models (Logistic Regression, Random Forest).
* Develop the FastAPI backend to serve the model via RESTful endpoints.
* Connect the API to the local PostgreSQL database using SQLAlchemy.

### Phase 3: Stress Testing 
* Write automated test scripts to simulate heavy user traffic.
* Refine database queries (using indexing and CTEs) to ensure the API response time remains under 200ms.

---
