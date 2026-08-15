# OpsAI — AI-Powered Weekly Operations Digest

**AI-Powered Operations Intelligence & Numerical Verification Dashboard**

---

## 📌 Project Overview

OpsAI is a modern, enterprise-grade SaaS frontend web application designed for weekly operational business intelligence. It ingests raw CSV datasets across stores, point-of-sale transactions, staffing shifts, and returns, performs data quality audits, calculates mandatory weekly KPIs, generates perspective-grounded AI summaries, and programmatically verifies numerical claims against actual calculated metrics.

---

## 🚀 Key Features & Workflow Pipeline

The application visualizes and executes the complete 10-stage operational data pipeline:

1. **Raw CSV Data**: Ingests `stores.csv`, `transactions.csv`, `staffing_shifts.csv`, and `returns.csv`.
2. **Data Audit**: Identifies 49 missing values, duplicates, invalid store references (`S099`), unparseable dates, negative revenue amounts, and referential integrity anomalies.
3. **Data Cleaning & Validation**: Maintains tracking of raw records (252), clean records (218), and flagged records (34).
4. **Weekly KPI Engine**: Dynamically calculates the 5 mandatory metrics:
   - **Weekly Revenue**: `SUM(transaction revenue)`
   - **Transactions Count**: `COUNT(valid transactions)`
   - **Return Rate %**: `Returned Transactions / Total Transactions × 100`
   - **Staffing Hours**: `SUM(staff_hours)`
   - **Sales per Staffed Hour**: `Weekly Revenue / Staffing Hours`
5. **Business Perspectives**: Dynamic view switching between:
   - **Store Operations Lead**: Focus on store floor, staffing, return friction.
   - **Regional Multi-Store Lead**: Focus on cross-store benchmarking and resource allocation.
   - **Finance Stakeholder**: Focus on top-line revenue, return refund totals, labor ROI.
6. **AI Digest Generation**: Produces structured JSON summaries grounded in metrics, tagged with `Grounded in calculated metrics` and `AI-generated content` badges.
7. **AI Approach Comparison**: Side-by-side comparison matrix comparing **Approach 1 (Prompt-Based Grounding)** vs **Approach 2 (Structured JSON + Programmatic Verification)**.
8. **Claim Verification Engine**: Parses numerical statements, checks ground-truth metrics, applies a ±0.1% tolerance window, and outputs green **PASS** or red **FAIL** badges with mathematical explanations.
9. **Verification Test Suite**: Executes an automated 5-test suite validating correct numbers, incorrect numbers, correct percentages, incorrect percentages, and mismatched metrics.
10. **Week-8 Holdout Evaluation**: Isolates Week 8 during development phase (Weeks 1–7), executing frozen model rules against unseen holdout data with reflection logging.
11. **Submission Readiness**: Interactive 13-item submission checklist with dynamic progress bar and completion triggers.

---

## 🛠️ Technology Stack

- **HTML5**: Semantic layout structure.
- **Vanilla CSS3 & Tailwind CSS**: Utility-first styling via CDN with light & dark theme support.
- **Vanilla JavaScript (ES6+)**: Modular client-side state management, CSV parsing, audit calculations, verification engine, and test runner.
- **Chart.js**: Line and bar charts for revenue trends and metric breakdowns via CDN.
- **FontAwesome Icons**: UI icons via CDN.

---

## 📂 Data Schema

### `stores.csv`
`store_id, store_name, region, status`

### `transactions.csv`
`transaction_id, store_id, transaction_date, revenue`

### `staffing_shifts.csv`
`shift_id, store_id, shift_date, staff_hours`

### `returns.csv`
`return_id, transaction_id, store_id, return_date, return_amount`

---

## 💻 How to Run Locally

1. Clone or download the workspace directory.
2. Open `index.html` directly in any modern web browser (Google Chrome, Microsoft Edge, Mozilla Firefox, Apple Safari).
3. No build step or local web server is required.
