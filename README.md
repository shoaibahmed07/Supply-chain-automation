# Supply-chain-automation
Automation of supply chain tasks using N8n and Quadratic


---

# 📦 Supply Chain Automation Project using N8n & Quadratic

This project automates various supply chain processes using **N8n** and **Quadratic**, with data stored in **Supabase**. It covers end-to-end business data processing—from setting up the database to calculating key supply chain KPIs and identifying top customers.

---

## 🚀 Project Overview

This project simulates real-world supply chain workflows and helps generate actionable insights for business decisions. It was created as part of a learning journey through \[Codebasics.io].

---

## 🧰 Tools & Technologies

* [N8n](https://n8n.io/) – Workflow automation
* [Quadratic](https://quadratic.to/) – AI-powered spreadsheet
* [Supabase](https://supabase.com/) – Backend as a Service (PostgreSQL)
* Excel – For external data
* Python (pandas) – For API and data prep (optional)
* Open Exchange Rates API – For historical FX rates

---

## 📌 Key Components

### ✅ 1. Supabase Setup

* Created a Supabase account and confirmed the email.
* Set up a new organization and project.
* Defined tables:

  * `fact_aggregate`
  * `dim_customers`
  * `dim_products`
  * `dim_targets_orders`
  * `fact_order_line`
* Imported data from CSV/Excel and cleaned date formats.
* Retrieved database connection details for integration with other tools.

---

### ✅ 2. Calendar & Exchange Rate Tables

* **Date Table:** Created a calendar with dates from **March 1, 2025, to May 31, 2025**.
* **Exchange Rate Table:** Pulled historical USD to INR rates (Mar 1 – May 17, 2025) via **Open Exchange Rates API**.

---

### ✅ 3. Data Loading, Cleaning & Merging

Performed multi-source data integration:

* Joined tables:

  * `fact_order_line` + `dim_products` (on `product_id`)
  * * `dim_customers` (on `customer_id`)
  * * `exchange_rate` (on `order_placement_date`)
* Cleaned:

  * Null/missing IDs
  * Date formatting
  * Whitespace & data types
* Calculated **total INR order value**:

  * For USD orders: `price_usd × exchange_rate × order_qty`
  * For INR orders: `price_inr × order_qty`

---

### ✅ 4. Business KPI Calculations

Defined key performance metrics:

| Metric             | Description                                    |
| ------------------ | ---------------------------------------------- |
| Total Order Lines  | Total number of items ordered                  |
| Line Fill Rate     | % of order lines fulfilled                     |
| Volume Fill Rate   | % of quantity fulfilled                        |
| Total Orders       | Unique orders placed                           |
| On-Time Delivery % | Orders delivered on or before promised date    |
| In-Full Delivery % | Orders with all requested quantities fulfilled |
| OTIF %             | Orders delivered both on time and in full      |

---

### ✅ 5. Top Customer Analysis

* Identified **Top 5 Customers (Global)** and **Top 5 in India** based on order value.
* For each, reported:

  * OTIF %
  * IF %
  * OT %
  * Customer Name, ID, and City

---

## 🧠 Key Learnings

* Automating supply chain workflows with N8n and Supabase
* Handling and transforming multi-format data (CSV, Excel, API)
* Creating robust KPIs to track supply chain health
* Visualizing customer performance and fulfillment metrics
* Understanding and calculating OTIF, Line Fill Rate, and Volume Fill Rate

---

## 📊 Understanding the Metrics

### 📦 Orders & Order Lines

* **Order**: A customer's single request (e.g., 1 order = 2 pens + 4 notebooks)
* **Order Line**: Each individual item type (e.g., 2 pens = 1 line)

---

### 📈 Fill Rate Metrics

| Metric           | Measures                      | Example                           |
| ---------------- | ----------------------------- | --------------------------------- |
| Line Fill Rate   | % of order lines fulfilled    | Ordered 2 pens, received 1 → 50%  |
| Volume Fill Rate | % of total quantity fulfilled | Ordered 6 items, received 5 → 83% |

---

### ⏱️ Delivery Metrics

| Metric             | Measures                             | Importance                     |
| ------------------ | ------------------------------------ | ------------------------------ |
| On-Time Delivery % | All items delivered by promised date | Key for logistics teams        |
| In-Full Delivery % | All quantities fulfilled             | Important for supply planning  |
| OTIF %             | Delivered both on time & in full     | Holistic reliability indicator |

---

## 📁 Folder Structure

```
supply-chain-automation/
├── README.md
├── n8n-workflow.json
├── quadratic-spreadsheet.xlsx
├── screenshots/
│   └── workflow-diagram.png
├── docs/
│   └── how-it-works.md
└── LICENSE
```

---

## 📬 Contact

If you have questions, feedback, or suggestions, feel free to reach out via [LinkedIn](https://www.linkedin.com/in/your-profile/) or open an issue on this repo.

---

Would you like me to generate this `README.md` file for you to download?
