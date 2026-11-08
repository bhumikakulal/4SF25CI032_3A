# Video Game Sales Analysis

## Overview
This project analyzes a dataset of video game sales using Python and Pandas. It covers reading the data, understanding its structure, transforming it, handling null values with mean imputation, generating insights and visualizing them.

The dataset has **16,598 games** and 11 columns: `Rank`, `Name`, `Platform`, `Year`, `Genre`, `Publisher`, `NA_Sales`, `EU_Sales`, `JP_Sales`, `Other_Sales` and `Global_Sales`. Sales are in millions of copies.

## Dataset
Video Game Sales (Kaggle): https://www.kaggle.com/datasets/gregorut/videogamesales

File used: `vgsales.csv`

## Files in this Repository
| File | Description |
|------|-------------|
| `videogame_sales_analysis.ipynb` | Python notebook with all the code and outputs |
| `vgsales.csv` | Dataset used for the analysis |
| `README.md` | Project overview |

## Steps Performed
1. **Reading the data:** loaded `vgsales.csv` using Pandas.
2. **Understanding the data:** checked the shape, info, summary statistics, column names, data types and the unique genres (12) and platforms (31).
3. **Data transformation:**
   - Dropped the `Rank` column because it is not needed for the analysis.
   - Found and removed 1 duplicate row (16,598 rows became 16,597).
   - Created filtered datasets for **Action** games (3,316 games) and **Nintendo** games (702 games).
4. **Handling null values:**
   - `Year` had 270 null values. They were filled with the mean year and stored in a new column `Year_mean`. The original `Year` column was kept for the yearly trend.
   - `Publisher` had 58 null values. It is a text column, so the mean cannot be used, and those rows were left as they are.
   - The sales columns had no null values.
5. **Insights and visualization:** the insights below are shown with bar charts, a histogram, a scatter plot and a correlation heatmap.

## Insights Covered
- Number of games in each genre and on each platform
- Average global sales of a game in each genre and on each platform
- Region-wise sales (North America, Europe, Japan, Other)
- Sales trend over the years (average global sales by release year)
- Distribution of global sales
- North America sales vs Europe sales
- Correlation between the sales columns
- Genres of Nintendo games

## Key Findings
- **Most common genres:** Action has the most games (3,316), followed by Sports (2,346) and Misc (1,739).
- **Most common platforms:** DS (2,163 games) and PS2 (2,161 games) have the most games.
- **Best selling genres per game:** Platform games average the highest global sales (about 0.94 million), followed by Shooter (about 0.79 million). Adventure games average the lowest (about 0.19 million).
- **Best selling platforms per game:** GB (about 2.61 million) and NES (about 2.56 million) have the highest averages, but each has only 98 games in the dataset.
- **Regions:** North America has the highest average sales per game (about 0.26 million), then Europe (0.15 million), Japan (0.08 million) and Other regions (0.05 million).
- **Trend over the years:** average sales per game were high and varied in the 1980s and early 1990s (peaking at about 4.3 million in 1989). From the 2000s they stay mostly between 0.4 and 0.7 million, and they fall after 2015.
- **Correlation:** `NA_Sales` (0.94) and `EU_Sales` (0.90) are the most strongly related to `Global_Sales`, while `JP_Sales` is lower (0.61).
- **Nintendo:** Platform (112), Role-Playing (106) and Misc (100) are the most common genres among its 702 games.

## Tools Used
- Python
- Pandas
- Seaborn
- Matplotlib
