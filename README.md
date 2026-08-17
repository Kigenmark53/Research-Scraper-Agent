Automated B2B lead generation, web scraping, and data enrichment pipeline to discover, verify, and format European & Asian buyers for organic agricultural exports using Python and openpyxl.

Suggested GitHub Topics / Tags
python data-pipeline openpyxl lead-generation web-scraping b2b-sales customs-data pandas




# Karakuta B2B Lead Generation & Outreach Pipeline

An automated data pipeline and web intelligence tool designed to discover, enrich, verify, and format high-value international B2B buyer leads (organic avocados and essential oils) for **Karakuta Fresh Produce**.

---

## 📌 Project Overview

This repository contains automation workflows and enrichment scripts used to generate standardized buyer longlists formatted to the official **GIZ AHP ("Partnering in Business with Germany")** program standards. 

The pipeline automates:
* Multi-source data ingestion (HS customs trade manifests, Word documents, industry directories).
* Search engine "Google Dorking" for automated LinkedIn decision-maker discovery (Heads of Sourcing, Procurement Managers, Category Directors).
* Impressum & corporate directory contact extraction.
* Data standardization, entity resolution, and duplicate pruning.
* Automated formatting and styling in Excel (`.xlsx`) using `openpyxl`.

---

## 🚀 Key Features

* **Targeted Search Intelligence (DuckDuckGo / Google Dorking):** Automatically constructs Boolean queries against `linkedin.com/in/` to identify procurement executives without risking account bans.
* **German Telemedia & Impressum Alignment:** Cleans and verifies switchboard area codes across German commercial hubs (Hamburg, Munich, Frankfurt, Stuttgart, etc.) and routes cold contact structures (`Einkaufsleitung / Head of Purchasing`).
* **Customs Trade Verification:** Cross-references live trade declarations (HS Code `080440` / `08044000`) to highlight active importers with proven buying records from Kenyan agricultural exporters.
* **GIZ AHP Template Compliance:** Programmatically builds `.xlsx` sheets with GIZ Deep Blue headers, Steel Blue table fills, auto-filtering, and strict column hierarchies.

---

## 📂 Repository Structure

```text
├── scripts/
│   ├── linkedin_dorker.py        # Automated DDGS/LinkedIn procurement finder
│   ├── impressum_scraper.py      # Website Impressum & contact info scraper
│   ├── template_formatter.py     # openpyxl styling engine for GIZ templates
│   └── hunter_enrichment.py      # Hunter.io API enrichment fallback
├── data/
│   ├── input/                    # Raw HS manifest extracts & docx lists
│   └── output/                   # Processed & styled Excel longlists
├── requirements.txt              # Project dependencies
└── README.md                     # Project documentation
🛠️ Tech Stack & Dependencies
Python 3.10+

Data Processing: pandas, openpyxl, xlrd

Search & Scraping: ddgs (duckduckgo_search), requests, beautifulsoup4

Text Processing: re (Regular Expressions for phone/email pattern recognition)

⚙️ Installation & Setup
Clone the Repository:

Bash
git clone [https://github.com/your-username/karakuta-b2b-lead-pipeline.git](https://github.com/your-username/karakuta-b2b-lead-pipeline.git)
cd karakuta-b2b-lead-pipeline
Create and Activate a Virtual Environment:

Bash
python -m venv venv
# On Windows (PowerShell):
.\venv\Scripts\Activate.ps1
# On macOS/Linux:
source venv/bin/activate
Install Dependencies:

Bash
pip install -r requirements.txt
🚦 Usage
1. Run LinkedIn Procurement Discovery
Bash
python scripts/linkedin_dorker.py
2. Format & Generate GIZ Master Excel Sheet
Bash
python scripts/template_formatter.py
📄 License & Confidentiality
Internal tooling developed for agricultural trade intelligence and market expansion.


---

### Suggested `requirements.txt` File
Add a `requirements.txt` in your project folder with:
```text
pandas>=2.0.0
openpyxl>=3.1.0
xlrd>=2.0.1
requests>=2.31.0
beautifulsoup4>=4.12.0
ddgs>=9.0.0
