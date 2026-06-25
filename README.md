# 🎮 CodeAlpha Steam Analytics

![CodeAlpha Badge](https://img.shields.io/badge/Internship-CodeAlpha-blue)
![Data Analytics](https://img.shields.io/badge/Domain-Data_Analytics-success)
![Python](https://img.shields.io/badge/Python-3.9+-yellow)

## 📌 Project Overview

**Data Analytics** internship project at CodeAlpha — building a simple End-to-End Data Pipeline to analyze player reviews on Steam.

**Topic:** Player reviews for the **Resident Evil** series on Steam.

The pipeline consists of 4 stages:

| Task | Description | Notebook |
|------|-------------|----------|
| 1 | Web Scraping — Collect reviews from Steam API | `01_web_scraping.ipynb` |
| 2 | EDA — Data cleaning & exploratory analysis | `02_eda_analysis.ipynb` |
| 3 | Visualization — Visualize insights | `03_visualization.ipynb` |
| 4 | Sentiment Analysis — NLP sentiment analysis | `04_sentiment_analysis.ipynb` |

---

## 🛠️ Tech Stack

- **Python 3.9+**
- `requests` — Call Steam Web API
- `pandas`, `numpy` — Data processing
- `matplotlib`, `seaborn` — Visualization
- `nltk` (VADER) — Sentiment analysis
- `wordcloud` — Word Cloud visualization
- `Jupyter Notebook` — Development environment

---

## 🚀 How to Run

### 1. Environment Setup

```bash
# Create and activate virtual environment (recommended)
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/macOS
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 2. Run in Order

```bash
cd notebooks
jupyter notebook
```

Run sequentially:
1. `01_web_scraping.ipynb` → creates `data/raw_steam_data.csv`
2. `02_eda_analysis.ipynb` → creates `data/clean_steam_data.csv`
3. `03_visualization.ipynb` → view charts directly in the notebook
4. `04_sentiment_analysis.ipynb` → NLP analysis results

> ⚠️ **Note:** Task 1 may take **20–40 minutes** due to Steam API rate limits (1 request/second). A maximum of 500 reviews is collected per game.

---

## 📂 Repository Structure

```text
CodeAlpha_DataAnalytics/
│
├── data/
│   ├── raw_steam_data.csv       # Output Task 1 (Web Scraping)
│   ├── raw_games_info.csv       # Detailed game info
│   └── clean_steam_data.csv     # Output Task 2 (EDA)
│
├── notebooks/
│   ├── 01_web_scraping.ipynb    # Task 1: Data collection
│   ├── 02_eda_analysis.ipynb    # Task 2: EDA & data cleaning
│   ├── 03_visualization.ipynb   # Task 3: Visualization
│   └── 04_sentiment_analysis.ipynb  # Task 4: NLP analysis
│
├── README.md
└── requirements.txt
```

---

## 📊 Expected Results

- **~3,500 reviews** from 7 Resident Evil games
- Detect **review bombing** over time
- **Word Cloud** charts of positive / negative keywords
- **Accuracy** of VADER vs. actual Steam labels

---

## 📋 Data Sources

- [Steam Store API](https://store.steampowered.com/api/appdetails)
- [Steam Review API](https://store.steampowered.com/appreviews/{appid}?json=1)
- Public data, no API key required
