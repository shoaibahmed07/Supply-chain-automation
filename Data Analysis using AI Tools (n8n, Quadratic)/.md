# 📊 Data Analysis using AI Tools (n8n, Quadratic)

![Workflow](./ss/Data%20analysis%20using%20AI%20-%20workflow.png)

## 🚀 Project Overview

This project showcases a complete end-to-end analytics pipeline using **AI-powered tools** like **n8n and Quadratic**, tailored for a **supply chain** use case.

With email automation, PostgreSQL data storage, and AI-driven spreadsheets, this project demonstrates how to build scalable, intelligent data solutions without writing code from scratch.

Inspired by [Codebasics](https://www.youtube.com/watch?v=PglKAYgRdJ4&ab_channel=codebasics).

---

## 🛠️ Tools Used
- **n8n** – Agentic workflow automation (email → JSON → PostgreSQL)
- **Supabase** – PostgreSQL cloud DB
- **Quadratic** – AI-powered spreadsheet
- **OpenExchangeRates** – For USD to INR conversion
- **Python via AI** – Used inside Quadratic prompts

---

## 🔄 Workflow Summary

### 1️⃣ Data Acquisition

Sales data from **daily emails** in the form of CSVs.

---

### 2️⃣ Email Automation with n8n

- Monitored Gmail for specific subjects
- Extracted CSV attachments
- Converted to JSON format

![Setting up N8N](./ss/Setting%20up%20N8N%20for%20Data%20Automation.png)

---

### 3️⃣ PostgreSQL Integration via Supabase

- Connected n8n to a cloud PostgreSQL DB
- Used JSON output to populate fact and dimension tables

![PostgreSQL Insert](./ss/Ingesting%20Data%20into%20PostgreSQL%20Database.png)

![Date Formatting](./ss/Date%20Transformation.png)

---

### 4️⃣ Execution Sample

- Before execution  
  ![Before](./ss/Before%20executing%20workflow.png)

- Executing workflow  
  ![Executing](./ss/Executing%20n8n%20workflow.png)

- Final Result  
  ![Result](./ss/Results%20%28%20CSV%20file%20fetched%20from%20email%20%E2%86%92%20converted%20to%20JSON%20%E2%86%92%20inserted%20in%20PostgreSQL%20%28hosted%20in%20Supabase%29%29.png)

---

### 5️⃣ Quadratic Integration

- Connected to PostgreSQL using Supabase credentials
- Pulled data into individual sheets

![Quadratic Connection](./ss/Connecting%20Quadratic%20to%20PostgreSQL%20and%20Pulling%20Data.png)

---

### 6️⃣ Creating Auxiliary Tables via AI Prompts

- `Dim Date` and `Exchange Rates` created using natural language prompts

![AI Tables](./ss/Creating%20Auxiliary%20Tables%20in%20Quadratic%20%28using%20AI%20Prompts%29.png)

---

### 7️⃣ Final Data Cleaning and Summary Table

- Merged fact & dimension tables
- Currency conversion applied
- AI-generated Python cleaned and transformed the data

![Fact Summary](./ss/Data%20Cleaning%20and%20Summarization%20%28Fact%20Summary%20Sheet%29.png)

---

## 📌 Key Learnings

- AI tools like **n8n** and **Quadratic** reduce manual coding.
- However, **core skills in Python, SQL, and data modeling** are essential to:
  - Debug AI hallucinations
  - Improve prompt quality
  - Validate logic and results

---

## 📸 Supabase ER Diagram

![Supabase ERD](./ss/Supabase_daig.png)

---

## 📂 License

MIT License – Free to use and modify.

---

## 🙌 Acknowledgment

Built with guidance from the **Codebasics community**.
