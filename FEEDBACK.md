# Peer Feedback — Practice 9 Step 4.02 (Simulated Classmate Review)

**Reviewer:** Fong Hio Lam (simulated for the "Test and Improve" exercise).
**Site reviewed:** https://fongchinwai-vivi.github.io/data-science-project/

## Purpose of this project site

- To explain the Assignment 1 regression pipeline (Modules 01–06) as a standalone
  GitHub Pages site: research question → datasets → methods → findings → reproduction.
- The site exists so that a visitor can understand the project and re-run it without
  opening a single notebook first.

## Main findings I can identify

- Engine size and horsepower dominate automobile price; the strongest correlation is
  engine size at r = 0.872.
- Square footage / living area dominates King County house prices.
- Polynomial regression overfits; Ridge with a grid-searched alpha raises the test-set
  R² and stabilises MSE.

## Limitations I would point out

1. The dataset source table names UCI / IBM / Kaggle but does not link to the exact
   datasets, so the "publicly available" claims are hard to verify from the page itself.
2. The 1985 automobile data limits transferability to today's market — the page admits
   this, which is good, but the caveat is not repeated near the findings section of the
   README.
3. No explicit statement of data-license compliance on the page (the README covers it).

## Improvement implemented in Step 4.03

- Added direct hyperlinks to the original dataset sources in the "Dataset sources" table
  so the provenance is verifiable from the page itself.
