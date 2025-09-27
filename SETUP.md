# 🚀 Setup Guide – Financial Forecasting AI Workflows (n8n + AI)

This guide explains how to set up and use the two open-source workflows in this repository:  

**Financial Forecast Assistant (Annual Reports)**  

Both workflows are built with **n8n**, **Google Drive**, **Google Sheets**, and **DeepSeek (via LangChain)**.

---

## 1️⃣ Prerequisites
Before you start, make sure you have:
- A **Google account** (for Drive & Sheets access)  
- A **DeepSeek API Key** (for AI processing)  
- An installation of **n8n** (desktop app, Docker, or cloud)  
  👉 [Download n8n](https://n8n.io/download)  

---

## 2️⃣ Import the Workflows
1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
Open n8n.

2. Go to Workflows → Import from File.

3. Upload the JSON file(s):
financial_forecast_assistant.json → Annual Reports workflow

---

## 3️⃣ Configure Credentials
You will need to set up 3 connections in n8n:

🔑 Google Drive OAuth2
Go to Settings → Credentials → New → Google Drive OAuth2 API
- Connect your Google account
- Allow access to Drive files

🔑 Google Sheets OAuth2
Go to Settings → Credentials → New → Google Sheets OAuth2 API
- Connect your Google account
- Allow access to edit Sheets

🔑 DeepSeek API
- Go to Settings → Credentials → New → DeepSeek API
- Paste your API key

---

4️⃣ Update Workflow Settings

📂 Google Drive Folder
Replace the folder ID in the List Drive PDFs node with your own folder ID.
Example format:

bash
Copy code
'1AbcD123xyz...' in parents and mimeType='application/pdf'
📊 Google Sheets
Update the Save to Sheet node to point to your Google Sheet.

Use the format:

bash
Copy code
https://docs.google.com/spreadsheets/d/<DOCUMENT_ID>/edit
🗂️ Sheets per Workflow
Annual Reports Workflow → summaries stored in your target sheet.

Quarterly Workflow →

Sheet2 → Quarterly summaries

Sheet3 → Forecast outputs

---

## 5️⃣ Run the Workflows
📌 Annual Reports Workflow
Place annual report PDFs into your Google Drive folder.

Run the workflow via Manual Start.

Flow:

Fetch PDFs → Extract Text → Summarize → Parse → Save to Google Sheets

📌 Quarterly Data Workflow
Place quarterly earnings reports / transcripts in Drive.

Run via Manual Start.

Flow:

Fetch PDFs → Extract Text → Summarize → Save to Sheet2

AI Agent generates forecasts → Save/Update in Sheet3

---

## 6️⃣ Validate the Results
Open your linked Google Sheet.

Annual workflow → Each report appears as a structured row.

Quarterly workflow →

Sheet2 contains parsed quarterly summaries

Sheet3 contains full-year AI forecasts

---

## 7️⃣ Notes & Tips
- PDF quality matters → Clean, text-based PDFs work best.
- Keep reports under ~80 pages (limit set in Extract Text node).
- AI forecasts are not financial advice → Use for structuring analysis, not final decision-making.
- If errors occur, check the _debug fields in the Parse/Code nodes.
- Adjust Google Drive/Sheets IDs when you switch to new companies or datasets.
