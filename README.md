# 🧠 Web Article Sentiment Analyzer

> 📊 A complete pipeline for scraping web articles, performing sentiment and readability analysis, and exporting results to Excel.

---

## 📌 Overview

This project automates the process of:
1. **Scraping** content from URLs using Playwright.
2. **Analyzing** text for sentiment and readability using NLTK-based NLP techniques.
3. **Generating** structured output with various metrics such as:
   - Positive/Negative scores
   - Subjectivity/Polarity
   - Readability scores (Fog Index, Avg. Sentence Length, etc.)

All you need is a list of article URLs in Excel format!

---

## 🧰 Tech Stack

- 🐍 Python 3.9+
- 📜 NLTK
- 🕸️ Playwright
- 📈 Pandas
- 📁 Excel I/O

---

## 🗂️ Project Structure

```bash
📦project_root
├── main_execution.py         # 🚀 Main pipeline execution script
├── web_scraper.py            # 🌐 Scrapes web articles
├── text_analysis.py          # 🧠 Performs sentiment and readability analysis
├── config.py                 # ⚙️ Configuration and directory setup
├── Input.xlsx                # 📥 Input URLs (with URL_ID and URL columns)
├── Output.xlsx               # 📤 Final results (auto-generated)
├── extracted_texts/          # 📄 Scraped text content
├── StopWords/                # ❌ Stop words text files
├── MasterDictionary/         # 🟢 Positive and 🔴 Negative word lists
```

---

## ✅ Requirements

Install Python 3.9+ and then install the following dependencies:

```bash
pip install pandas nltk openpyxl playwright
python -m playwright install
```

Additionally, NLTK resources are automatically downloaded on the first run.

---

## ▶️ How to Run

### Step 1: Prepare Input
Add URLs in an Excel file `Input.xlsx` with the following columns:
- `URL_ID` — Unique ID for each article
- `URL` — Full article URL

### Step 2: Run the Pipeline

```bash
python main_execution.py
```

This will:
1. Optionally scrape articles (uncomment the scraper section in `main_execution.py` if needed).
2. Analyze text files in the `extracted_texts/` folder.
3. Generate `Output.xlsx` with results.

---

## 📊 Output Features

Each analyzed article will have:
- `positive_score`, `negative_score`
- `polarity_score`, `subjectivity_score`
- `average_sentence_length`, `percentage_of_complex_words`
- `fog_index`, `syllables_per_word`
- `personal_pronouns`, `avg_word_length`
- And more...

---

Run analysis:
```bash
python main_execution.py
```

---

## 💡 Notes

- Ensure `StopWords` and `MasterDictionary` folders are populated with appropriate `.txt` files (e.g., `positive-words.txt`, `negative-words.txt`, etc.).
- Scraping is based on typical article structures, but may need adjustment for non-standard websites.

---

## 📄 License

This project is open-source and free to use under the MIT License.
