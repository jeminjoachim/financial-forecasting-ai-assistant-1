# 📊 Financial Forecast Assistant (n8n Workflow)

This repository contains an **n8n workflow** that automates the extraction, summarization, and forecasting of financial data from company annual reports.  

The workflow leverages **Google Drive, Google Sheets, and AI (DeepSeek + LangChain)** to provide a streamlined financial analysis pipeline.

---

## 🚀 Features
- **Automated PDF ingestion**: Fetches annual reports directly from Google Drive.  
- **Text extraction**: Extracts content from PDF reports.  
- **AI-powered summarization**: Generates structured summaries with key financials:  
  - Year  
  - Revenue  
  - Operating Income (EBIT)  
  - Net Income  
  - EPS  
  - Cash Flow  
  - Other key metrics  
  - Management guidance  
  - Key events & risks  
- **Google Sheets integration**: Stores all extracted summaries in a structured table.  
- **Forecasting engine**: Analyzes multi-year summaries and generates **financial forecasts** for the next fiscal year with assumptions and risk scenarios.  
- **Interactive chat**: Users can query financial data and forecasts in real-time.

---

## 🛠️ Tech Stack
- [n8n](https://n8n.io/) – Workflow automation platform  
- Google Drive – Source of annual report PDFs  
- Google Sheets – Storage of structured financial summaries  
- [LangChain](https://www.langchain.com/) – AI orchestration  
- DeepSeek LLM – AI model for summarization & forecasting  

---

## 📂 Workflow Overview
1. **Manual Start** → Triggers workflow  
2. **Fetch PDFs** → Lists and downloads annual reports from Google Drive  
3. **Extract Text** → Reads financial text from PDFs  
4. **Summarize Report (AI)** → Converts raw text into structured financial summaries  
5. **Parse & Save** → Cleans and appends results to Google Sheets  
6. **Chat Query** → Allows users to query financial data  
7. **Forecasting** → AI analyzes 5 years of summaries and generates predictions  

---

## ⚙️ Setup Instructions
1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/financial-forecast-assistant.git

2. Import the workflow into n8n:
   - Open n8n → Workflows → Import from File
   - Upload financial_forecast_assistant.json

3. Configure credentials:
   - Google Drive OAuth2 (for report fetching)
   - Google Sheets OAuth2 (for saving summaries)
   - DeepSeek or Open AI API Key (for AI-powered summarization & forecasting)

4. Run the workflow manually or via the chat trigger.

---

## 📊 Example Output

Structured summary for each annual report:
  - Year: 2023
  - Revenue: $43.0B
  - Operating Income / EBIT: $10.5B
  - Net Income: $8.2B
  - EPS: $2.15
  - Cash Flow: $6.8B
  - Other Key Metrics: Dividend payout increased by 5%
  - Management Guidance: Focus on emerging markets growth
  - Key Events / Strategic Actions: Acquisition of XYZ Beverages
  - Risks / Challenges Noted: Rising input costs, FX headwinds

Forecast:
  - Revenue expected to grow 4–6% driven by strong APAC demand.
  - EPS forecasted at $2.25–2.35 with cost optimization measures.

Risks: Inflationary pressures, regulatory uncertainties.

---

## 📌 Use Cases

Financial analysts automating company research

Students preparing investment or case studies

Researchers building datasets from annual reports

Automating financial due diligence processes

---

### 📄 License

This project is licensed under the MIT License.

---

### 🤝 Contributing

Pull requests are welcome! If you find a bug or want to suggest a feature, feel free to open an issue.
