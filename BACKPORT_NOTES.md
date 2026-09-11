# Backport Notes — RBPE derivative learnings → main manuscript (v1.4.5, unreleased)

**Date:** 2026-09-11
**Source of learnings:** the RBPE derivative manuscript v0.4 (`~/workspace/your_files/rbpe-derivative-draft/`), which passed a full cold peer review (verdict: Major Revisions; all six majors + minors applied and verified in `REVISION_NOTES_V04.md`).
**Scope:** source-only edits to `manuscript/`. No PDF rebuild, no Zenodo action, no release tag.

Every number below was re-verified against the vault/FEDS sources for this backport; the derivative's revision notes were treated as provenance, not gospel.

---

## 1. Metric-dependence framing (peer review M1)

- **Chapter 5 intro** (`05_CHAPTER_5_ECONOMIC.md`): the chapter's thesis sentence now reads "improvement in a group's level does not imply convergence between groups. Level-improvement, gap-narrowing, and ratio-convergence are logically independent, and across these series they disagree."
- **§5.5 conclusion** rewritten: concedes the wealth ratio's near-tripling and the unemployment ratio's ~1/3 decline toward equality up front; holds every distance claim the data support (record 2022 dollar gap; never-inverted ratio; homeownership gap wider than 1968; denial ratio above 2.0); closes "The disagreement among the measures is the finding."
- The old "In no case does a legal remedy … produce convergence" line was vulnerable under the paper's own descriptive definition of convergence (the unemployment ratio did move toward equality); it now reads "produced parity," which the data support.

## 2. Percentage-point gaps (peer review M2) — all re-verified

- **§5.2 (unemployment):** new paragraph — 5.35 pp (1972), 6.99 pp (1989), 2.39 pp (2024), a roughly two-thirds decline from the 1989 peak against the ratio's roughly one-third decline from its maximum. Verified three ways: (a) means of the 12 monthly BLS observations in `data/bdi-raw-data-vault/economic/bls_unemployment_monthly_1972-2025_RAW.json` (1972: 10.4000/5.0500; 1989: 11.4667/4.4750; 2024: 5.9750/3.5917); (b) the annual vault file `bls_unemployment_by_race_1972-2025_FULL_RAW.json` (10.4/5.05, 11.47/4.48, 5.98/3.59); (c) the manuscript's own Table 5.3 values.
- **§5.4 (HMDA):** new paragraph — 19.0 pp (1993) → 10.7 pp (2022), nearly halved. Verified against `data/bdi-raw-data-vault/housing/hmda_mortgage_denial_eviction_RAW.json` (34.3−15.3; 19.8−9.1) and Table 5.7.
- **Table 5.3:** filled the blank 2024 row (5.98%/3.59%/1.666 — matches both vault files; ratio 1.6658→1.666 as mean of monthly ratios) and marked 2025 as a partial-year average (11 of 12 months in the archived pull; October missing — see anomaly note below).

## 3. Convergence-literature paragraph (peer review M6)

- **§5.2:** new paragraph distinguishing the paper's descriptive usage of "convergence" (a relational statistic moving toward equality) from the econometric convergence literature, citing Smith & Welch (1989) and Bayer & Charles (2018). Adapted to the book's voice; the Derenoncourt/Gerard/Leeb/Monge paper the referee mentioned could not be verified and was excluded (same disposition as in the derivative).
- **References** (`11_REFERENCES.md`): added in the paper's existing Chicago style —
  - Bayer, Patrick, and Kerwin Kofi Charles. 2018. "Divergent Paths: A New Perspective on Earnings Differences Between Black and White Men Since 1940." *Quarterly Journal of Economics* 133 (3): 1459–1501.
  - Smith, James P., and Finis R. Welch. 1989. "Black Economic Progress After Myrdal." *Journal of Economic Literature* 27 (2): 519–564.
  Both match the derivative's verified APA entries (authors, year, title, journal, volume, pages).

## 4. Language discipline

- **"Persistence" terminological note** added at first use (`01_INTRODUCTION.md`): "('Persistence' here means observed continuity of the measured disparity, not a claim about its dynamic process.)" Chapter 5's later uses inherit the definition.
- **Headline scan:** "## 5.4 Homeownership, and What the Fair Housing Act Did Not Do" asserted what the body disclaims (a claim about the Act's efficacy) → retitled "## 5.4 Homeownership Since the Fair Housing Act." No other section headline in the manuscript showed the assert-then-disclaim pattern.
- **"Mortgage discrimination":** the only manuscript occurrence (`02_CHAPTERS_1_2.md`) describes the National Fair Housing Alliance's own enforcement-tracking work — a legitimate description of that organization's activity, not the paper's claim about HMDA. Left as-is. Chapter 5 uses "denial" throughout; "discriminatory USDA lending" (§5.1) is a documented-mechanism claim and stands.

## 5. HMDA honesty (peer review M4)

- **Table 5.7** expanded 6 → 12 rows with the six previously-omitted archive years (1995, 1997, 2006, 2014, 2017, 2021), each from `hmda_mortgage_denial_eviction_RAW.json` with its published-summary source. Ratios re-verified (e.g., 27.0/11.5 = 2.348 → 2.35); range "2.01 to 2.36" still holds exactly.
- **Selection rule** now stated in the body: "the twelve years for which the vault holds a published-summary estimate; intervening years are not in the archive."
- **2003 margin** acknowledged: 20.3/10.1 = 2.0099 → 2.01; "one hundredth lower would have crossed it."

## 6. 2020 "convergence by white deterioration"

Already present in §5.2 ("sometimes it means everyone is drowning and the distance between swimmers has shrunk") — as strong as the derivative's version. No change needed.

## 7. False BLS methods claim removed (found during backport)

- §5.2 previously stated that "the 1972–1975 observations are later reconstructions, and the continuous published series begins in 1976." The derivative's v0.2 audit established this is false — BLS publishes the race-disaggregated series from January 1972 (the vault archives 647 months, 1972-M01 through the 2025 pull). Corrected to "are published from January 1972."

## Observed but not resolved (flagged for follow-up)

- **2025 BLS monthly pull anomaly:** the archived pull contains 2025-M12 but is missing 2025-M10 (11 months total), while the vault's coverage note says "1972-01 through 2025-11." The 2025 annual row (6.90/3.73/1.850) reproduces exactly as the mean of the 11 archived months, so no manuscript figure depends on the anomaly — but the missing-October/present-December labeling should be reconciled at the next BLS pull. The table now marks 2025 as a partial-year average regardless.

## Files changed

- `manuscript/05_CHAPTER_5_ECONOMIC.md` (framing, pp gaps, 2024 row, 2025 partial-year note, BLS dating fix, convergence paragraph, 5.4 retitle, HMDA table expansion + honesty notes, 5.5 rewrite)
- `manuscript/01_INTRODUCTION.md` ("persistence" terminological note)
- `manuscript/11_REFERENCES.md` (Bayer & Charles 2018; Smith & Welch 1989)
- `CHANGELOG.md` (v1.4.5 entries)
- `BACKPORT_NOTES.md` (this file)
