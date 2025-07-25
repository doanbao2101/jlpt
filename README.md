Here's the **final polished version** of your `README.md` project description, integrating the JLPT App details and the full crawling pipeline workflow in a clean, professional, and GitHub-friendly format:

---

# JLPT App

Welcome to the **Japanese Exam Preparation App** project! This app is designed to help users practice for the **Japanese Language Proficiency Test (JLPT)** with a focus on three core sections: **Vocabulary & Grammar**, **Reading**, and **Listening**.

---

## 📌 Project Overview

This platform provides a comprehensive learning experience for users preparing for all JLPT levels (**N5–N1**), with features tailored to maximize engagement and learning outcomes:

* **Interactive Quizzes** – Practice JLPT-style questions by category and level.
* **Progress Tracking** – Monitor performance and improvements over time.
* **Real-Time Feedback** – Get instant answer validation and explanations.
* **Mobile-First Design** – Fully responsive UI for mobile and desktop users.

---

## 🧰 Key Technologies

### Front-End

* **FlutterFlow** – Rapid UI development with responsive design.

### Back-End

* **Supabase** – Handles database, authentication, and API endpoints.
* **Python** – Supports ETL tasks, data preprocessing, and scripting.

### Database

* **PostgreSQL (via Supabase)** – Stores users, questions, answers, and progress.

### Additional Tools

* **Web Scraping** – Python (`BeautifulSoup`, `Scrapy`) for data collection.
* **Apache Spark** – Optional, for scalable ETL operations on large datasets.
* **Docker** – For containerized deployment and development environments.

---

## 🚀 Sample JLPT Data Sources
   * [DethiTiengNhat.com](https://dethitiengnhat.com/jlpt/N1/201412/1)
   * [LopHocTiengNhat.com](https://m.lophoctiengnhat.com/de-thi-nang-luc-tieng-nhat-jlpt_n1.html)
   * [Kosei.vn](https://kosei.vn/hot-33-tong-hop-de-thi-jlpt-n1-cac-nam-tai-mien-phi-ban-day-du-n3016.htm)
---

## 🛠️ Crawling & ETL Workflow

### 1. **Extract – Web Crawling**

* Use Python scripts (`BeautifulSoup`, `Playwright`) to extract:

  * JLPT questions and choices
  * Correct answers
  * Explanations (if any)
  * Question level (N5–N1)
  * Category (Vocabulary, Grammar, etc.)
* Output is stored in raw form (HTML or JSON).

---

### 2. **Load – Store Raw Data in PostgreSQL**

* Insert scraped data directly into a raw staging table:

  **Table**: `raw_questions`

  ```sql
  Columns: id, source_url, question_html, level, category, scraped_at, raw_json
  ```

---

### 3. **Transform – Normalize Using SQL Scripts**

* Use SQL scripts or DBT models to transform and insert into structured tables:

  * **questions** (`id`, `question_text`, `level`, `category_id`, `explanation`, `created_at`)
  * **answers** (`id`, `question_id`, `answer_text`, `is_correct`)
  * **categories** (`id`, `name`)

* Apply constraints, enum types, and foreign keys for integrity.

---

### 4. **Optional Enhancements**

* Add `is_processed` to `raw_questions` to track transformation status.
* Automate with schedulers like **cron**, **Airflow**, or **Kestra**.
* Add error handling, retry logic, and logging for resilience.

---

### 🔁 ETL Pipeline Diagram

```
[Websites]
    ↓
[Crawling Script]
    ↓
[PostgreSQL: raw_questions]
    ↓
[SQL Transformation Scripts / DBT]
    ↓
[Structured Tables: questions, answers, categories]
```
