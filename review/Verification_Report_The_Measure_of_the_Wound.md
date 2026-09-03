# Verification Report — *The Measure of the Wound*

**Prepared by:** Manus AI  
**Review date:** September 1, 2026  
**Materials reviewed:** `The_Measure_of_the_Wound.pdf` (80 pages), `CORRECTIONS_LEDGER.md`, and `bdi-black-paper-v1.1.bundle`

## Determination

The supplied PDF is a **materially corrected and unusually transparent manuscript**, and the external ledger is substantively reflected in Appendix H and in the body text. The parallel review confirmed that many of the ledger’s prominent corrections are actually carried into the print edition: the police-killing figures, homeownership vintages, life-expectancy timing, NAEP narrowing, eviction scope, and the retraction of several overstated draft claims all appear as corrections rather than being silently retained.

However, the package is **not fully verifiable as a reproducible empirical record**. The supplied Git bundle is incremental and lacks prerequisite commit `91a9c756c879e4588ea7cb027571606dda23628a`; consequently, its tree, raw-vault JSON, manifests, and the claimed recomputations could not be inspected. In addition, primary-source checking identifies one **high-priority unresolved problem**: the SCF wealth table mixes or leaves unspecified its dollar basis, while its 1989 values do not match the Federal Reserve’s published race-specific historical real median series. This makes the paper’s $83,000-to-$240,100 comparison, 3.2-cent ratio gain, and 868-year parity extrapolation unsupported as presently documented.[1][2]

> **Overall status: Partially verified.** The correction process is real and largely implemented, but the project cannot support the stronger claim that every figure has been independently reproducibly verified from the supplied package.

| Verification plane | Result | Confidence | Reason |
|---|---|---:|---|
| PDF integrity and readability | **Pass** | High | The PDF is a non-encrypted, 80-page document with extractable text and no embedded JavaScript. Sampled pages render legibly. |
| Ledger presence and implementation | **Substantially passes** | High | Appendix H contains the corrections ledger structure and the manuscript incorporates the principal corrected formulations. |
| Internal arithmetic | **Mixed** | High | Several disclosed calculations are correct; the wealth projection is internally correct only when calculated from the table’s own unexplained ratios. |
| Primary-source confirmation | **Mixed** | Medium–High | Health, housing, NAEP, major historical counts, and much of labor are supportable; wealth, some incarceration definitions, and local/methodological outputs require correction or reproducibility support. |
| Raw-data / repository reproducibility | **Blocked** | High | The supplied Git bundle cannot be resolved without its prerequisite commit or a complete bundle/repository. |

## Method

The review used two parallel evidence stages. First, six independent manuscript-range reviews extracted material numerical, methodological, and historical claims and matched them to the supplied ledger. Second, eight independent source-review lanes examined the labor, wealth, housing, health, justice, education, history/agriculture, and local/methods domains against primary or authoritative sources. Findings were then reconciled against the source PDF’s exact text, tables, and sampled visual pages.

This report distinguishes three different propositions that should not be conflated: **(1) the final PDF matches the supplied ledger; (2) a claim is internally arithmetically consistent; and (3) a claim is independently confirmed by an authoritative source.** A ledger entry can pass the first test while still failing the third.

## 1. Package-level verification

| Item | Observation | Result |
|---|---|---|
| PDF | 80 pages; letter-size; non-encrypted; text extractable; no PDF JavaScript detected. Visual sampling of pp. 39 and 55 found tables legible and correctly rendered. | **Pass** |
| External ledger | Describes ten recomputation errors (R-1 through R-10), 27 triage decisions, current-source checks, and disclosed methodological limitations. | **Reviewed** |
| Appendix H | The PDF includes an Appendix H correction ledger that tracks the supplied ledger’s principal R-series values and triage dispositions. | **Substantive match** |
| Git bundle | Head advertised as `ba5097240e89f2b458ddb32081574e66f62e1e63` (`corrected-print-edition-v1.1`). Verification reports an absent prerequisite commit: `91a9c756c879e4588ea7cb027571606dda23628a`. | **Blocked** |

The bundle finding is consequential. The manuscript states that its values were recomputed from raw-vault files and refers to specific repository paths. Those assertions cannot be independently tested from an incremental bundle whose required parent history is absent. No content from the bundle was executed.

## 2. Ledger-to-manuscript implementation

The strongest positive result is that the manuscript does not merely attach an errata document. It generally embeds the corrective narrative in the relevant chapters and repeats it in Appendix H.

| Ledger item | Final-manuscript treatment | Implementation status |
|---|---|---|
| R-1 / R-2 — unemployment absolutes and claimed floor | Chapter 5 withdraws both draft absolutes and uses a 1.58–2.56 range with a 2.115 average. | **Implemented** |
| R-3 — police killings | Chapter 6 gives 3,496 Black people killed and 397 unarmed for 2013–2023, while identifying earlier 3,015/377 totals as undercounts. | **Implemented** |
| R-4 — incarceration floor | Chapter 6 distinguishes the empirical-window floor from the full-series range rather than retaining “never below 5.7.” | **Implemented, but source definition needs support** |
| R-5 — homeownership | Chapter 5 gives 28.9 percentage points for ACS 2022 and 27.7 points for the cited later release, replacing 30.1. | **Implemented** |
| R-6 / R-7 — wealth | The manuscript uses 868 years and “nearly tripled/2.89-fold” rather than 263 years and “tripled.” | **Implemented internally; externally unresolved** |
| R-8 — life expectancy | The manuscript gives a 2019–2021, four-year fall and avoids the erroneous “20 years in 18 months” formulation. | **Implemented** |
| R-9 — NAEP | Chapter 6 presents the 29.63-to-24.54 Grade 8 reading gap and a mechanical 144-year linear extrapolation. | **Implemented** |
| R-10 — eviction scope | The manuscript distinguishes the Eviction Lab and Graetz et al. measures rather than presenting a scope-free 3× assertion. | **Implemented** |

An editorial ambiguity remains around the paper’s “Five Compound Catastrophe Zones.” The introduction lists Humphreys, Detroit, East St. Louis, Claiborne, and the southeastern Louisiana petrochemical corridor. The ranked county table and Appendix D instead rank Humphreys, Claiborne, Sunflower, Alexander, and Amite as the top five county scores. Chapter 7 later explains that the originally named places were selected for documentary depth rather than score, and the conclusion says that the prior list was “withdrawn and replaced.” This is disclosed, but the introduction should label its five places as **case studies** rather than presenting them under a score-like heading. Otherwise, a reader encounters an unresolved apparent contradiction before reaching the explanation.

## 3. Independent fact-check results

### Confirmed or well-supported claims

| Domain | Claim examined | Independent result | Assessment |
|---|---|---|---|
| Maternal mortality | 2021 Black maternal mortality rate of 69.9 per 100,000; 2022 rates of 49.5 Black and 19.0 White. | The NCHS 2022 table reports all three rates. The 2022 division is 49.5 ÷ 19.0 = **2.605263**, conventionally rounded to **2.61**.[3] | **Confirmed**, with a minor rounding correction from 2.62 to 2.61 if two decimals are used. |
| Life expectancy | Black life expectancy fell from 74.8 in 2019 to 70.8 in 2021. | The parallel primary-source review found the stated four-year decline supportable from NCHS life-table data. | **Supported** |
| NAEP reading | Grade 8 White–Black gap narrowed from approximately 30 points in 1992 to approximately 25 in 2022. | NCES table 221.10 reports rounded scores of 267/237 in 1992 and 268/244 in 2022. It also discloses the accommodation change between the earlier and later assessments.[4] | **Confirmed in substance** |
| NAEP linear extrapolation | 29.6274 to 24.5404 is a 5.0870-point decrease; extrapolating this average annual closure rate gives about 144.7 additional years. | Arithmetic is correct as a **mechanical linear extrapolation** from the stated high-precision values. | **Internally correct; label as extrapolation, not forecast** |
| Homeownership | Gap of approximately 24 points in 1968; 28.9 points in ACS 2022; 27.7 points in the cited 2023 NAR release. | Parallel source review located support in Census housing historical data and the cited NAR release. These are different series/vintages and must remain labelled as such.[8] | **Supported with vintage labels** |
| HUD Section 3 | 53% of PHAs did not file required reports. | The reported 1,650 of 3,102 PHAs equals 53.2%; source citation should be standardized to the applicable HUD OIG report rather than only a regional variant. | **Supported; citation cleanup needed** |
| Transatlantic slave trade | 12,521,337 embarked; 10,702,656 disembarked; difference 1,818,681; 14.5% mortality; 388,747 North American disembarkations. | The precise arithmetic is 14.524654% mortality and 3.632247% of arrivals for the North American figure. The manuscript’s 14.5% and 3.6% are valid roundings.[9] | **Confirmed** |
| Police killings | 3,496 Black people killed and 397 unarmed, 2013–2023. | These values are supportable as a **dated Mapping Police Violence snapshot**, not as current live totals. MPV is non-federal and should continue to be labelled that way.[6] | **Supported with snapshot/date label** |
| Unemployment distribution | 54-year series, ratio low about 1.576 (2020), high about 2.56 (1989), mean about 2.115, and 17 years below 2.0. | Parallel recomputation from the named BLS/FRED series found these distributional results supportable, subject to annual aggregation method and data-vintage revisions.[10][11] | **Supported with method note** |

### Claims needing revision, qualification, or raw-data access

| Priority | Claim or presentation | Finding | Required remedy |
|---:|---|---|---|
| **1** | Table 5.1 wealth series; $83,000-to-$240,100 comparison; 3.2-cent gain; 868-year parity | The Federal Reserve expressly provides separate nominal and 2022-dollar historical tables.[1] Its published real race-specific median series gives 1989 White $164.03k and Black $9.20k, versus 2022 White $285.01k and Black $44.89k.[2] The manuscript’s 1989 $95k/$12k endpoints and 2022 $285k/$44.9k endpoint therefore do not state a consistent visible price basis. | Publish the raw SCF extraction, variable definitions, race coding, price basis, and code. Rebuild Table 5.1 in either nominal or constant 2022 dollars. Recompute the gap, ratio trend, and any parity scenario from that one consistent series. |
| **2** | 868-year wealth parity claim | From the paper’s own rounded ratios, (1 − .158) ÷ ((.158 − .126) ÷ 33) = **868.04**, so the arithmetic is internally consistent. But the Federal Reserve’s published real endpoints imply .056087 in 1989 and .157503 in 2022: an average change of .003073/year and a simple linear result of **274.14 years**. Neither figure should be framed as a forecast. | Withdraw “the correct number is worse” unless the underlying series is documented. Call any figure a conditional, linear scenario and state its instability. |
| **3** | 2023/2024 unemployment ratios beside rounded annual rates | 5.5 ÷ 3.3 = **1.666666**, not 1.683; 5.9 ÷ 3.6 = **1.638888**, not 1.666. The discrepancy can arise if ratios are averaged monthly while displayed component rates are rounded annual averages. | State the aggregation rule explicitly and report sufficient precision in the component rates, or calculate ratios directly from the displayed annual averages. |
| **4** | 1925 and 2022 incarceration ratios of 6.45 and 6.31; 46% decarceration | Current BJS reporting begins its series in 1926 and uses population/sex/race-specific definitions. The claimed endpoints cannot be confirmed from the supplied material without the exact historical crosswalk. Parallel review suggests the ratios may refer to Black male imprisonment rates, which must be stated.[5] | Cite table identifiers, numerator/denominator, and sex/age definition for every endpoint. Do not use “Black Americans” if the series is Black males. |
| **5** | 1930 maternal ratio 1.48 and 1.76× widening | The 2022 rate evidence is clear. The supplied citations do not make the historical 1930 maternal numerator/denominator independently reproducible in this review. The ratio should not be compared across eras without a source/definition statement. | Add the historical table and a definition note; make clear whether the measure is maternal mortality, pregnancy-related mortality, or another mortality measure. |
| **6** | Humphreys FDI 87.25 and tract/county rankings | The paper commendably discloses a hand recomputation of **79.7** versus published **87.25**, as well as imputation artifacts in eight tract rows. Yet the cited “full Phase 3 corpus” and raw normalization bounds are unavailable because the supplied Git bundle cannot be opened. | Supply a complete repository/bundle plus immutable raw input files, transformation code, normalization bounds, and the final CSV. Until then, describe FDI outputs as **not independently reproducible from the supplied package**. |
| **7** | Humphreys local inputs | The manuscript explicitly separates poverty vintages and estimates, which is good practice. A later ACS result cannot by itself contradict an older vintage. But the 28.0% vacancy input and other local figures need vintage/table IDs in the public artifact. | Add ACS table IDs, release years, geography codes, and formulas in Appendix E or a data dictionary. |
| **8** | Black-owned farmland “13.5 million acres lost 1910–1997” | Parallel review found 1.5m acres in the 1997 Census supportable, but a 13.5m peak aligns more closely with a 1900 figure; a 1910 source may support a different total. | Reconcile the **year–value pairing**: either use the cited 1910 total or label the 13.5m value as a 1900 peak. |

## 4. Reproducibility and editorial risks

The manuscript’s willingness to publish its own caveats is a meaningful strength. It identifies the 1,855-to-1,574 observation-count correction, an imputation artifact in high-scoring tract results, small-area ACS uncertainty, a food-desert proxy, and the unresolved 79.7-versus-87.25 decomposition. These disclosures make the work more auditable than a paper that suppresses its errors.

Nevertheless, transparency is not a substitute for a complete reproducibility package. The text repeatedly characterizes raw data and repositories as public and checkable. For that representation to be independently testable, a reviewer must be able to obtain a complete Git history or full archive, raw data files, provenance hashes, code, dependency/version lockfile, and a deterministic command that rebuilds the tables in the PDF. The provided incremental bundle does not meet that standard by itself.

The paper should also use more careful language for projections. A linear parity calculation is an arithmetic extension of historical endpoints, not an estimate of a social or economic future. The claim remains rhetorically forceful when stated precisely; calling it a forecast overstates what the data can establish.

## 5. Required actions before calling the edition fully verified

| Action | Why it matters | Priority |
|---|---|---:|
| Provide a complete Git bundle or repository containing prerequisite commit `91a9c756c879e4588ea7cb027571606dda23628a`. | Enables inspection of vault data, manifests, source citations, and transformation history. | **Critical** |
| Publish the Table 5.1 SCF extraction and rebuild it with a single stated price basis. | Resolves the most material quantitative discrepancy and the downstream parity claim. | **Critical** |
| Add a reproducibility appendix/data package for FDI scores and ranks. | Allows independent recomputation of 1,574 observations, 15,507 tracts, 49 cities, and the 87.25 score. | **Critical** |
| Define the unemployment aggregation method and display precision. | Resolves visible numerator/ratio inconsistencies without changing the underlying argument. | High |
| Define the incarceration series’ population and cite endpoint tables. | Prevents a potentially material mismatch between male-specific rates and all-person wording. | High |
| Source the 1930 maternal comparator and reconcile the farmland peak’s year/value. | Corrects or qualifies two historical anchors. | High |
| Rename the introductory “Five Compound Catastrophe Zones” section to distinguish case studies from top-ranked counties. | Removes a reader-facing internal ambiguity that the later text already explains. | Medium |

## Conclusion

The supplied materials demonstrate that the authors performed a serious correction pass and incorporated many of its results into the printed manuscript. The final edition is more defensible than the drafts described in the ledger. **It should not yet be described as fully source-verified or fully reproducible**, however, because the supporting bundle is incomplete and the wealth series is presently not documented in a consistent, independently reconcilable form.

The fastest path to a fully verifiable edition is narrow and concrete: release a complete repository, reproduce the SCF table from a single stated basis, and provide the FDI computation artifacts. Those steps would allow the manuscript’s strongest claim—that its record can be checked—to be tested rather than merely asserted.

## References

[1]: https://www.federalreserve.gov/econres/scfindex.htm "Federal Reserve — Survey of Consumer Finances"
[2]: https://www.federalreserve.gov/econres/notes/feds-notes/greater-wealth-greater-uncertainty-changes-in-racial-inequality-in-the-survey-of-consumer-finances-accessible-20231018.htm "Federal Reserve — Greater Wealth, Greater Uncertainty"
[3]: https://www.cdc.gov/nchs/data/hestat/maternal-mortality/2022/maternal-mortality-rates-2022.htm "CDC/NCHS — Maternal Mortality Rates in the United States, 2022"
[4]: https://nces.ed.gov/programs/digest/d22/tables/dt22_221.10.asp "NCES — Digest Table 221.10, NAEP Reading Scores"
[5]: https://bjs.ojp.gov/library/publications/prisoners-2022-statistical-tables "Bureau of Justice Statistics — Prisoners in 2022"
[6]: https://mappingpoliceviolence.org/ "Mapping Police Violence — National Database"
[8]: https://www.census.gov/housing/hvs/data/histtabs.html "U.S. Census Bureau — Housing Vacancies and Homeownership Historical Tables"
[9]: https://www.slavevoyages.org/assessment/estimates/ "Slave Voyages — Trans-Atlantic Slave Trade Estimates"
[10]: https://fred.stlouisfed.org/series/LNS14000006 "FRED — Unemployment Rate: Black or African American"
[11]: https://fred.stlouisfed.org/series/LNS14000003 "FRED — Unemployment Rate: White"

