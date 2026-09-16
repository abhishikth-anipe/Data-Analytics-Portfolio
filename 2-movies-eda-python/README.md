# Movies Dataset EDA — Python

**Tools:** Python | Pandas | NumPy | Matplotlib | Jupyter Notebook

---

## Dataset

- **Source:** IMDB movies dataset
- **Size:** 5,043 movies (1916–2016), 28 columns
- **Key attributes:** Director, actors, gross revenue, budget, IMDB score, genres, number of votes, Facebook likes

---

## Objectives

Perform end-to-end exploratory data analysis to identify:
- The most profitable movies of all time
- IMDb's top 250 films (with vote threshold)
- The best-rated directors
- Most profitable genre combinations
- Audience vs. critic favourites among top Hollywood actors

---

## Work Done

### Data Cleaning
- Detected null values column-wise and row-wise; calculated null percentages
- Dropped 15 irrelevant columns (Facebook likes, poster features, aspect ratio, etc.)
- Removed rows with >5% null rates in key financial columns (gross, budget)
- Filled remaining language nulls with 'English' (dominant value)
- Removed duplicate rows
- **Retained 3,891 rows (77.2% of original dataset)**

### Analysis
| Task | Insight |
|------|---------|
| Top 10 by profit | Avatar leads with $523M profit; Titanic, The Dark Knight in top 10 |
| IMDb Top 250 | Filtered by score + 25,000+ votes; extracted non-English films separately |
| Best directors | Charles Chaplin and Tony Kaye tie at 8.6 avg rating; Christopher Nolan at 8.4 |
| Popular genres | Family + Sci-Fi highest avg gross ($435M); Action + Adventure strong at $110M |
| Actor comparison | Leonardo DiCaprio leads in both critic reviews (330 avg) and user reviews (914 avg) vs. Brad Pitt and Meryl Streep |

---

## Files

| File | Description |
|------|-------------|
| `Movies_EDA.ipynb` | Jupyter notebook with full analysis, code, and outputs |

---

## How to Run

```bash
pip install pandas numpy matplotlib jupyter
jupyter notebook Movies_EDA.ipynb
```
