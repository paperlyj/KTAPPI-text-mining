# KTAPPI Text Mining

This repository provides the Python workflow used for text mining, keyword network analysis, LDA topic modeling, topic dynamics, and citation-impact analysis of Scopus-indexed *Journal of Korea TAPPI* articles.

## Repository contents

```text
KTAPPI-text-mining/
├─ data/
│  ├─ scopus_ktappi_2000_2025.csv
│  └─ README.md
├─ notebooks/
│  └─ KTAPPI_text_mining_workflow.ipynb
├─ figures/
├─ results/
├─ requirements.txt
└─ README.md
```

## Data file

The main input file is:

```text
data/scopus_ktappi_2000_2025.csv
```

This file name is recommended because it is short, descriptive, and independent of the original Scopus export ID.

The dataset should contain Scopus-exported bibliographic metadata, including at least:

- `Title`
- `Abstract`
- `Author Keywords`
- `Index Keywords`
- `Year`
- `Cited by`
- `Document Type`

The notebook is designed to automatically recognize these column names.

## Analysis workflow

The notebook includes the following steps:

1. Load and check the Scopus metadata
2. Filter Article and Review documents published up to 2025
3. Clean and refine author/index keywords
4. Merge synonyms, including `nanofibril`, `cellulose nanofibril(s)`, `CNF`, `cellulose nanocrystal(s)`, and `CNC` into `nanocellulose`
5. Generate keyword frequency and keyword evolution results
6. Construct keyword co-occurrence networks and centrality tables
7. Evaluate the number of LDA topics using perplexity and coherence
8. Fit the final LDA topic model
9. Analyze annual topic proportions, topic life-cycle patterns, and citation impact

## How to run

Install the required packages:

```bash
pip install -r requirements.txt
```

Then open and run:

```text
notebooks/KTAPPI_text_mining_workflow.ipynb
```

All tables and figures are displayed directly in the notebook. Set `SAVE_OUTPUTS = True` in the first code cell if you also want to export CSV tables and PNG figures to the `results/` and `figures/` folders.

## Notes

- The notebook uses fixed random seeds for reproducibility.
- Topic labels are manually assigned after inspecting representative terms. The included labels can be edited in the notebook if the topic structure changes after modifying preprocessing rules.
- The Scopus export file should be used in accordance with the terms and conditions of the data provider.

## Suggested citation

If this repository is cited in a manuscript, cite it as supplementary analysis code for the corresponding article.
