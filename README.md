# Bechdel-Test Analysis of Oscar-Nominated Films
![Bechdel Test](https://upload.wikimedia.org/wikipedia/en/b/bf/Dykes_to_Watch_Out_For_%28Bechdel_test_origin%29.jpg)

## Overview

This project automates the evaluation of the Bechdel Test on 20 Oscar-nominated films by integrating web scraping, relational database design and script-level textual analysis.

The objective is to quantify gender representation in film dialogue and assess structural inequalities using reproducible computational methods.

The Bechdel Test requires that a film:
1. Has at least two named female characters  
2. Includes at least one scene where they talk to each other  
3. The conversation is not about a man  

The analysis moves beyond manual evaluation by applying automated database-driven checks on full movie scripts.

---

## Dataset Construction

A structured relational database was built from multiple sources:

### Data Sources
- IMSDB – Movie scripts
- IMDb – Cast information
- Names Dataset Library – Gender inference
- External validation (Wikipedia + Bechdel Test forum)

### Dataset Statistics

- 20 films analyzed
- 3012 scenes extracted
- 876 actors
- 3 relational tables:
  - MOVIE
  - SCRIPT
  - CAST

An SQLite database was designed with primary/foreign key relationships to ensure referential integrity and efficient querying.

---

## Data Processing

### Script Parsing
- Scene segmentation using INT/EXT markers
- Uppercase token analysis to detect speakers
- Lowercase dictionary analysis to detect male mentions
- Text cleaning (HTML removal, punctuation normalization)

### Cast Cleaning
- Role standardization
- Removal of uncredited characters
- Elimination of ambiguous roles (e.g., “The Doctor”)
- First-name probabilistic gender inference

### Data Quality Controls
- Cross-validation with external sources
- Manual resolution of inconsistencies
- Referential integrity enforcement

---

## Analytical Framework

The Bechdel evaluation was implemented through SQL queries applied to the relational database.

### Results

Out of 20 films:

- 20 pass Level 1 (100%)
- 12 pass Level 2 (60%)
- 8 pass all three levels (40%)

Additional findings:

- 71% of cast members are male
- Men appear in scenes 2.1× more often than women
- 77% of scenes include a male character as subject or mention
- 70% of Level-3-passing scenes occur in indoor settings

The percentage of “Bechdel-friendly” scenes across full scripts remains consistently low.

---

## Technical Stack

- Python
- BeautifulSoup (web scraping)
- SQLite
- SQL queries
- NLP preprocessing
- Names Dataset Library

---

## Key Insights

- Gender imbalance is measurable at script level.
- Passing the Bechdel Test often depends on isolated scenes.
- Female characters are frequently defined relationally (e.g., wife, mother).
- Automated evaluation exposes structural patterns invisible in manual summaries.

---

## Authors

Daniele Lepre  
Alice Anna Maria Brunazzi  
Alessandro Della Beffa
