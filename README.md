# 📡 RadarPro: Regulatory Compliance & Reporting Engine

![Status](https://img.shields.io/badge/Status-Production_Enterprise-success)
![Compliance](https://img.shields.io/badge/Standard-NFIU_&_CBN_Compliant-blue)
![Stack](https://img.shields.io/badge/Stack-Python_XML_Automation_|_Django-green)

> **⚠️ Portfolio Notice:** This repository serves as a technical case study for **RadarPro**, a proprietary compliance software developed for Adroit Consulting. The source code is confidential. This document details the system architecture and my role in automating regulatory reporting for Nigerian Financial Institutions.

---

## 📸 System Interface
<div align="center">
  <img src="./assets/2025-11-24 04_37_59-.png" alt="RadarPro Compliance Dashboard" width="800">
  <p><em>Figure 1: The Compliance Reporting Generator</em></p>
</div>

---

## 🏛️ Project Overview

**RadarPro** is a specialized "RegTech" (Regulatory Technology) solution designed to bridge the gap between Financial Institutions and Regulatory Bodies (specifically the **NFIU** - Nigerian Financial Intelligence Unit).

In the banking sector, failing to report specific transactions within a set timeframe results in massive sanctions. RadarPro automates this entire lifecycle, converting raw banking data into the strict XML/JSON formats required by government portals (goAML), eliminating manual error and ensuring 100% compliance.

---

## 📦 Core Reporting Modules

The system is divided into four critical reporting engines, powered by robust Python scripts:

### 1. CTR (Customer Transaction Reporting)
* **Function:** Automatically detects and reports cash transactions exceeding the statutory limit (e.g., ₦5M for individuals, ₦10M for corporates).
* **Automation:** Daily cron jobs scan the core banking database, aggregate cash lodgments/withdrawals, and generate the report file.

### 2. FTR (Foreign Transaction Reporting)
* **Function:** Tracks all cross-border inflows and outflows.
* **Compliance:** Ensures every forex transaction is captured with necessary metadata (Sender, Receiver, Purpose of Payment) before submission.

### 3. STR (Suspicious Transaction Reporting)
* **Function:** An intelligent detection module that flags transactions that do not fit a customer's standard profile (e.g., a student account suddenly receiving ₦50M).

### 4. SAR (Suspicious Activity Reporting)
* **Function:** A behavioral monitoring tool used to report suspicious *activities* (not just transactions), such as potential staff collusion or attempted bypass of internal controls.

---

## ⚙️ Technical Highlight: Python XML Automation

The most technically challenging aspect of this project was adhering to the strict **goXML / goAML** schema requirements enforced by the NFIU.

* **The Challenge:** The NFIU portal rejects submissions if a single XML tag is out of order or if a date format is incorrect. Manual file creation was impossible at scale.
* **My Solution:** I engineered a custom **Python Automation Engine** that handles the generation pipeline:

1.  **Extraction:** Python scripts query the Oracle/MSSQL Banking Database to pull transaction rows.
2.  **Validation:** A pre-processing layer checks for data integrity (e.g., ensuring every transaction has a valid BVN and Address) *before* generation.
3.  **Serialization:** Using Python's `lxml` and string formatting to map the banking data into the complex, nested XML tree structure required by goAML.
4.  **Encryption:** The final XML files are hashed and encrypted for secure transmission.

> **Key Tech:** `Python`, `Celery` (Background Tasks), `Pandas` (Data Aggregation), `XML/XSD Validation`.

---

## 👨‍💻 My Role

As the **Lead Developer**, I was responsible for:
1.  **Logic Implementation:** Coding the rulesets for CTR/FTR detection based on current CBN circulars.
2.  **Schema Mapping:** Mapping internal banking database fields to external regulatory schemas.
3.  **Performance:** Reducing report generation time from hours to minutes using efficient SQL queries.

---

## 📬 Contact

**Tunde Oluwamo**
*Senior Full Stack Developer & RegTech Specialist*
[ linkedin.com/in/oluwamo-shadrach-740242185 ]
