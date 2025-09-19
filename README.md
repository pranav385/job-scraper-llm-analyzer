# 🚀 Automated Job Scraper & Relevance Analyzer 

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)  
![Selenium](https://img.shields.io/badge/Selenium-Automation-brightgreen)  
![LLM](https://img.shields.io/badge/AI-LLM--powered-orange)  
![Status](https://img.shields.io/badge/Status-Active-success)  

---

## 📌 Overview  


This project automates the **end-to-end job search process** by:  

- Scraping job listings from platforms like LinkedIn and Glassdoor.  
- Extracting job details such as title, company, location, and full job descriptions.  
- Analyzing job relevance to the candidate’s profile using a **Large Language Model (LLM)**.  

The system is designed to reduce the manual effort of browsing job boards, filtering relevant roles, and evaluating suitability based on a candidate’s **resume, skills, and career goals**.  

---

## 🏗️ Project Structure  

The project is divided into **three major notebooks**:  

### 1️⃣ LinkedIn Scraper  
- Automates login and navigation using **Selenium**.  
- Scrolls through job listings, handles pagination, and extracts details:  
  - Job Title  
  - Company Name  
  - Location  
  - Job Description (fully scrolled and expanded)  
  - Job Link  
- Implements **human-like behavior** with randomized delays, scrolling, and interaction patterns to avoid detection.  
- Stores all scraped jobs in structured format (`list → DataFrame`).  

### 2️⃣ Glassdoor Scraper  
- Automates login and scraping on Glassdoor.  
- Loads all job listings dynamically by handling **“Show More”** buttons.  
- Extracts:  
  - Job Title  
  - Company Name  
  - Location  
  - Full Job Description  
  - Job Link  
- Handles popups, retries for failed extractions, and ensures duplication prevention with a **link_set**.  
- Builds a **clean dataset** of jobs for downstream analysis.  

### 3️⃣ LLM-Based Job Relevance Analyzer  
- Uses a **prompt-engineered LLM pipeline** to evaluate job relevance.  
- Candidate inputs:  
  - Resume (work experience, education, achievements)  
  - Skills (Python, SQL, Power BI, Tableau, Data Analysis, etc.)  
  - Additional Details (projects, badges, problem-solving highlights)  
- For each job description, the LLM outputs structured JSON containing:  
  - **Relevance** (High / Medium / Low / Not Relevant)  
  - **Reason** (why the classification was given)  
  - **Skills Demanded** (extracted from JD)  
  - **Expected Work** (summary of responsibilities)  
  - **Experience Required** (in words)  
  - **Experience Year** (numeric, or -1 if not mentioned)  
- Final structured data is normalized into a clean **DataFrame** for reporting and filtering.  

---

## 🔑 Features  

- ✅ Automated login and scraping for LinkedIn & Glassdoor  
- ✅ Handles dynamic content, scrolling, and pagination  
- ✅ Extracts **complete job descriptions** (not just previews)  
- ✅ Anti-bot strategies with random delays, scrolls, and human-like interactions  
- ✅ Intelligent **deduplication** of job links  
- ✅ **LLM-powered** job relevance analysis with structured JSON outputs  
- ✅ Data pipeline from raw scraping → structured dataset → job suitability insights  

---

## 📊 Workflow  

### Scraping Phase  
- Collect job listings from LinkedIn & Glassdoor.  
- Save all structured details (title, company, location, JD, link).  

### Analysis Phase  
- Pass job descriptions through LLM.  
- Compare against candidate’s **resume & skills**.  
- Classify into relevance levels.  

### Output Phase  
- Consolidated **DataFrame** with columns:  

Job Title | Company | Location | Link | JD | Relevance | Reason | Skills Demanded | Experience Required | Experience Year


- Exportable to **CSV/Excel** for easy filtering.  

---

## 📂 Example Output  

| Title           | Company      | Location   | Relevance    | Skills Demanded        | Experience Required | Experience Year |  
|-----------------|-------------|------------|--------------|------------------------|---------------------|-----------------|  
| Data Analyst    | ABC Pvt Ltd | Bangalore  | High         | Python, SQL, Power BI  | 1–2 Years           | 1               |  
| Business Analyst| XYZ Tech    | Pune       | Low          | Excel, Reporting       | 3+ Years            | 3               |  
| Backend Engineer| DEF Systems | Remote     | Not Relevant | Java, Spring Boot      | 2–4 Years           | 2               |  

---

## 🔮 Future Scope  

- Expand scraping to **Indeed, Naukri, Monster**.  
- Integrate real-time dashboards in **Power BI / Streamlit**.  
- Add **automated job application** (with resume tailoring).  
- Train a **fine-tuned model** for job-candidate matching instead of relying solely on prompting.  

---

## 🏁 Conclusion  

This project demonstrates the power of combining:  

- 🌐 **Web Automation (Selenium)**  
- 📊 **Data Collection & Cleaning (Pandas, Python)**  
- 🧠 **NLP/LLM Analysis**  

to build a **practical Job Scraper + Relevance Analyzer**.  

It automates tedious job searching and provides **data-driven insights** on which roles are most suitable, saving candidates time and improving focus on **high-potential opportunities**.  

---
