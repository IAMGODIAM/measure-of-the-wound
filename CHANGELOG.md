# Changelog

## v1.4 — Submission Edition (2026-09-03)
The edition prepared for deposit. A dedication, and three changes about stating things exactly.

- **A dedication page is added**, after the copyright page and before the abstract. It names the tradition the author writes from — the love warriors, wounded healers and freedom fighters who went before; Professor Cornel West; the author's late grand-uncle Ralph C. McCartney of Overtown, whose 1997 oral testimony about the construction of I-95 through that neighborhood is quoted in the Preface as primary-source evidence; the author's wife, who edited the manuscript by hand; and the descendants of chattel-enslaved persons for whom the record is assembled. The Preface now also states the kinship to McCartney plainly, which changes how a reader meets his testimony.

- **The AI-assistance disclosure is rewritten to describe the division of labor exactly.** The v1.3 wording — "used substantially… to draft and revise prose, recompute derived statistics" — overstated the machine's role and understated the author's, which is an accuracy problem before it is a compliance one. What happened: the author wrote the prose; a human editor read the draft and returned handwritten notes; the model applied line edits against those notes, did the arithmetic on sources the author had chosen, compiled the corrections ledger and built the typesetting pipeline. It originated no research question, selected no source, drew no conclusion and made no claim.
- **Chapter 7 carries the FarmBlock reproducibility limit at §7.1**, where the index is introduced, instead of leaving it to Appendix E.4a sixty pages later. A reader now meets the limitation before the scores rather than after them. The chapter is retained on that footing rather than withdrawn: what is missing is the pre-scoring pipeline, not the outputs, formulas, weights or normalization method, all of which are public — and §7.3 already prints this project's own failed reproduction (79.7) beside the published score (87.25).
- **The abstract no longer claims the independent review is printed as an appendix.** It is not; it is published alongside the release. Appendix H is the corrections ledger, as stated.

Also corrected: the printed edition date now reads September 2026 rather than August, which is when this edition was actually set; the suggested citation names the author rather than the organization and points at the publication package, as does the data-availability statement; the working repository's README still carried a v1.1 version line and a superseded tract count (15,578).

No change to any finding. 91 pages — the dedication adds one.

## v1.3 — Submission Edition (2026-09-02; build 2026-09-03)
- Added abstract, keywords, JEL codes, author of record, AI-assistance disclosure, data availability statement
- Added consolidated References section (38 entries, author-date, hanging indent)
- Build made deterministic and containerised (`build/Dockerfile`, pinned fonts and wheels, fixed metadata dates, `SOURCE_DATE_EPOCH`); two runs on the same commit are byte-identical and the PDF's SHA-256 is shipped beside it. Answers the independent review's request for a deterministic rebuild command.
- Publication package `IAMGODIAM/measure-of-the-wound` created: paper, sources, build, frozen data snapshot with SHA-256 manifest, errata, review.
- No substantive change to any finding. 90 pages.

## v1.2 — Second-wave corrections (2026-09-01)
Adopted from the independent verification review (Manus AI, 2026-09-01).
- **Table 5.1 wealth series rebuilt** from Federal Reserve FEDS Notes (2023-10-18) Fig. 2, constant 2022 dollars. The prior table spliced a real 2022 endpoint onto nominal 1989 history and reconciled with the Fed's published series under neither basis. Withdrawn: "gap nearly tripled" (2.89×), the 3.2-cent ratio gain, the 868-year parity horizon. Corrected: real gap $154,830 → $240,120 (widest on record); ratio 0.056 → 0.158; Black median wealth +388% vs white +74%.
- No wealth parity horizon asserted; baseline-sensitivity table printed instead (274 yr from 1989; 1,632 from 1992; none from 2001).
- Incarceration scope narrowed: BJS all-adults ratio 5.22 printed beside the series' 6.31 (probably male rates).
- Pre-1933 maternal mortality caveat; unemployment aggregation rule stated; farmland peak uncertainty; NAEP accommodation change disclosed.
- Appendix E.4a: FDI outputs stated as not independently reproducible from the published package.
- Author response filed in `peer-review/responses/`. 86 pages.

## v1.1 — Corrected Print Edition (2026-08-31)
- Drafted Introduction, Chapters 5–8, Appendices A–H (previously stubs)
- Applied all 27 Claim Triage Matrix rulings
- Recomputed every derived statistic from raw; 10 errors found (e.g., 3,015 → 3,496 police killings; "never below 2× unemployment" withdrawn — below 2.0 in 17 of 54 years; NAEP gap 20 → 24.5 pts; incarceration floor 5.7 → 5.80)
- Stack Truth Table counts found stale: 15,578 → 15,507 tracts; 50 → 49 cities
- 8 tracts with imputation artifacts found, incl. the top-ranked tract
- "Five compound catastrophe zones" list withdrawn; instrument's actual top five published
- Fixed Introduction/Ch. 4 cross-reference to the withdrawn list. 80 pages.

## v1.0 — Black Paper drafts (2026-04)
- Preface, Part One (Ch. 1–2), Methodology, Measure, Conclusion drafted; other chapters stubs.
