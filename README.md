# SAAFAH — Chairman's Business Review 2026

Executive dashboard for SAAFAH (سعفة) — Consolidated Financial & Operational Forecast FY 2026.

## Architecture
- **`index.html`** — Single-file dashboard (HTML + CSS + JS)
- **`data.xlsx`** — Excel workbook containing all data (Financial, Cash Flow, Strategy, Pipeline, Sales)
- **`vercel.json`** — Vercel deployment config

## Data Source
The dashboard reads directly from `data.xlsx` using [SheetJS](https://sheetjs.com/) (client-side XLSX parser). No backend or Google Sheets dependency required.

### Updating Data
1. Edit `data.xlsx` locally (or in Excel/Google Sheets and re-export as .xlsx)
2. Replace the file in the repo
3. Push to GitHub → Vercel auto-deploys

### Excel Sheet Structure
| Sheet | Purpose |
|-------|---------|
| `Financial_Overview` | Quarterly P&L inputs and KPI formulas |
| `Cash_Flow` | Quarterly cash flow linked to financial data |
| `Strategy_Operations` | Narrative content, service pillars, sectors |
| `Pipeline_Revenue` | Active proposals, monthly revenue ramp |
| `Sales_Performance` | Sales KPI card inputs, funnel, probability |
| `Sales_Raw_Opportunities` | Detailed proposals table |
| `Sales_Raw_Operations` | Operations readiness table |
| `Sales_Stage_Details` | Client-level month/week detail |

## Deployment
### Vercel (recommended)
1. Push this repo to GitHub
2. Import in [Vercel](https://vercel.com)
3. Deploy — no build step needed (static site)

### Manual
Serve the folder with any static file server:
```bash
npx serve .
```

## Features
- 🌙 Dark / Light theme toggle
- 📊 5 dashboard tabs: Financial, Cash Flow, Strategy, Pipeline, Sales
- 📈 Chart.js visualizations
- 🔄 Refresh button re-reads Excel file
- 📱 Responsive layout
