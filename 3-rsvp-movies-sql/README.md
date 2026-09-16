# RSVP Movies — SQL Data Analysis

**Tools:** MySQL

---

## Context

RSVP Movies is an Indian production house planning a global movie release in 2022. They need data-driven insights from 3 years of IMDB movie data to guide decisions on genre selection, director and actor hiring, and production partner choice.

---

## Database Schema

6 related tables:

| Table | Description |
|-------|-------------|
| `movie` | Core movie data — title, year, duration, country, gross income |
| `genre` | Genre classifications per movie |
| `ratings` | IMDB ratings, median rating, total votes |
| `names` | Directors and actors — name, DOB, known movies |
| `director_mapping` | Movie ↔ director relationships |
| `role_mapping` | Movie ↔ actor/actress relationships with category |

---

## Analysis Scope — 29 Business Questions Answered

### Segment 1: Movie & Genre Analysis
- Total rows per table; null value audit
- Movies by year and month-wise trend
- USA/India movie production count (2019)
- Genre distribution; single-genre movies count
- Average movie duration by genre
- Thriller genre ranking

### Segment 2: Ratings Analysis
- Min/max values in ratings table
- Top 10 movies by average rating
- Movie count by median rating
- Production house with most hit movies (avg rating > 8)
- Movies by genre, country, and votes (March 2017, USA, >1000 votes)
- Movies titled 'The*' with avg rating > 8
- German vs. Italian movie votes comparison

### Segment 3: Director & Actor Analysis
- Null value audit on names table
- Top 3 directors per top 3 genres (avg rating > 8)
- Top 2 actors by movie count with median rating ≥ 8
- Top 3 production houses by total votes
- Top actors in Indian movies (weighted avg rating, min 5 movies)
- Top 5 Hindi-movie actresses (min 3 movies)
- Thriller movie classification: Superhit / Hit / One-time-watch / Flop

### Segment 4: Advanced Analysis
- Genre-wise running total and moving average of duration
- Top 5 highest-grossing movies per year per top 3 genres
- Top 2 production houses for multilingual hit movies
- Top 3 actresses in Drama genre superhits
- Top 9 directors: full profile with inter-movie days, avg/min/max rating, total votes

---

## SQL Techniques Used

- `JOIN` (INNER, LEFT) across 4+ tables
- Common Table Expressions (`WITH ... AS`)
- Window functions: `RANK()`, `DENSE_RANK()`, `ROW_NUMBER()`, `LEAD()`
- Aggregate functions: `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`
- Conditional aggregation: `CASE WHEN`
- Date functions: `MONTH()`, `DATEDIFF()`, `EXTRACT()`
- String functions: `LOWER()`, `LIKE`, `POSITION()`
- Subqueries and nested filters

---

## Files

| File | Description |
|------|-------------|
| `RSVP_Movies_Analysis.sql` | Complete SQL script with all 29 questions, solutions, and commentary |

---

## How to Run

1. Import the IMDB database schema and data into MySQL
2. Run `USE imdb;` to select the database
3. Execute queries in `RSVP_Movies_Analysis.sql` sequentially
