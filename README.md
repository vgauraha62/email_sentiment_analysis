# 💼 Employee Email Sentiment Analysis

This project analyzes employee email messages to evaluate sentiment and engagement patterns. It is structured to meet all the tasks outlined in the internal evaluation document (`Project_details.docx`), including sentiment labeling, EDA, scoring, flight risk analysis, and predictive modeling using linear regression.

---

## 📁 Project Structure

```
The_email_sentiment_analysis_project/
│
├── test.csv                            # Raw input data (unlabeled)
├── The_email_sentiment_analysis_project.ipynb  # Main analysis notebook
├── Final_Report.docx                   # Summary report with methodology and findings
├── README.md                           # Project description and documentation
└── visualization/                      # Charts and visuals for EDA, rankings, word clouds
    ├── sentiment_distribution.png
    ├── positive_wordcloud.png
    ├── negative_wordcloud.png
    ├── neutral_wordcloud.png
    ├── top_positive.csv
    ├── top_negative.csv
    └── flight_risks.csv
```

---

## ✅ Workflow Overview

### 🔹 1. **Sentiment Labeling**
- Used VADER (from `nltk.sentiment`) for sentiment classification.
- Messages labeled as `Positive`, `Negative`, or `Neutral` based on compound score.
- Output: A new `sentiment` column in the DataFrame.

---

### 🔹 2. **Exploratory Data Analysis (EDA)**
- Checked for missing values, message lengths, and sentiment distribution.
- Created visualizations:
  - **Sentiment distribution bar plot**
  - **Word clouds** for all three sentiment types.
- Output saved in `visualization/`.

---

### 🔹 3. **Employee Monthly Sentiment Score**
- Scores mapped: `+1` for Positive, `-1` for Negative, `0` for Neutral.
- Grouped by employee and month to compute **monthly sentiment scores**.

---

### 🔹 4. **Employee Ranking**
- Ranked employees by score per month.
- Extracted:
  - **Top 3 Positive Employees**
  - **Top 3 Negative Employees**
- Sorted alphabetically in case of tie.
- Output saved as:
  - `visualization/top_positive.csv`
  - `visualization/top_negative.csv`

---

### 🔹 5. **Flight Risk Identification**
- Flagged employees who sent **4+ negative messages within any 30-day window**.
- Rolling window applied per employee.
- Output saved to: `visualization/flight_risks.csv`

---

### 🔹 6. **Predictive Modeling**
- Built a **linear regression model** using:
  - Message count
  - Average message length
- Target: Monthly sentiment score
- Output: R² Score and analysis in notebook.
- Model helps quantify and forecast engagement trends.

---

## 📊 Key Visuals (in `/visualization`)
- `sentiment_distribution.png`
- `positive_wordcloud.png`
- `negative_wordcloud.png`
- `neutral_wordcloud.png`
- `top_positive.csv` (Top 3 most positive employees monthly)
- `top_negative.csv` (Top 3 most negative employees monthly)
- `flight_risks.csv` (Flagged employees for potential attrition)

---

## 💡 Highlights

| Task                          | Implemented | Output Generated |
|-------------------------------|-------------|------------------|
| Sentiment Labeling            | ✅          | `score`, `sentiment` columns |
| EDA + Visuals                 | ✅          | Word clouds, distribution chart |
| Monthly Sentiment Score       | ✅          | `monthly_score` DataFrame |
| Employee Ranking              | ✅          | `top_positive.csv`, `top_negative.csv` |
| Flight Risk Detection         | ✅          | `flight_risks.csv` |
| Predictive Modeling (Linear)  | ✅          | Regression results, R² Score |

---

## 🔁 Reproducibility

To reproduce this analysis:
1. Place `test.csv` in the root folder.
2. Open `The_email_sentiment_analysis_project.ipynb`.
3. Run all cells.
4. All output files and visualizations will be saved automatically.

---

## 📬 Submission Notes

- Do not share this project publicly. This is an **internal evaluation**.
- Complies fully with `Project_details.docx`.
- For questions, contact the project mentor via Microsoft Teams.
