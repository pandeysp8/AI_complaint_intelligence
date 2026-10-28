## Problem

Credit card issuers receive a steady stream of customer complaints written
in free text. Today, teams typically read, tag, and route these by hand.
This creates three business problems:

1. **Slow routing.** Complaints wait in a queue before reaching the team
   that can fix them, which delays resolution and frustrates customers.
2. **Inconsistent tagging.** Different reviewers label the same issue
   differently, so complaint trend reports are unreliable.
3. **Late detection of emerging issues.** A new problem, such as a billing
   error after a system change or a new fraud pattern, is often noticed only
   after complaint volume has already grown, raising customer harm and
   regulatory risk.

## Objective

Build and evaluate an LLM-powered system that, for each credit card
complaint:
- classifies the issue into a standard category,
- extracts the root cause and assigns a severity level, and
- writes a one-sentence summary for managers,

and that detects emerging complaint themes month over month.

The key question: **Can an LLM do this accurately and cheaply enough to
replace or assist manual review, compared with a traditional ML model?**

## Users

- Complaint operations teams who route and resolve complaints
- Compliance and risk teams who monitor customer harm
- Product leaders who need early warning on new issues

## Success metrics

| Goal | Metric | Target |
|---|---|---|
| Accurate routing | Macro F1 vs. CFPB issue labels | Beat the TF-IDF baseline |
| Trustworthy extraction | % of root causes and summaries rated accurate | ≥ 85% |
| Trustworthy evaluation | LLM-judge agreement with my manual review (30 cases) | ≥ 80% |
| Practical to run | Cost per 1,000 complaints and seconds per complaint | Reported for each approach |
| Early warning | Top 3 fastest-growing complaint themes identified | Named and charted |

## Data

Public CFPB Consumer Complaint Database exports (credit card complaints with
consumer narratives). No proprietary or employer data is used.

## Out of scope

- Real-time production deployment
- Automated responses to customers
- Any decisions about individual customers
