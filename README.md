# AI Problem Design — Scam Message Classification

**Internship:** SWYNEX Technologies — Artificial Intelligence Internship
**Task:** Task 1 — AI Problem Design

## Problem Statement
Classify incoming SMS/text messages as scam or legitimate, to help users identify phishing and fraud attempts before they act on them.

## AI Use Case Type
Classification (binary: scam vs. legitimate)

## User
A general smartphone user receiving unsolicited SMS messages — particularly ones with links, urgency cues ("your account will be blocked"), or requests for personal/financial info. They need a fast, understandable signal on whether a message is risky.

## Data Source
A small labeled dataset of SMS messages tagged as "scam" or "legitimate" (e.g. public SMS spam/phishing datasets, or a hand-collected sample of ~200–500 messages for a prototype).

## Constraints
- **Small dataset** — the model must generalize without overfitting; simple, interpretable models (e.g. TF-IDF + Logistic Regression) are preferred over deep learning here.
- **Near real-time** — needs to score a single message quickly, not run as a batch job.
- **Explainability** — users should see *why* a message was flagged (e.g. specific words/phrases that triggered risk), not just a black-box score.
- **False positive cost** — flagging safe messages as scam erodes user trust, so precision on the "legitimate" class matters as much as catching scams.

## Evaluation Approach
- Train/test split on the labeled dataset, with precision, recall, and F1-score reported per class.
- Track false positive rate separately, given its real usability cost.
- Manual review of a handful of misclassified examples to sanity-check the model isn't relying on spurious keywords.
