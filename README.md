# Emotional Framing in Netflix Descriptions with Python

A Python course project exploring how emotional language in Netflix movie and TV show descriptions differs by format, genre and year of addition.

**Author:** Kristian Roncero · [GitHub portfolio](https://github.com/roncerok)

## Project overview

This project uses word matching against emotion lexicons to compare short catalogue descriptions. It analyses the language used to describe titles—not audience reactions or the emotional content of the films and series themselves.

The notebook preserves the exploratory process: initial observations, data-quality checks, revisions to genre grouping, changes to the analysis period and the reasoning behind the final comparisons.

**[Read the analysis notebook](python_emotional_framing.ipynb)**

## Questions

- How do emotion profiles differ between movies and TV shows?
- Which emotional patterns distinguish the main genre families?
- How do average emotion profiles compare across titles added between 2017 and 2021?

## Main findings

- TV show descriptions show somewhat higher rates of trust, joy and anticipation; movie descriptions show higher rates of fear, sadness, anger and disgust.
- The observed differences between genres are larger than those between formats. Horror, Crime, Thriller and Action & Adventure tend towards more fear-related language, lower valence and higher arousal relative to the sample average.
- Average emotion rates and VAD scores remain broadly stable across the 2017–2021 addition-year groups. This descriptive comparison does not establish whether external events affected Netflix's catalogue or writing practices.

## Approach

1. **Audit the data:** check missing values, duplicate identifiers, lexicon entries, date formats and description lengths.
2. **Prepare the sample:** parse addition dates, exclude ten titles with missing addition dates and 138 titles added before 2016, leaving 8,659 titles for format and genre comparisons.
3. **Group genres:** split multi-label categories, combine related movie and TV labels, and remove duplicate genre assignments within each title. Genre comparisons include groups with at least 200 titles.
4. **Score descriptions:** tokenise the text and count repeated word occurrences. Express the eight emotion counts per 100 words and calculate mean valence, arousal and dominance (VAD) scores across matched word occurrences.
5. **Compare groups:** average the per-description scores by format, genre and addition year. The time comparison uses 2017–2021; 2021 covers January–September only.
6. **Check interpretation:** compare description lengths and lexicon coverage across groups.

## Tools and skills

**Python · pandas · NumPy · regular expressions · Plotly · Matplotlib · Jupyter notebooks**

The project demonstrates data-quality auditing, date parsing, text preparation, multi-label category mapping, normalisation, grouped reporting and interpretation of analytical limitations.

## Data and attribution

Both CSV files were supplied through my course.

- **Netflix titles:** the supplied file contains 8,807 records and 12 columns. The corresponding public dataset is [Netflix Movies and TV Shows, published by Shivam Bansal on Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows). The original course download/version was not recorded. Consult the source page for its current licence and download information.
- **Emotion lexicon:** the course supplied a combined `emotion_lexicon.csv` containing columns from NRC EmoLex and NRC VAD, along with additional derived columns. The exact versions and preparation procedure for this combined file were not documented in the supplied materials.

This project makes use of:

- [NRC Word–Emotion Association Lexicon (EmoLex)](https://saifmohammad.com/WebPages/NRC-Emotion-Lexicon.htm), created by Saif M. Mohammad and Peter D. Turney at the National Research Council Canada. Reference: *Crowdsourcing a Word–Emotion Association Lexicon* (2013).
- [NRC Valence, Arousal and Dominance Lexicon](https://saifmohammad.com/WebPages/nrc-vad.html), created by Saif M. Mohammad at the National Research Council Canada. Reference: *Obtaining Reliable Human Ratings of Valence, Arousal, and Dominance for 20,000 English Words* (2018).

The NRC lexicon data are not included because their terms prohibit redistribution. Obtain them through the official resource pages and follow their terms of use. Third-party data retain their own terms and are not covered by any licence applied to this project's code.

## Running the notebook

The saved notebook outputs can be inspected without running the analysis.

To execute it locally, use Python with Jupyter or VS Code's notebook support and install:

```bash
python -m pip install pandas numpy plotly matplotlib jupyter
```

Place `netflix_titles.csv` and a compatible `emotion_lexicon.csv` beside `netflix_emotional_framing.ipynb`, then restart the kernel and run the cells in order.

**Reproducibility limitation:** official NRC downloads are not necessarily in the same format as the combined course CSV. The notebook expects a `word` column, eight `NRC_EmoLex_<emotion>` columns and the `NRC_VAD_valence`, `NRC_VAD_arousal` and `NRC_VAD_dominance` columns. Exact reproduction also depends on the original word coverage and scores; renaming columns alone does not guarantee equivalent results. The preparation of the course lexicon remains undocumented, so the repository is not a self-contained reproduction package.

## Limitations

- This is a historical catalogue snapshot, not a complete record of all Netflix additions or the current catalogue.
- Lexicon matching ignores negation, context, irony and word senses; coverage is incomplete.
- A word can belong to several emotion categories, so the eight rates do not sum to 100%.
- Genre groups overlap, and the grouping scheme is an analytical choice.
- The findings are descriptive associations, not causal explanations or evidence of deliberate marketing decisions.

## Development context

Completed as part of a data-analysis course. AI-assisted tools were used for code suggestions, debugging and methodological discussion. The notebook documents the analytical decisions, checks and revisions made during the project.

## Other portfolio projects

- [Excel lab results analysis](https://github.com/roncerok/excel-lab-results-analysis)
- [AdventureWorks SQL and Power BI analysis](https://github.com/roncerok/adventureworks-sql-powerbi-analysis)
