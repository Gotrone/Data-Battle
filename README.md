# Data Battle 2024 – Matching needs to energy-saving solutions

Team project for the 2024 Data Battle (CY Tech × Kerdos Energy): given a free-text description of an industrial need, recommend the most relevant energy-efficiency solutions from a technology catalogue.

## Approach

1. **Text cleaning** – strip HTML/CSS, lemmatize with spaCy (French model), remove stop words and punctuation.
2. **Vectorization** – TF-IDF representation of the catalogue entries and of the user query.
3. **Ranking** – cosine similarity between the query and each solution; the top matches are returned.
4. **Footprint tracking** – energy consumption of the pipeline measured with CodeCarbon.

## Contents

| File | Description |
|---|---|
| `projet_f.py` | Command-line pipeline: cleaning, TF-IDF, similarity ranking. |
| `Projet.ipynb` | Exploration and prototyping notebook. |
| `prompt.php` | Minimal web search form. |
| `tbldictionnaire.csv`, `tblsolution.csv`, `tbltechno.csv` | Extracts of the catalogue tables used by the pipeline. |

## Run

```bash
pip install pandas scikit-learn spacy beautifulsoup4 codecarbon mysql-connector-python
python -m spacy download fr_core_news_sm
python projet_f.py
```

## Tech stack

Python · spaCy · scikit-learn (TF-IDF, cosine similarity) · pandas · CodeCarbon · MySQL · PHP
