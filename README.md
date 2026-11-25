# 🛒 n8n E-Commerce Product Enrichment & Catalog Sync

An automated AI-powered workflow built with **n8n**, **Google Gemini / OpenAI**, and **Google Sheets** that enriches raw e-commerce product lists with standardized SKUs, SEO-optimized descriptions, categories, and tags before syncing to storefronts (such as WooCommerce/Shopify/Takealabor).

## 🚀 Problem Solved
E-commerce teams spend hours manually writing product descriptions, formatting SKUs, and researching SEO tags for bulk supplier spreadsheets. This workflow automates the entire enrichment pipeline with zero manual copy-pasting.

## ⚙️ Workflow Architecture
1. **Trigger:** Watches a Google Sheet for newly added product rows with missing attributes.
2. **AI Enrichment Node:** Sends raw product title and basic specs to an LLM (Gemini/OpenAI) with structured prompt rules to generate:
   - Standardized SKU code (`CAT-BRAND-XXX`)
   - High-converting product description
   - Clean category mapping & comma-separated SEO tags
3. **Data Validation & Update:** Updates the matching row in Google Sheets using `matchingColumns` (`Product_ID` / `Title`) to prevent duplicates.
4. **Storefront Sync:** Pushes enriched product payloads via REST API / Webhook to the e-commerce catalog.

## 📂 Repository Contents
- `workflow.json` – Exportable n8n workflow template ready to import.
- `sample_products.csv` – Sample input dataset for testing.

## 🛠️ How to Use
1. Open your **n8n** instance (Cloud or Self-Hosted Docker).
2. Click **Add Workflow** > **Import from File** and select `workflow.json`.
3. Connect your **Google Sheets** and **Gemini/OpenAI** credentials.
4. Activate the workflow and add a new product row to test automatic enrichment.
