# 🔮 Predicting Job Industries from Job Postings
---
## Why this project?
Job descriptions are full of clues. Tech roles say “API,” “Python,” “agile.” Customer service talks “assist,” “clients,” “tickets.” I wanted to see how far a simple, transparent pipeline (clean → tokenize → TF-IDF → classify) could go in sorting jobs into industries.
## Questions I wanted to answer
- Can we classify job postings into industries using text and metadata?

- Which industries are easiest (or hardest) to distinguish?

- Which models work best for this kind of task?

## Data
- Size: ~98,913 rows × 27 columns

- Features: job title, description, country, language, and metadata

- Target: industry category
<img width="2098" height="826" alt="image" src="https://github.com/user-attachments/assets/ce3daf43-9ad7-4697-8ec3-98be7121d295" />

The dataset was messy: inconsistent categories, missing values, long free-text fields. That made it a good challenge for data wrangling and NLP preprocessing.

## Data Cleaning (NLP Prep)
- Fix camelCase spacing: r'([a-z])([A-Z])' → '\1 \2'

- Lowercase, strip URLs & punctuation

- Remove stopwords (nltk.corpus.stopwords)

- Create sig_description for modeling

*Why*: reduces noise so TF-IDF focuses on meaning-bearing terms.
