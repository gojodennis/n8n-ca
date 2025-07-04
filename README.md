# 🧠 Creative Agency Ad Spinning Automation (n8n)

A full-stack ad analysis and creative generation workflow powered by n8n, OpenAI, and Apify. Scrapes Facebook ads, rewrites them using LLMs, generates visual variants, stores creatives in Google Drive, and logs everything in Google Sheets.

---

## 📌 What It Does

- Scrapes **active Facebook ads** using [Apify](https://apify.com)
- Downloads and analyzes ad images
- Uses **OpenAI GPT-4 & GPT-4o** to:
  - Describe visuals
  - Generate multiple creative rewrites (prompt spinning)
- Sends prompts to **DALL·E / GPT Image Editor** for image remixing
- Uploads all creatives to **Google Drive**, organized into folders
- Logs metadata to **Google Sheets**

---

## 🧩 Integrations

- **Apify** – Facebook Ads Library Scraper
- **OpenAI (GPT-4 / GPT-4o)** – Prompt generation + image analysis
- **OpenAI Image API** – Generates creative variants
- **Google Drive** – Asset management
- **Google Sheets** – Logging + tracking

---

## 🚀 How It Works

[Manual Trigger]
↓
[Apify: Facebook Ads Scraper]
↓
[Filter & Limit Results]
↓
[Download Ad Images]
↓
[Analyze with GPT-4o → Generate Change Prompts → Create Variants]
↓
[Generate Images (OpenAI DALL·E)]
↓
[Upload Assets to Google Drive]
↓
[Log to Google Sheets]


---

## 🧰 Requirements

- Apify API Token
- OpenAI API Key (GPT-4 & Image)
- Google OAuth Credentials for:
  - Google Drive
  - Google Sheets
- n8n (self-hosted or Cloud)

---

## 📁 Folder Structure (Drive)

- `/Creative Agency`
  - `1. Source Assets/`
  - `2. Spun Assets/`
- Each ad batch gets its own parent folder

---

## 🗂 Spreadsheet Columns

Logged to the `scraped_ads` sheet:
- `timestamp`
- `ad_archive_id`
- `page_id`
- `page_name`
- `original_image_url`
- `ad_body`
- `date_scraped`
- `spun_prompts`
- `asset_folder`
- `source_folder`
- `spun_folder`
- `direct_spun_image_link`

---

## 🛠 Setup

1. Clone this repo
2. Import `Creative agency.json` into n8n
3. Set up credentials:
   - **Apify**: Insert token in HTTP Request headers
   - **OpenAI**: Connect GPT and Image APIs
   - **Google Drive/Sheets**: Use OAuth2 credentials
4. Replace static IDs:
   - `spreadsheetId`
   - `googleDriveFolderId`

---

## 🧪 Optional Enhancements

- Add email/Slack output for sharing creatives
- Trigger on a schedule or webhook
- Auto-run on new ads using Apify scheduling

---

## 📜 License

MIT.  

---
