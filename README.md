# Hi, I'm Jack 👋

### 📊 Data Analyst | Turning Data into Actionable Insights

I'm a data analyst passionate about transforming raw data into **clear insights, meaningful visualisations, and data-driven decisions**.

I enjoy exploring datasets, identifying trends, solving business problems, and communicating findings in a way that makes complex information easy to understand.

## 😂 Daily Data Joke

<!-- DAILY_JOKE_START -->
> Loading today's data joke...
<!-- DAILY_JOKE_END -->

name: 😂 Daily Data Joke

on:
  schedule:
    - cron: "0 9 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  joke:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Update joke
        run: |
          python <<'PY'
          import random
          from pathlib import Path

          jokes = [
              "Why did the data analyst break up with Excel? Because it wasn't giving them enough space. 📊",
              "I told my SQL query a joke... It didn't return any results. 😂",
              "Why do data analysts love coffee? Because they need to keep their queries running. ☕",
              "My dataset and I have a lot in common... We're both full of issues. 😅",
              "Why was the database administrator so calm? They knew how to handle the transactions. 😎",
              "I asked Python to analyse my dataset. It said, 'Pandas can do that.' 🐼",
              "Why did the data scientist bring a ladder? To reach a higher dimension. 📈",
              "My Power BI dashboard walked into a bar... It had too many visualisations. 🍻",
              "Why did the analyst go broke? They kept spending all their time on the data. 💸",
              "SQL and I have a great relationship... It's based on strong joins. ❤️",
              "What does a data analyst eat for breakfast? Cereal correlations. 🥣",
              "Why did the analyst stare at the spreadsheet for hours? They were trying to find the missing cell-f-esteem. 😂"
          ]

          joke = random.choice(jokes)

          readme = Path("README.md")
          content = readme.read_text()

          start = "<!-- DAILY_JOKE_START -->"
          end = "<!-- DAILY_JOKE_END -->"

          replacement = f"{start}\n> {joke}\n{end}"

          start_pos = content.index(start)
          end_pos = content.index(end) + len(end)

          content = content[:start_pos] + replacement + content[end_pos:]

          readme.write_text(content)
          PY

      - name: Save joke
        run: |
          git config user.name "github-actions[bot]"
          git config user.email "41898282+github-actions[bot]@users.noreply.github.com"
          git add README.md
          git diff --cached --quiet || git commit -m "😂 Update daily data joke"
          git push


---

## 🛠️ Data Analytics Toolkit

### 🐍 Programming & Data Analysis

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

### 🗄️ Databases & SQL

- SQL
- Data querying
- Joins
- CTEs
- Subqueries
- Window Functions
- Aggregations

### 📊 Business Intelligence & Visualisation

- Power BI
- DAX
- Data Modelling
- Tableau
- Interactive Dashboards
- Data Storytelling

### 📈 Excel

- PivotTables
- XLOOKUP
- Power Query
- Data Cleaning
- Dashboard Development

---

## 💡 Data Analysis Skills

- 🔍 Exploratory Data Analysis (EDA)
- 🧹 Data Cleaning & Transformation
- 📊 Statistical Analysis
- 📈 Trend & Pattern Analysis
- 🎯 KPI & Performance Analysis
- 🔗 Data Modelling
- 💼 Business Intelligence
- 📋 Reporting & Dashboard Development
- 💬 Data Storytelling
- 💡 Data-Driven Decision Making

---

## 🚀 What I Do

- Clean, transform, and validate raw datasets
- Use SQL to extract meaningful business insights
- Perform exploratory data analysis to identify trends and patterns
- Build interactive Power BI dashboards
- Analyse KPIs and business performance
- Automate repetitive data analysis tasks using Python
- Translate complex data into clear, actionable insights
- Present findings to technical and non-technical audiences

