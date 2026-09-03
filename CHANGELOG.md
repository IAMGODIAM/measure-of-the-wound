# Changelog

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
