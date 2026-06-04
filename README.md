# Care Leavers and Higher Education, Analysis README

A data journalism project in the spirit of *1 in 9*. The thesis: the data on care leavers in UK higher education is fragmented, suppressed, self-declared, and contradictory — and **that fragmentation is the story.** Where FIDE handed over 47M clean chess records, the care system gives gaps, four-nation definitional chaos, and headline stats that change depending on who you ask (6% vs 13% vs 14% HE progression).

## The human anchor

The piece is anchored by a real story: a friend who is a care leaver founded **Oxford Class Act**, a University of Oxford society for students from underrepresented backgrounds. They held a care-leaver meet-up. **Two people showed up.** That single image carries the whole project — every percentage in this analysis is really about how few people are in that room.

## Central angle

**The number nobody agrees on** — a methodological piece interrogating why the headline figure for care-leaver university access changes depending on the source (6% SSDA903 vs 13% DfE digest vs 14%), and what that says about how seriously the system counts these young people.

## The core questions

### Q1 — The HE participation funnel
How many care leavers start, progress, and enter higher education, broken down by nation (England, Scotland, Wales, NI). The headline funnel.

### Q2 — The geography of opportunity
Local-authority-level mapping of care-leaver HE entry rates. Postcode-lottery framing. Visual centrepiece.

### Q3 — Subject-level gaps
What care leavers study versus the general student population, and where the gaps cluster.

### Q4 — Retention and completion
Getting in versus getting through. Entry is not the same as a degree.

### Q5 — Promises versus outcomes
Universities' Access and Participation Plan (APP) pledges against the actual care-leaver numbers they record.

### Q6 — Distance from home (NEW)
How far care-experienced children are placed from where they originated. SSDA903 records placement distance and out-of-authority placements, so "placed 20+ miles away" is directly pullable; a 100+ mile cut can often be derived.
**Status: gettable.** Pull from DfE SSDA903 placement data.

### Q7 — Placement stability during the exam years (NEW)
Placement instability across the GCSE / A-level years (ages 15–18), using the published "three or more placement moves in a year" indicator.
**Status: gettable if reframed.** Note: data on moves timed *specifically to exam weeks* is NOT published — reframe as instability across the exam-age window, which the data supports. Do not claim exam-week precision.

### Q8 — Graduate salary by subject studied (NEW)
For the subjects care leavers cluster into (from Q3), the typical graduate earnings using the LEO (Longitudinal Education Outcomes) dataset.
**Status: gettable with a hard caveat.** LEO does NOT publicly break earnings down by care-leaver status (cells too small, suppressed). Honest framing: "care leavers cluster in subjects X and Y; typical graduate earnings for those subjects are Z" — NEVER "care leavers earn Z."

## Nested deep-dive: care leavers in the Russell Group

This sits inside Q1 (funnel) and Q5 (promises vs outcomes). Derived three ways and triangulated — the methods are not averaged, the spread is the finding.

### The two questions (never conflate)
- **Q_A** — % of care leavers who reach a Russell Group uni (denominator = all care leavers). ~1–2%.
- **Q_B** — % of Russell Group students who are care leavers (denominator = all RG students). ~0.4%.

### The three methods
1. **Method 1 — DfE widening participation (tariff proxy).** Answers Q_A. "High tariff" as a proxy for RG. Benchmark ~1.8%.
2. **Method 2 — OfS bottom-up (exact UKPRN match).** Answers Q_A and Q_B. Sums care-experienced entrants across the exact 24 RG providers. Rigorous, but a **floor not a true count.**
3. **Method 3 — flipped national-rate cross-check.** Answers Q_B against the published ~0.4% sector figure.

### Primary data source for the RG deep-dive
Office for Students (OfS) Access and Participation data dashboard, 2025 release — access lifecycle stage. Open Government Licence v3. Last updated February 2026.

## Data sources by question

- **Q1, Q6, Q7:** DfE SSDA903 "Children Looked After in England" (Explore Education Statistics)
- **Q1 (devolved):** Scotland Children's Social Work Statistics, StatsWales, NI DoH
- **Q1, Q2, Q5, RG:** DfE Widening Participation; OfS Access & Participation dashboard
- **Q3, Q8:** HESA subject data; LEO (Longitudinal Education Outcomes)
- **Q4:** OfS continuation/completion indicators
- **Context:** House of Commons Library briefing CBP-8429; Rees Centre; Become / NNECL

## Caveats baked into every result

- **Suppression.** OfS rounds and suppresses small cells. Care-leaver counts at individual RG providers are frequently suppressed, pushing Method 2 below the true number. This is itself a finding.
- **Self-declaration.** The care-experience flag is self-reported; many eligible students never tick it. Downward pressure on every count.
- **No earnings-by-care-status.** LEO cannot be sliced by care-leaver status publicly (Q8). State subject-level earnings, not care-leaver earnings.
- **No exam-week placement data.** Q7 reframed to the exam-age window, not literal exam timing.
- **Four-nation definitions differ.** "Looked after" means different things across the UK; do not stack numbers across nations.
- **The 22–25 cohort is undercounted.**
- **RG definition.** Exact match on 24 UKPRNs, not a tariff proxy. The notebook's match-failure report must come back clean before any total is trusted.

## Headline framing rule

Always report as "one of the small percentage of care leavers to reach a Russell Group university" — never a hard single percent. The precise figure is not cleanly published and is challengeable.

## Files

- `care_leavers_russell_group.ipynb` — the RG triangulation notebook (auto-downloads OfS data)
- `data/rg_ukprn_lookup.csv` — the 24 Russell Group providers + UKPRNs (generated)
- `data/rg_care_by_provider.png` — per-provider chart (generated)
