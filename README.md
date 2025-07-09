# 🌍 World Happiness Report 2015

This project analyzes and visualizes the **2015 World Happiness Report** using Power BI and Python. It explores how happiness scores vary across countries and regions based on economic, health, and social factors.

## 📊 Dashboard Preview

![Dashboard](World%20Happiness%20Dashboard%20-%202015%20.png)

## 🧠 Project Overview

- **Goal:** Understand what factors contribute to happiness at the country and regional levels using the 2015 dataset.
- **Data Source:** [World Happiness Report 2015 – Kaggle](https://www.kaggle.com/datasets/unsdsn/world-happiness) — provided by the United Nations Sustainable Development Solutions Network.
- **Tools Used:**
  - Python (Pandas for cleaning and aggregating data)
  - Power BI (for dashboard design and interactivity)
  - Git & GitHub (for version control and publishing)

## 🗺️ Map Visualization Logic

The interactive map visual in this dashboard was thoughtfully designed to give an intuitive understanding of regional happiness levels:

- **Bubble Size** is based on an **inverted happiness ranking**.  
  This means countries with higher happiness (i.e., lower rank numbers) appear as **larger bubbles**, making it easier to spot positive trends at a glance.

- This was accomplished by creating a calculated DAX measure that inverts the `happiness_rank` values:

  ```DAX
  HappinessRank_Inverted = 
    MAXX(ALL('world_happiness_2015_cleaned'[happiness_rank]), 'world_happiness_2015_cleaned'[happiness_rank]) 
    + 1 
    - 'world_happiness_2015_cleaned'[happiness_rank]
  ```

- **Tooltips** were customized to provide additional insights when hovering over a region. These include:
  - Average happiness score
  - Economy (GDP per capita)
  - Health (Life expectancy)
  - Freedom, Trust, and Generosity scores

Together, these enhancements make the map both visually engaging and analytically valuable for exploring how different factors relate to global happiness.

## 📂 Files Included

| File | Description |
|------|-------------|
| `2015.csv` | Raw dataset from Kaggle |
| `world_happiness_2015_cleaned.csv` | Cleaned version of the dataset |
| `world_happiness_2015_region_summary.csv` | Summary statistics grouped by region |
| `World Happiness Report.ipynb` | Data cleaning & analysis notebook |
| `World Happiness Dashboard - 2015.png` | Final dashboard image |
| `.pbix` file (optional) | Power BI dashboard file (if included)

## 📦 How to Use

1. Clone the repository  
   ```bash
   git clone git@github.com:yourusername/world-happiness-report-2015.git
   ```

2. Open the Jupyter notebook to view data preparation  
   ```
   World Happiness Report.ipynb
   ```

3. View the Power BI dashboard via the included PNG or recreate it using the CSV files in Power BI.

## 📈 Key Insights

- Western Europe, North America, and Australia lead in average happiness scores.
- Sub-Saharan Africa and Southern Asia consistently fall below global averages.
- Factors like GDP per capita and life expectancy show a strong correlation with happiness scores.
  
### 💰 Wealth vs. Happiness (2015)
There is a strong positive correlation between GDP per capita and happiness scores across countries. As economic prosperity increases, average happiness also tends to rise.

![Wealth vs Happiness (2015)](./Wealth%20vs%20Happiness%20(2015).png)

---

### 🧬 Life Expectancy vs. Happiness (2015)
Countries with higher life expectancy also report higher happiness scores. This suggests that access to healthcare and longer lives are linked to greater national well-being.

![Life Expectancy vs Happiness (2015)](./Life%20Expectancy%20vs%20Happiness%20(2015).png)

## ✅ Credits

[World Happiness Report 2015 – Kaggle](https://www.kaggle.com/datasets/unsdsn/world-happiness)  
Provided by the United Nations Sustainable Development Solutions Network.
