# Care Leavers and Higher Education: Analysis

A data-journalism analysis of how care leavers progress to UK higher education: who gets in, who reaches the most selective universities, and the gap that widens at the top.

By age 19, **13%** of care leavers have reached any form of higher education, against **46%** of all other pupils. At high-tariff universities, the most selective in the country, that figure collapses to **2%**. This notebook builds the evidence base behind that finding and produces the figures used in the accompanying data story.

> 🔗 **Read the published piece:** [the data story site](https://anp-exe.github.io/care-leaver-analysis-he/)

---

## What this analyses

The notebook works through twelve questions about care-experienced young people and higher education, moving from the headline gap to the human picture behind it:

1. **The progression gap** — care leavers vs all other pupils, for any HE and for high-tariff HE.
2. **A second disadvantaged cohort** — pupils looked after 12+ months, shown to track care leavers closely.
3. **Change over time** — a decade of progression rates, showing the gap holding even as both rise.
4. **Applicant age** — care-experienced applicants apply older and less often at the standard age of 18.
5. **Applicant volume** — growth in care-experienced applicants, 2018–2022.
6. **Qualification routes** — the over-representation of Access to HE, BTEC, and "Other" routes.
7. **A-level attainment** — a more polarised, U-shaped distribution among care-experienced applicants.
8. **POLAR4 participation** — over-representation in the lowest-participation neighbourhoods.
9. **Duration of care** — most applicants spent 3+ years in care.
10. **Subject choice** — the lean toward nursing, health and social care, and away from business and economics.
11. **What applicants look forward to** — aspiration is not the missing ingredient.
12. **What applicants worry about** — finances and wellbeing far ahead of academic concerns.

---

## Data sources

| Source | Used for |
| --- | --- |
| **DfE — Widening Participation in Higher Education** | Progression to HE by age 19, split by care status and institution tariff |
| **UCAS — care-experienced applicant statistics** | Applicant age, qualification route, POLAR4, subject choice, duration of care, and survey responses |

All figures come from publicly available government and UCAS releases. The analysis combines and reshapes them; the underlying data is not redistributed in this repository.

> [!NOTE]
>  **Note for anyone re-running this:** the raw source files are not committed to the repo (they're large and publicly available at source). Download them from the DfE and UCAS releases above and place them in `notebooks/data/` to reproduce.

---

## Methods

*(This section describes the approach — please verify the specific library and version details against your actual notebook before publishing.)*

- **Language:** Python
- **Core libraries:** `pandas` for data wrangling, `matplotlib` for all figures
- **Workflow:** each question is a self-contained section — load and clean the relevant slice, reshape, then plot
- **Design choices:** a consistent green/mauve palette is used across every chart so the same colour carries the same meaning throughout the set; figures are exported as PNGs for use in the companion site

### A note on definitions
The DfE and UCAS define "care-experienced" slightly differently, so the two datasets are treated as **complementary rather than identical** — the analysis does not merge them into a single population. Cross-year comparisons are affected by KS5 reform and pandemic disruption (per DfE guidance), and survey responses capture stated intent rather than outcome. These caveats are carried through to the published piece.

---

## Repository structure

```
notebooks/
├── <analysis-notebook>.ipynb     # the analysis (update with real filename)
└── data/                         # source data — not tracked in git
charts/                           # exported figures (PNG)
```
*(Update this tree to match your actual layout.)*

---

## How to run

```bash
# clone the repo
git clone https://github.com/anp-exe/care-leaver-analysis.git
cd care-leaver-analysis

# install dependencies
pip install pandas matplotlib jupyter        # add any others your notebook uses

# add the source data files to notebooks/data/ (see Data sources above)

# launch
jupyter notebook
```
