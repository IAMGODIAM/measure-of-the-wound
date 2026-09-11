# Changelog

## v1.4.5 — Line-205 correction (unreleased; 2026-09-11)

Caught by the RBPE derivative's Reckoning Protocol audit (2026-09-11), which scored the draft 7/10 and traced two stale figures to this line.

- **Chapter 5 §2008 line corrected.** The crisis paragraph still carried two superseded figures: Black median wealth "$11,200 in 2013, its lowest point in the entire SCF series" (the withdrawn nominal-series figure; corrected Table 5.1 reads $16.78k for 2013 in constant 2022 dollars, series minimum 1989 at $9.20k) and homeownership "peaked around 2004 … trough in 2013" (the vault's ACS 1-year series, tables B25003B/B25003H, shows peak 2007 at 46.5% and post-2000 trough 2016 at 40.7%). The line now reads the vault-verified figures, and the causal verb is softened ("the 2007–2016 window coincided with a reversal of …"). No empirical conclusion changes.
- **Print-edition PDF rebuild pending.** The pinned-container build (Docker) is unavailable in this environment and the PDF toolchain is not installed locally; `The_Measure_of_the_Wound.pdf` still reflects v1.4.4 until the PDF is rebuilt from these sources. Rebuild with `build/rebuild.sh` before any v1.4.5 Zenodo deposit.
- **2023 homeownership row: table-definition break corrected (2026-09-11).** An independent pull of the ACS 2023 1-year summary file (B25003B/B25003H, national) reproduced the 2022 row exactly (44.1/73.0/28.9) but showed the carried 2023 white rate (72.4%) came from B25003A (White alone, includes Hispanic) rather than the series' B25003H (White non-Hispanic, 73.1%). Table 5.6's 2023 row is corrected to 44.7 / 73.1 / 28.4; the verified 2023 row is appended to the raw vault with full provenance. No empirical conclusion changes: the gap remains wider than at the Fair Housing Act's passage.
- **RBPE peer-review backports (2026-09-11).** The derivative article's full cold peer review (Major Revisions; all six majors applied in derivative v0.4) produced analytic and language learnings, backported here and documented in `BACKPORT_NOTES.md`:
  - **Metric-dependence framing (§5.5, Ch. 5 intro).** The conclusion now concedes ratio-convergence where the data show it (wealth ratio nearly tripled; unemployment ratio fell ~1/3 from its maximum) and states the sharper finding: level-improvement, gap-narrowing, and ratio-convergence are logically independent and empirically disagree. "No convergence" → "no parity," which the data support.
  - **Percentage-point gaps alongside ratios.** §5.2: unemployment pp gap 5.35 (1972) / 6.99 (1989) / 2.39 (2024), triple-verified against the monthly BLS pull, the annual vault file, and Table 5.3. §5.4: HMDA pp gap 19.0 (1993) → 10.7 (2022), verified against the HMDA vault file. Table 5.3's blank 2024 row filled (5.98/3.59/1.666); 2025 marked partial-year (11 of 12 months in the archived pull).
  - **Convergence literature engaged.** New §5.2 paragraph distinguishing the paper's descriptive "convergence" from the econometric literature, citing Smith & Welch (1989, *JEL*) and Bayer & Charles (2018, *QJE*); both added to the references. The Derenoncourt/Gerard/Leeb/Monge paper could not be verified and was excluded.
  - **Language discipline.** "Persistence" defined at first use (Introduction) as observed continuity of the measured disparity, not a dynamic-process claim. §5.4 retitled "Homeownership Since the Fair Housing Act" (the old headline asserted what the body disclaims).
  - **HMDA honesty.** Table 5.7 expanded to all twelve archive years with the selection rule stated ("years for which the vault holds a published-summary estimate"); the 2003 2.01 razor-thin margin acknowledged.
  - **False BLS methods claim removed.** §5.2 no longer states the 1972–1975 observations are reconstructions or that the published series begins in 1976; BLS publishes the race-disaggregated series from January 1972 (647 months archived).

## v1.4.4 — "Road to 10" forensic pass (2026-09-11)

A strict-gate audit scored v1.4.3 at 7/10 and named four deductions. This edition resolves what can be resolved and writes down what cannot. No reconciliation is fabricated.

- **FDI: honestly unreproducible → demoted (−1.5 resolved by demotion).** Four documented recomputation attempts on the Humphreys 87.25 score (true Phase 3 corpus bounds: 80.69; with obesity: 80.69; Phase 2 bounds: 82.97; decomposition hand calc: 79.7) all fail; no computation code exists in the package (the referenced `farmblock_pipeline_v2.py` is absent). The Appendix E §E.3 "full-corpus normalization" explanation is falsified and replaced. The FDI is demoted from headline contribution to the organization's exploratory instrument throughout Chapter 7, Chapter 3, the Introduction, the Conclusion, and the abstract — scores are published outputs, not verified findings, not to be cited as findings. New sub-finding: the "corpus mean" no-internet fill (5.879) does not match the corpus mean (7.863); label withdrawn (§E.4).
- **Incarceration denominator established; 2022 endpoint corrected (−0.5 resolved).** Cell-for-cell BJS comparison definitively pins the series as male imprisonment rates (vault `population_basis` field added). The 2022 row (1,862/295/6.31) matched no BJS table — corrected to BJS-published 1,826/337/5.42; 2020 white rate corrected to 332 (ratio 5.67). Cross-era movement restated: 6.45 → 5.42, 1.03 points; range 5.42–7.70; decarceration 47%. Propagated through Chapters 4, 6, 8, Conclusion, README, abstract, Appendix C; W-3 and P-5 annotated as superseded; §E item 8 updated. Pre-1980 Cahalan rows remain carried as compiled.
- **Provenance: new §E.6 (−0.5 partially resolved).** ACS table IDs, vintages, and geography codes recovered from the package's own methodology files (tracts ACS 5-Year 2023; counties ACS 5-Year 2022; health components CDC PLACES 2023). Six-item owed inventory printed for FDI v3.0 (cell definitions, county table audit, query strings, pull/transform code, raw inputs, PLACES attribution).
- **Causal language** swept in a dedicated pass; every edited passage logged (see report).
- **Appendix H gains Section H** with the full fifth-wave record. `errata/` and `review/` are read-only by project constraint and retain superseded figures; documented as frozen-stale in §H.4.

## v1.4.3 — Maternal mortality baseline correction (2026-09-11)

An independent verification review found that the 1930 maternal mortality ratio of 1.48, carried since the first edition, could not be verified as a maternal-mortality figure. Primary-source research confirmed the 1.48 ratio as the documented nonwhite/white **neonatal** mortality ratio for 1939–41 (Shin 1975, Table I) and confirmed that complete national maternal mortality reporting by race begins in **1933**, not 1930 — the first year every state reported maternal deaths (Black 1,000 / White 564 per 100,000 live births, ratio 1.8; MacDorman et al. 2021).

- **1915 and 1930 maternal rows withdrawn** (definitional error, not a precision caveat). Table 6.1 now opens at 1933 (Black 1,000.0 / White 564.0 = 1.77; period classification "negro"). The vault file retains the withdrawn rows with dated withdrawal notices.
- **Cross-era widening restated:** 1.77 → 2.61, a factor of 1.47 over eighty-nine years (replacing the 1.76-fold / ninety-two-year formulation in §6.1, the Conclusion, §8, Appendix C and the abstract). Absolute improvement restated as a factor of twenty (1,000 → 49.5).
- **Appendix H gains Section G** with the full correction record; the W-4 disposition is updated from caveat to withdrawal-and-replacement.
- **1926 series start corrected back to 1925.** v1.4.2 had adopted the reviewer's "BJS dates its series to 1926" in the Conclusion and Appendix C. Verification established the distinction: 1926 begins BJS's *Prisoners report series*; the BJS Historical Corrections Statistics *data* covers yearend 1925. The manuscript is restored to 1925 / ninety-seven years throughout (the pre-1980 Cahalan crosswalk and denominator remain under review per W-3).
- New references: MacDorman et al. 2021 (AJPH); Shin 1975 (Demography).

No change to any empirical conclusion: the ratio is higher in 2022 than in every earlier decade of the table, and the fully-registered 2010→2022 rise (2.24 → 2.61) is unaffected.

Deposit: new Zenodo version under concept DOI `10.5281/zenodo.22270905`. v1.4.2 remains citable as the historical record.


## v1.4.2 — Archive corrections (2026-09-09)

Adopted from the second independent peer review (2026-09-09), conducted with full repository access. No change to any empirical conclusion.

- **Vault SCF series deprecated and replaced (P-1).** The frozen data snapshot still carried the withdrawn W-1 splice in `scf_wealth_gap_1989_2022` (1989: $12,000/$95,000 nominal) after Table 5.1 was rebuilt from the Fed's constant-2022-dollar series in v1.2 — the printed table could not be derived from the vault. The deprecated series is retained unmodified with a dated deprecation notice; the corrected series is committed as `scf_wealth_gap_1989_2022_FEDS2023_constant2022` (12 waves, 1989–2022; Federal Reserve FEDS Notes, 2023-10-18, Fig. 2; universe: families; constant 2022 dollars). Appendix A item 5 now points to the corrected key.
- **Sovereign dataset resealed (P-4).** `data.bdi_composite_index.validation_test` read "compound score 83.5" — the figure superseded by the published FDI of 87.25 in v1.1 (CD-9). The string is corrected, the crosswalk's Humphreys entry updated (fdi 87.25; compound recomputed as the mean of the corrected inputs, 83.53), and the dataset resealed as v1.1-RESEALED with a dated reseal note.
- **Stale Humphreys figures corrected in the snapshot.** The FarmBlock methodology chapter and the vault claim-triage matrix still cited the superseded 83.5; both now read 87.25.
- **Appendix H gains Section F** with the five third-wave findings (P-1–P-5) and their dispositions; **Appendix E** now prints effective FDI tract weights alongside nominal weights; **new Appendix I** prints the 17-state BDI composite ranking.
- **Text corrections:** the Conclusion and Appendix C qualify the imprisonment ratio as probably male rates (6.45 in 1926; 6.31 in 2022; BJS all-adults 2022: 5.22); the series start is corrected to 1926; Chapter 4 "50-city" → "49-city"; §5.2 corrects the BLS series dating.

Deposit: new Zenodo version under concept DOI `10.5281/zenodo.22270905`. v1.4.1 remains citable as the historical record.


## v1.4.1 — DOI edition (2026-09-03)
- Deposited to Zenodo. **Concept DOI `10.5281/zenodo.22270905`** (always resolves to the current edition); v1.4 carries version DOI `10.5281/zenodo.22270906`.
- The concept DOI is now printed on the paper's copyright page, in the suggested citation and in the data-availability statement, so the record cites itself. Added to `CITATION.cff` (as `doi` plus both version identifiers) and to both repository READMEs.
- No change to any text or finding. 91 pages.

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

## 2026-09-11 — BLS monthly unemployment series archived (unreleased; on main, no version bump)
- Added `data/bdi-raw-data-vault/economic/bls_unemployment_monthly_1972-2025_RAW.json`: 647 months (1972-01–2025-11) of LNS14000006/LNS14000003 pulled live from the BLS Public Data API v2 (unregistered) on 2026-09-11 to document the monthly no-inversion claim used by the RBPE derivative.
- Verification: zero months with Black unemployment below white unemployment; all 54 annual values in the existing annual vault file recompute as means of these monthly observations (2025 from 11 months); closest approach to parity April 2020 (ratio 1.190).
- Note: the BLS API key recorded in the annual vault file (`b01f97f6`) is no longer valid as of 2026-09-11 (BLS returns "key invalid"); unregistered access was used for this pull.
