# APPENDICES

## APPENDIX A — SOURCE CITATION TABLE

Every series used in this paper, with the agency, instrument, coverage and vault location. All raw files were committed unmodified to `bdi-raw-data-vault` before any analysis was performed.

| # | Series | Agency &amp; instrument | Years | Vault file |
|---|---|---|---|---|
| 1 | Unemployment by race | Bureau of Labor Statistics<br/>CPS, series LNS14000006 / LNS14000003 | 1972–2025 | `economic/bls_unemployment_by_race_1972-2025_FULL_RAW.json` |
| 2 | State unemployment (total rate) | Bureau of Labor Statistics<br/>LAUS, series LASST — not race-disaggregated | 2010–2024 | `economic/tier1_state_bls_unemployment_2010-2024_RAW.json` |
| 3 | Homeownership, income | Census Bureau<br/>ACS 1-year, B25003B/H, B19013B/H | 2005–2022 | `economic/census_acs_homeownership_income_RAW.json` |
| 4 | Poverty | Census Bureau<br/>ACS 1-year, B17001B/H | 2005–2022 | `economic/census_acs_poverty_RAW.json` |
| 5 | Family wealth | Federal Reserve Board<br/>Survey of Consumer Finances, triennial — as presented in the Board's FEDS Notes, constant 2022 dollars | 1989–2022 | `economic/fed_reserve_scf_wealth_usda_land_RAW.json`, key `scf_wealth_gap_1989_2022_FEDS2023_constant2022` |
| 6 | Black farmland | USDA NASS<br/>Census of Agriculture | 1910–2022 | `economic/fed_reserve_scf_wealth_usda_land_RAW.json` |
| 7 | State economics | Census Bureau<br/>ACS 5-year, all states | 2010–2022 | `economic/tier1_state_economics_ACS_2010-2022_RAW.json` |
| 8 | Metro economics | Census Bureau<br/>ACS 5-year, 516+ MSAs | 2015–2022 | `economic/tier2_metro_msa_economics_ACS_2015-2022_RAW.json` |
| 9 | County economics | Census Bureau<br/>ACS 5-year, 3,222 counties | 2015–2022 | `economic/tier3_county_economics_ACS5Y_2015-2022_RAW.json` |
| 10 | Life expectancy, maternal mortality | NCHS<br/>National Vital Statistics Reports | 1900–2022 | `health/nchs_life_expectancy_maternal_mortality_RAW.json` |
| 11 | Imprisonment by race | Bureau of Justice Statistics<br/>Prisoners series; Cahalan 1986 for pre-1980 | 1925–2022 | `criminal_justice/bjs_incarceration_mpv_killings_RAW.json` |
| 12 | Police killings | Mapping Police Violence *(non-federal)*<br/>MPV public database | 2013–2023 | `criminal_justice/bjs_incarceration_mpv_killings_RAW.json` |
| 13 | NAEP score gaps | NCES<br/>Main Assessment, reading and mathematics | 1992–2022 | `education/tier1_naep_score_gaps_national_1992-2022_RAW.json` |
| 14 | Educational attainment | Census Bureau<br/>ACS B15002, all states | 2022 | `education/tier1_state_education_attainment_2022_RAW.json` |
| 15 | Historical homeownership; voter turnout | Census Bureau<br/>Census of Housing; CPS P20 November supplement | 1940–2010; 1964–2020 | `housing/census_decennial_homeownership_1940-2010_RAW.json` |
| 16 | Mortgage denial; eviction | CFPB / FFIEC; Princeton Eviction Lab<br/>HMDA; Eviction Lab national dataset | 1993–2022; 2000–2016 | `housing/hmda_mortgage_denial_eviction_RAW.json` |
| 17 | Transatlantic slave trade | Slave Voyages, Emory University<br/>Trans-Atlantic Slave Trade Database, 2023 edition | 1514–1866 | `historical/slavevoyages_1514-1866_aggregate_RAW.json` |
| 18 | County Black population share | Census Bureau<br/>ACS B02001 | 2022 | `demographics/tier3_county_black_population_pct_2022_RAW.json` |

**Supplementary sources cited in text:** HUD Office of Inspector General, *Audit of HUD's Section 3 Program*, 2013-AT-0003 (March 28, 2013); Graetz et al., *PNAS* (2023), eviction and filing rates by race; EPA EJScreen via Public Environmental Data Partners (removed from EPA.gov February 5, 2025); Tessum et al. (2021); Mikati et al. (2018); CDC PLACES 2023; USDA Food Access Research Atlas 2019; HRSA Area Health Resources File.

**Primary-source qualitative evidence:** McCartney, Ralph, oral history interview, August 14, 1997, Samuel Proctor Oral History Program, University of Florida / Black Archives of South Florida. Meek, Carrie P., Congressional Record, 103rd Congress, February 1, 1994, p. 723.

---

## APPENDIX B — COUNTING METHODOLOGY

**The rule.** One data point equals one row in a time series, or one unique observation record.

**Included:** each year of an annual series; each census decade in a decennial series; each year × race combination in a stratified series; each year × grade combination in NAEP.

**Excluded:** JSON metadata keys (`source`, `pillar`, `notes`, `verification_note`); text-only records carrying no numeric observation; duplicate series committed from the same source in more than one file.

**The correction of record.** The dataset was publicly described at one point as containing **1,855 data points**. That count included metadata keys as though they were observations. Applying the rule above yields **1,574 verified empirical observations**. The corrected figure is used in every public statement, is recorded in the dataset JSON itself (`total_data_points_original_claim: 1855`, with a correction note), and appears in this paper's Introduction rather than only in a methods note.

**Tier breakdown of the raw vault (~14,811 observations):**

| Tier | Scope | Observations |
|---|---|---|
| Tier 1 | National series | 479 |
| Tier 1 | State series | 358 |
| Tier 2 | Metro / MSA (516+ areas) | 1,550 |
| Tier 3 | County (3,222 counties) | 12,382 |
| Historical | 1514–1866 aggregates | 42 |

---

## APPENDIX C — PILLAR SUMMARY

| Pillar | Weight | Headline finding | Series span |
|---|---|---|---|
| Economic | 20% | Real wealth gap widened $154,830 → $240,120 (widest on record) while the ratio nearly tripled, 0.056 → 0.158 | 1972–2025 |
| Health | 20% | Maternal mortality ratio 1.77 (1933) → 2.61 (2022); Black life expectancy −4.0 years, 2019–2021 | 1900–2022 |
| Criminal justice | 20% | Imprisonment ratio, Black males vs white males, 6.45 (1925) → 5.42 (2022); BJS all-adults ratio 5.22 — denominator established as male rates (v1.4.4) | 1925–2022 |
| Education | 15% | Grade 8 reading gap 29.6 → 24.5 points; ~144 years to parity at observed rate | 1992–2022 |
| Housing | 10% | Homeownership gap 28.9 pp in 2022 vs ~24 pp when the Fair Housing Act passed | 1940–2023 |
| Environmental | 10% | Fence-line tracts, St. James Parish Districts 4–5: 65–94% Black vs ~44% parish-wide | 2015–2022 |
| Political | 5% | 2012 the only year Black turnout exceeded white (+2.5); −8.3 by 2020 | 1964–2020 |
| Historical | context only | 12,521,337 embarked; 1,818,681 lost; 13.5M acres of farmland lost 1910–1997 | 1514–1997 |

---

## APPENDIX D — THE RANKED COMPOUND DISTRESS COUNTIES

FarmBlock County Distress Index, Phase 2 published pilot, n = 24.

| Rank | County | FDI | Rank | County | FDI |
|---|---|---|---|---|---|
| 1 | Humphreys, MS | 87.25 | 13 | Acadia, LA | 55.28 |
| 2 | Claiborne, MS | 85.26 | 14 | Accomack, VA | 54.37 |
| 3 | Sunflower, MS | 78.34 | 15 | Benton, TN | 51.59 |
| 4 | Alexander, IL | 77.38 | 16 | Adams, WI | 50.89 |
| 5 | Amite, MS | 70.86 | 17 | Bronx, NY | 50.43 |
| 6 | East Carroll, LA | 70.02 | 18 | Adams, OH | 48.85 |
| 7 | Adams, MS | 68.31 | 19 | Tallapoosa, AL | 48.36 |
| 8 | Barbour, AL | 65.68 | 20 | Ashtabula, OH | 45.70 |
| 9 | Ashley, AR | 59.55 | 21 | Allegany, MD | 43.14 |
| 10 | Gadsden, FL | 57.98 | 22 | Essex (Newark), NJ | 42.83 |
| 11 | Wayne (Detroit), MI | 56.79 | 23 | Fresno, CA | 40.03 |
| 12 | St. Louis City, MO | 55.43 | 24 | Allen, IN | 34.47 |

*Earlier drafts named a "five compound catastrophe zones" list — Humphreys, Detroit, East St. Louis, Claiborne and Cancer Alley — that did not correspond to this ranking. Detroit ranks 11th. East St. Louis lies in St. Clair County, Illinois, which is not in this corpus. The list is withdrawn; the ranking above stands.*

---

## APPENDIX E — FARMBLOCK METHODOLOGY AND KNOWN DEFECTS

### E.1 Formulas

**County (Phase 2, n = 24):**
```
FDI_county = normalize(poverty_rate)                        × 0.25
           + normalize(mean(diabetes_pct, hypertension_pct)) × 0.25
           + normalize(pct_no_internet)                      × 0.20
           + normalize(vacancy_rate)                         × 0.15
           + normalize(pct_black)                            × 0.15
```

**Tract (v2.0, n = 15,507):**
```
FDI_tract = (D1_poverty + D2_income_deficit + D3_food_access
           + D4_health + D5_vacancy + D6_digital) / 6 × 100
```
where `normalize(x) = (x − corpus_min) / (corpus_max − corpus_min)`, and the tract formula contains **no racial composition variable**.

**Effective weights — disclosure correction (v1.4.2).** The six dimensions enter the tract formula at nominal 1/6 weights, but the D3 and D6 definitions each embed `pct_no_internet` (D3 = food_desert_proxy × 0.60 + pct_no_internet × 0.40; D6 = pct_no_internet), so the digital-exclusion signal carries an effective weight of (1/6 × 0.40) + (1/6 × 1.00) = **0.233** — nearly one-quarter, not the nominal one-sixth. No published score changes: this is a disclosure correction, not a formula change. Readers comparing "equal weighting" claims against the definitions should use 0.233 for the digital signal.

### E.2 The `% Black` variable, and the objection to it

The county formula includes Black population share at 15 percent weight as a structural-exposure proxy: the theoretical basis is that communities with higher Black population concentration have been subjected to greater documented disinvestment, redlining and exclusion, and that the variable therefore captures accumulated exposure to systemic risk rather than any intrinsic characteristic.

**The strongest objection is that this is partly circular.** An index that includes racial composition and is then used to demonstrate racial disparity in outcomes has assumed part of what it sets out to show. This objection is legitimate and is not dismissed here.

Two responses, offered as arguments rather than refutations. First, the tract instrument excludes the variable entirely and produces convergent results — the highest-distress tracts are overwhelmingly majority-Black without the formula being told to look for that. Second, the county weights were sensitivity-tested and alternative weight sets produce similar rank orderings among high-distress counties. Readers who find the objection dispositive should use the tract instrument, which was built partly for them.

### E.3 Humphreys County decomposition

| Component | Raw | Normalized | Weight | Contribution |
|---|---|---|---|---|
| Poverty | 35.0% | 1.000 | 0.25 | 0.250 |
| Health burden | 36.15% | 1.000 | 0.25 | 0.250 |
| Digital exclusion | 30.0% | 0.447 | 0.20 | 0.089 |
| Vacancy | 28.0% | 0.419 | 0.15 | 0.063 |
| Structural exposure | 80.0% | 0.964 | 0.15 | 0.145 |
| **Hand-calculated total** | | | | **0.797 → 79.7** |
| **Published score** | | | | **87.25** |

The decomposition above attributes the 7.5-point gap to approximate range endpoints and states that the published score normalizes against the full Phase 3 corpus. A v1.4.4 forensic recomputation disproves that explanation: the same five components, normalized against the corpus bounds actually present in the published Phase 3 file (42 counties — poverty 9.6→35.0, health burden 18.35→36.15, no-internet 8.1→49.8, vacancy 4.1→66.7, Black share 0.0→83.0), yield **80.69**, still 6.6 points below the published 87.25. The stated endpoints in this decomposition do not match the actual corpus bounds either (e.g. poverty 21.0→35.0 stated vs 9.6→35.0 actual; vacancy 12.3→49.8 stated vs 4.1→66.7 actual). No documented normalization of the published inputs reproduces 87.25. The published figure is the organization's published output; it is not a verified finding and should not be cited as one.

### E.4 Known defects in the published tract file

**Eight tracts carry imputation artifacts.** Each has `poverty_rate` filled to exactly 100.0 alongside `median_hh_income` filled to exactly $75,738.50 — the corpus median. Several also carry `pct_no_internet` at the corpus mean. These are rows where the Census returned suppressed or null values and the pipeline substituted a maximum for one field and a central-tendency fill for another.

| FIPS tract | City | Pop | FDI | Fills |
|---|---|---|---|---|
| 13215010606 | Columbus, GA | 1815 | 79.42 | poverty=100.0; income=corpus median; no_internet=100.0 |
| 36005031900 | Bronx, NY | 762 | 58.19 | poverty=100.0; income=corpus median; no_internet=100.0 |
| 06037980014 | Los Angeles, CA | 40 | 58.08 | poverty=100.0; income=corpus median |
| 45079010806 | Columbia, SC | 876 | 45.41 | poverty=100.0; income=corpus median; no_internet=corpus mean |
| 45079010408 | Columbia, SC | 4243 | 43.01 | poverty=100.0; income=corpus median; no_internet=corpus mean |
| 04013981000 | Phoenix, AZ | 696 | 42.22 | poverty=100.0; income=corpus median; no_internet=corpus mean |
| 12057010900 | Lakeland, FL | 7218 | 31.37 | poverty=100.0; income=corpus median |
| 12011980000 | Jacksonville, FL | 2 | 31.12 | poverty=100.0; income=corpus median; no_internet=corpus mean |

The first row is the highest-scoring tract in the entire published corpus. It reports 100 percent poverty, 100 percent without home internet, and a $75,738 median household income simultaneously — an impossible combination. It is a group-quarters tract on a military installation, and its score also sets the reported maximum for Columbus, Georgia in the published city rankings.

Because the tract instrument min–max normalizes across the corpus, an artificially maximal tract compresses every other tract's normalized position on the affected dimensions. These eight rows are flagged for exclusion in FDI v3.0, and the imputation logic will be rebuilt to fail loudly rather than fill silently.

*Correction (v1.4.4):* four of the eight tracts (45079010806, 45079010408, 04013981000, 12011980000) carry `pct_no_internet` = 5.879292, described above as "the corpus mean." The mean of the published corpus is 7.863, not 5.879. The "corpus mean" label is not verifiable against the published file and is withdrawn pending the v3.0 pipeline release.

**398 tracts (2.6 percent) have D4 health imputed to zero** where CDC PLACES data was unavailable. This is conservative in the wrong direction: it understates distress in precisely the data-sparse places most likely to be distressed.

**Food-desert proxy.** USDA FARA direct download returned HTTP 404 at collection time. The substitute is `food_desert_proxy = 1 WHERE poverty_rate ≥ 20% AND median_household_income ≤ $65,000`, approximating the USDA low-income/low-access standard. Every row carries a `food_desert_source` flag distinguishing proxy-assigned from FARA-confirmed designations.

### E.4a Reproducibility status

**The FDI outputs in this paper are not independently reproducible from the published package.** That is the finding of the September 2026 independent review and it is accepted here without qualification.

What exists publicly: the scored output CSVs, the formulas, the weights, the normalization method, the Humphreys decomposition and the enumerated defects. What does not yet exist publicly: the raw pre-scoring inputs with ACS table identifiers, release years and geography codes; the full Phase 3 corpus that supplies the normalization bounds; the transformation code with a dependency lockfile; and a deterministic command that rebuilds every published score from raw inputs.

Until that package is released, a reader can audit the *logic* of the FDI and cannot audit its *arithmetic*. The distinction matters and it is stated plainly: the 87.25 score for Humphreys County, the 15,507 tract scores and the 49 city rankings should be cited as this organization's published outputs, not as independently verified results. Producing that package is the first deliverable of FDI v3.0.

### E.5 Verified corpus counts

| Quantity | Value | Basis |
|---|---|---|
| Tracts scored | **15,507** | direct row count, `processed/farmblock_fdi_v2.csv` |
| Cities | **49** | direct row count, `processed/farmblock_city_rankings.csv` (48 distinct names; Columbus appears in GA and OH) |
| Counties, tract layer | 49 | pipeline manifest v2.1 |
| Counties, published county pilot | 24 | direct row count, `farmblock_fdi_phase2.csv` |

*These supersede the Stack Truth Table values of 15,578 and 50, which were locked April 18, 2026 and did not incorporate the version 2.1 removal of duplicated Selma, Alabama rows.*

### E.6 ACS provenance — what the repo records and what is still owed

The ACS table identifiers for the FDI's census-derived variables are recorded in the published package, in `data/farmblock-dataset/methodology/fdi_methodology_v2.json` (dated April 17, 2026). That file documents the FDI's ACS pull against the Census API endpoint `https://api.census.gov/data/2023/acs/acs5` with the variable list `B17001, B19013, B02001, B28002, B25002, B01003`, and maps each dimension to a table: poverty → B17001, median income → B19013, % Black → B02001, no internet → B28002, vacancy → B25002.

The vintage is confirmed independently by the output files. Every one of the 15,507 rows in `processed/farmblock_fdi_v2.csv` carries `source = "Census ACS 5-Year 2023"` and `pull_date = 2026-04-17`, with census-tract geography in `fips_tract` (11-digit FIPS). The county-level files (`data/farmblock-dataset/farmblock_fdi_phase2.json`, `farmblock_phase3_manifest.json`) record their sources as "Census ACS 5-Year 2022, CDC PLACES 2023, BLS LAU 2025"; `farmblock_fdi_phase2.csv` records `data_vintage = "2022-2023"` on every row with county geography in `fips` (5-digit FIPS). The Humphreys decomposition (`data/farmblock-dataset/methodology/HUMPHREYS_COMPOUND_DISTRESS_DECOMPOSITION.md`) confirms the county-level ACS values are 2022-vintage (Humphreys County: 35.0% poverty, $24,000 median income, 30.0% no internet, 28.0% vacancy, 80.0% Black share).

One provenance caveat is owed alongside the table. The methodology JSON's header describes the April 17 Phase 1 tract pull (12,426 tracts, 53 counties); the published tract file is the August 1 v2.1 dedupe (15,507 tracts, 49 counties; see E.5). Vintage and variable names match, but no per-file table audit exists to prove the v2.1 values were re-pulled with the same table list. That audit is owed.

**Per-variable ACS provenance**

| FDI variable | ACS table (repo-recorded) | Tract layer | County layer | Still owed |
|---|---|---|---|---|
| `poverty_rate` | B17001 — poverty status (`fdi_methodology_v2.json`) | ACS 5-Year 2023 | ACS 5-Year 2022 | variable-cell definition (which B17001 cells form numerator/denominator) |
| `median_hh_income` | B19013 — median household income (`fdi_methodology_v2.json`) | ACS 5-Year 2023 | ACS 5-Year 2022 | variable-cell definition |
| `pct_black` | B02001 — race (`fdi_methodology_v2.json`) | published column; not in the v2.1 tract formula | 15% formula weight | cell definition (Black alone vs. alone-or-in-combination) |
| `pct_no_internet` | B28002 — internet subscription (`fdi_methodology_v2.json`) | ACS 5-Year 2023 | ACS 5-Year 2022 | numerator/denominator cell definition |
| `vacancy_rate` | B25002 — housing occupancy/vacancy (`fdi_methodology_v2.json`) | ACS 5-Year 2023 | ACS 5-Year 2022 | variable-cell definition |
| `total_population` | B01003 — total population (API variable list only) | column present | n/a | role as denominator/control is not documented; no per-dimension mapping recorded |
| `food_desert_proxy` | not an ACS table — ACS-*derived* proxy | n/a | n/a | nothing: the proxy is fully documented — `1 WHERE poverty_rate >= 20% AND median_hh_income <= $65,000` — labeled per row in `food_desert_source`; the USDA FARA 2019 direct download returned HTTP 404 (see E.4) |
| health variables (`pct_diabetes`, `pct_high_bp`, `pct_obesity`, `smoking_pct`, `mental_health_pct`, `pct_food_insecure`) | **not ACS** — CDC PLACES 2023 (`health_source` column; `data/farmblock-data/methodology/METHODOLOGY.md`) | PLACES 2023, tract (D4 = mean of diabetes and high BP) | PLACES 2023, county (health_burden = diabetes + hypertension + obesity, 25% weight) | the repo labels `pct_food_insecure` as PLACES; that attribution is repo-stated and was not re-verified in this pass |
| `state_unemployment_rate` | **not ACS** — BLS Local Area Unemployment, 2025 | n/a | state level, county file only | BLS vintage confirmed in `farmblock_fdi_phase2.json` |

The % Black note: the Phase 1 tract run used B02001 at 1/6 weight (`fdi_methodology_v2.json`); the published v2.1 tract formula excludes it (`data/farmblock-data/methodology/fdi_manifest.json`; `data/farmblock-dataset/methodology/race_variable_note.md`) while the column remains published in the tract file. The county phase2/phase3 formula uses it as `Black_pct_proxy` at 15% weight.

The 2023 5-year release covers the 2019–2023 period and the 2022 5-year release covers 2018–2022 — the standard Census release-period mapping. The repo records release years; the period spans are stated here from the Census mapping, not from repo text.

**Owed inventory for FDI v3.0 (checklist)**

1. Variable-cell definitions for all six ACS variables at both geographies (numerator and denominator cells; whether margins of error were carried).
2. A county-pull table audit: confirm the phase2/phase3 county variables came from B17001/B19013/B02001/B28002/B25002 at the 2022 endpoint (`https://api.census.gov/data/2022/acs/acs5`) — the 2022 county pull currently has no table-ID record of its own.
3. The exact Census API query strings (`get=` and `for=` clauses).
4. The pull code: `code/step1_census_pull.py` is referenced in `data/farmblock-data/methodology/METHODOLOGY.md` but does not exist in the published package; the transformation pipeline and a dependency lockfile are owed.
5. The raw pre-scoring ACS inputs themselves — the core of what E.4a lists as missing. This section supplies the identifiers, vintages, geography codes, and endpoint; it does not supply the inputs.
6. Re-verification of the `pct_food_insecure` PLACES attribution.

Until items 1–5 are published, E.4a's finding stands unchanged: a reader can audit the *logic* of the FDI and cannot audit its *arithmetic*. What this section adds is the first half of the bridge — table IDs, release vintages, geography codes, and the API endpoint are now documented in the manuscript — so the remaining gap is enumerated rather than open-ended.

---

## APPENDIX F — PROVENANCE AND SEALS

| Asset | Contract | Token | Network |
|---|---|---|---|
| BDI Sovereign Dataset v1.0 | ExodusV4 `0x8582684C53912D496Df60C5B1B9Bb44D3d2f9B44` | #2 | Base Mainnet |

**Repositories, all CC0 1.0 Universal:**

| Repo | Layer | Contents |
|---|---|---|
| `IAMGODIAM/bdi-raw-data-vault` | Layer 1 | 18 raw federal source files, ~14,811 observations; reports and triage records |
| `IAMGODIAM/bdi-sovereign-dataset` | Layer 2 | 1,574 verified observations, 8 pillars; quantitative specification |
| `IAMGODIAM/farmblock-data` | Layer 3, tract | 15,507 tracts, 49 cities |
| `IAMGODIAM/farmblock-dataset` | Layer 3, county | 24-county published pilot |
| `IAMGODIAM/bdi-black-paper` | Layer 4 | This manuscript, drafts, peer review |

**Related campaign record:** the DC Package — nine policy packets delivered to congressional leaders and to Justice Clarence Thomas in July 2026, comprising a 166-page shared evidentiary record per packet — is published at `dc.e5enclave.com`. This paper is the empirical instrument underlying that record.

---

## APPENDIX G — ACKNOWLEDGMENTS AND INTELLECTUAL LINEAGE

W.E.B. Du Bois · Ida B. Wells · Harriet Tubman · Frederick Douglass · Nat Turner · Ella Baker · Malcolm X · James Baldwin · Cornel West · Melina Abdullah · The Movement for Black Lives

Ralph C. McCartney, Overtown, Miami · Congresswoman Carrie Meek · The Black Archives of South Florida · The Samuel Proctor Oral History Program, University of Florida

**Editor of the manuscript:** Elvia G. Brazil-Armstead, who read every draft by hand.

*Nil satis nisi optimum.*

---

## APPENDIX H — CORRECTIONS LEDGER

## A. ERRORS FOUND BY RECOMPUTATION (not previously flagged)

These are new. They were not in the April triage matrix; they surfaced when the drafts' arithmetic was rebuilt from the source series.

| # | Draft claim | Status | Verified value | Print-edition language |
|---|---|---|---|---|
| R-1 | "Black unemployment has never fallen below 2x the white rate" (Conclusion v2, v2.1) | **FALSE** | Ratio fell below 2.0 in **17 of 54 years**; low 1.576 (2020) | "The ratio has ranged from 1.58 to 2.56 and averaged 2.115 across 54 years. It has never inverted — not in one month of one year." |
| R-2 | "Below 1.86, no normal economic year has gone in more than half a century" (Report 3, Adj. 3) | **FALSE** | 2023 = 1.683, 2024 = 1.666 — both normal expansion years | Floor language removed. Replaced with the distributional statement above. |
| R-3 | "3,015 Black Americans killed by police 2013–2023; 377 unarmed" | **UNDERCOUNT** | Vault row sum: **3,496 killed; 397 unarmed** | Corrected to 3,496 and 397; aggregate Black share 26.7% of 13,096 total. |
| R-4 | "Incarceration ratio has never fallen below 5.7" | **FALSE** | 1991–2022 window minimum **5.80 (2018)**; full 1925–2022 series minimum 5.44 (1940); maximum 7.70 (2000) | "In the empirical window the ratio has not fallen below 5.8. Across the full 97-year series it has ranged 5.44 to 7.70." |
| R-5 | "Homeownership gap stands at 30.1 points today" | **WRONG VINTAGE** | ACS 2022: **28.9 pp**; ACS 2023 (NAR): 44.7% vs 72.4% = **27.7 pp** | "28.9 percentage points (ACS 2022); 27.7 points on the 2023 release." |
| R-6 | "Wealth ratio reaches parity in approximately 263 years" | **ARITHMETIC ERROR**, then **WITHDRAWN ENTIRELY** (see W-1) | The 263-year figure was miscalculated; the recomputed 868-year figure rested on a defective series; the corrected series yields 274 years from 1989 but 1,632 from 1992 and no convergence from 2001 | No parity horizon is asserted. The sensitivity table is printed in §5.1 instead. |
| R-7 | "The gap tripled in absolute dollars" | **IMPRECISE**, then **SUPERSEDED** (see W-1) | Nominal 2.893×; in constant 2022 dollars **1.55×**, $154,830 → $240,120 | "The absolute gap widened by $85,290 in real terms and is the widest in the series." |
| R-8 | "COVID erased 20 years of life expectancy gains in 18 months" | **TIMELINE WRONG** | Black life expectancy fell **4.0 years** across **two calendar years** (74.8 → 70.8, 2019→2021), returning to a mid-1990s level | "Between 2019 and 2021 — two years, not eighteen months — Black life expectancy fell four full years, to a level last seen in the mid-1990s." |
| R-9 | "NAEP gap... exists in 2022 as it did in 1992" (Conclusion) | **OVERSTATED** | G8 reading gap narrowed 29.6 → 24.5; G8 math 40 → 32; G4 reading 32 → 28 | Movement acknowledged and quantified; convergence rate stated. |
| R-10 | "Eviction rate three times the white rate" | **SCOPE UNSTATED** | Eviction Lab 2000–2016: 3.00–3.54×. Graetz et al. 2023 PNAS: ~4× evictions, ~4.8× filings | Both cited with explicit scope and instrument. |

---

## B. TRIAGE MATRIX RULINGS APPLIED (April 18, 2026 — 27 claims)

| ID | Ruling | Print-edition disposition |
|---|---|---|
| E-1 | source-confirmed → **REVERSED** (see W-1) | The 1989 endpoint could not be reconciled to the Federal Reserve's published race-specific medians under either price basis. Table rebuilt from the Fed's constant-2022-dollar series. |
| E-2 | source-confirmed | ~30 pp restated as 28.9 pp (ACS 2022) per R-5. |
| E-3 | source-conflicted | "Ranged 2.24 to 2.84 across ACS 2005–2022" — no "never below 2:1" absolute. |
| E-4 | source-confirmed | 1968 ≈ 24 pp vs 2022 28.9 pp. Both vintages footnoted. |
| H-1 | source-confirmed | 69.9/100K locked to **2021**; 2022 = 49.5 shown; NCHS 2024 trajectory noted. |
| H-2 | source-conflicted | Rewritten per R-8. |
| H-3 | source-conflicted | Fence-line tract geography specified: 65–94% Black (St. James Districts 4–5); parish ≈44%. |
| CJ-1 | source-conflicted | Rewritten per R-4. |
| ED-1 | source-conflicted | 24-point gap and century-plus parity horizon — **independently confirmed against the live NAEP API** (see §C). |
| HO-1 | source-confirmed | HMDA denial ratio; range 2.01–2.36 stated rather than a single figure. |
| HO-2 | source-conflicted | Rewritten per R-10. |
| HO-3 | internally-derived | **$4.5B aggregate removed.** Replaced with HUD OIG 2013-AT-0003: 53% of PHAs did not file required Section 3 reports. |
| HO-4 | source-conflicted | "Erased a decade in 18 months" → "reversed nearly a decade of gains across the 2007–2013 window." |
| HI-1 | source-conflicted | Embarked/disembarked disambiguated: 12,521,337 / 10,702,656 / 1,818,681 lost (14.5%). |
| HI-2 | source-confirmed | 1514 anchor retained with footnote. |
| EN-1 | citation-vintage | EJScreen cited via Public Environmental Data Partners; EPA.gov removal (Feb 5, 2025) disclosed. |
| CD-1 | source-confirmed | Humphreys 78.6% (ACS 2022). |
| CD-2 | source-confirmed | Detroit 77.1%. |
| CD-3 | source-confirmed | East St. Louis 97.4%. |
| CD-4 | source-confirmed | Claiborne 86.1%. |
| CD-5 | source-conflicted | Same fix as H-3. |
| CD-6 | citation-vintage | **32.1% all-persons and 55.0% child poverty (ACS 2022)** adopted as the citation figures; 36.4% (ACS 2015–2019) retained as the historical vintage; ACS 2024 5-year now reports 27% ±6.3 — disclosed as the current release. |
| CD-7 | source-confirmed | Hospital closure 2013 (HRSA AHRF). |
| CD-8 | source-conflicted | "No grocery within 15 miles" → USDA FARA low-income/low-access (LILA) designation. |
| CD-9 | internally-derived → **published** | Humphreys score corrected **83.5 → 87.25** and the full five-component decomposition printed as Appendix E. |
| META-1 | source-confirmed | **1,855 → 1,574** verified empirical observations, everywhere. |
| META-2 | internally-derived | "MiroFish 94%" removed. Replaced with the dual-source protocol description. |

---

## B2. SECOND-WAVE CORRECTIONS — INDEPENDENT REVIEW (v1.2)

On September 1, 2026 an independent review of the v1.1 print edition was conducted by Manus AI, working only from the published PDF, the corrections ledger and the supplied git bundle — with no access to this project's repositories. It found problems the internal audit had missed, and its principal finding is the most material error yet identified in this paper. The findings are adopted below.

**Why the internal audit missed them.** The recomputation pass described in §A verified that every derived figure followed correctly from the vault's stored series. It did. What it never asked was whether a stored series was itself coherent, or whether it reconciled to the agency's published figures. An internal consistency check cannot detect an incoherent input. The audit protocol is amended: **primary-source reconciliation of every series endpoint is now a required pass.**

| # | Claim | Finding | Print-edition disposition |
|---|---|---|---|
| **W-1** | **Table 5.1, the SCF wealth series; the "$83,000 → $240,100" gap; "nearly tripled"; the 3.2-cent ratio gain; the 868-year parity horizon** | **CRITICAL — series defective.** The table stated no price basis. Its 1989 endpoint ($12k / $95k) was nominal while its 2022 endpoint ($44.9k / $285k) was the Fed's constant-2022-dollar figure — a real endpoint back-filled with nominal history, whose apparent trend was substantially an inflation artifact. Worse, deflating the old 1989 values to 2022 dollars yields $28,321 and $224,211 against the Fed's published $9,200 and $164,030 — so they reconcile under **neither** basis, and their provenance was undocumented. | **Table rebuilt in full** from Federal Reserve FEDS Notes (Oct 18, 2023), Figure 2, constant 2022 dollars, families. Corrected findings: real gap **$154,830 → $240,120** (1.55×, +$85,290, widest in the series); ratio **0.056 → 0.158** (nearly tripled); Black median wealth **+388%** vs white **+74%**. The "nearly tripled gap," the 3.2-cent gain and the 868-year horizon are all withdrawn. |
| **W-2** | Parity projections (wealth and NAEP) | Presented with insufficient warning that they are mechanical extrapolations. The wealth horizon proves extremely baseline-sensitive: 274 years from 1989, 1,632 from 1992, 1,511 from 1995, 366 from 2007, 117 from 2013, and **no convergence at all** from 2001. | **No wealth parity horizon is asserted.** The full sensitivity table is printed in §5.1. The NAEP 144-year figure is retained but explicitly labelled an arithmetic extension of two endpoints, not a forecast. |
| **W-3** | Incarceration ratios, and "Black Americans were imprisoned at 6.31 times the white rate" | **Definition unverified and probably overstated in scope.** BJS publishes, for 2022, **1,196 per 100,000 Black adult residents and 229 per 100,000 white adult residents — a ratio of 5.22.** The series' 1,862 and 295 correspond closely to BJS *male* rates (≈1,826 and 279). The vault does not record the denominator, and the Cahalan (1986) pre-1980 crosswalk is undocumented. BJS also dates its series to 1926, not 1925. | Chapter 6 now prints the BJS all-adults ratio of **5.22** alongside the series ratio of 6.31, states that the basis is probably male rates, and stops writing "Black Americans" where the source may say "Black males." The stability finding, which holds on either basis, carries the argument. **Superseded by v1.4.4 (Fifth-Wave section):** denominator forensics established male imprisonment rates as the series basis (vault `population_basis` field); the 2022 endpoint was corrected to BJS-published 1,826/337 (ratio **5.42**) — the prior 1,862/295 matched no BJS table. The 1926 series-start claim was already corrected back to 1925 in v1.4.3 (§G). |
| **W-4** | 1930 maternal mortality ratio of 1.48, and the 1.76-fold widening | The pre-1933 figures come from the birth-registration states only, which were not nationally representative. The cross-era comparison is not strictly commensurable. | **Withdrawn and replaced in v1.4.3 (see §G).** The 1.48 figure could not be verified as maternal mortality at all: the verification review traced it to the neonatal-mortality literature (Shin 1975, Table I: nonwhite/white neonatal ratio 1.48 for 1939–41), and complete national maternal reporting by race begins in 1933. The 1915 and 1930 rows are removed; the series now opens at 1933 (Black 1,000.0 / White 564.0 = 1.77, national vital statistics via MacDorman et al. 2021). The widening is restated as 1.47-fold over eighty-nine years. The 2022 ratio remains confirmed directly against NCHS (49.5 ÷ 19.0 = 2.605 → 2.61). |
| **W-5** | Unemployment ratios shown beside rounded annual rates | 5.5 ÷ 3.3 = 1.667, not the 1.683 printed. The discrepancy arises because ratios are computed from unrounded monthly data while the displayed component rates are rounded annual averages. | Aggregation rule now stated explicitly in §5.2, with the worked 2023 example (5.5167 ÷ 3.2750 = 1.685) and a vintage-revision note. The stored values are correct; the method was undisclosed. |
| **W-6** | Black farmland "13.5 million acres lost, 1910–1997" | The 15-million-acre peak's year and level are contested; some compilations place the maximum nearer 1900. | Note added. The 1997 figure of 1.5 million is well supported; the 90 percent loss is now framed against a peak carrying acknowledged uncertainty in year and level. |
| **W-7** | NAEP endpoint precision and comparability | NCES publishes rounded scores (267/237, 268/244) and discloses that 1992 permitted no testing accommodations while later years did. | Both disclosed in §6.6. |
| **W-8** | The supplied git bundle | **Unusable for independent review.** It was created incrementally (`main..branch`) and declares a prerequisite commit the reviewer did not have, so the repository tree, raw vault JSON and manifests could not be inspected at all. | Replaced with a **complete-history bundle** requiring no prerequisite. This was the single largest obstacle to the review and it was an avoidable packaging error. |
| **W-9** | Introduction's "Five Compound Catastrophe Zones" heading | Flagged as an apparent contradiction with the Chapter 7 ranking. | **Already corrected before the review was received** — the reviewer worked from the superseded v1.1 PDF. The Introduction now names the instrument's actual top five and states the withdrawal. |

**Findings acknowledged and not yet closed.** The review's three "critical" reproducibility actions are only partly satisfied by this edition. The complete bundle (W-8) addresses repository access. It does **not** yet supply a full data package for the FDI computation — raw inputs, normalization bounds, transformation code and a deterministic rebuild command — nor ACS table identifiers and geography codes for every Humphreys input. Until those exist, the correct characterisation is the reviewer's: **the FDI outputs are not independently reproducible from the supplied package.** Appendix E says so.

---

## C. LIVE FEDERAL-SOURCE VERIFICATION (August 2026)

| Series | Endpoint | Result |
|---|---|---|
| Black unemployment (LNS14000006) | BLS via FRED, monthly 2019–2025 | Annual averages reproduce the vault series. 2019 = 6.1, 2023 = 5.5, 2024 = 5.9, 2025 = 6.9. **Confirms vault.** |
| White unemployment (LNS14000003) | BLS via FRED, monthly 2019–2025 | 2019 = 3.3, 2023 = 3.3, 2024 = 3.6, 2025 = 3.7. **Confirms vault.** Ratios recomputed from live monthly data reproduce R-1 and R-2. |
| NAEP G8 reading by race, national | NCES Nation's Report Card data service | **1992:** White 267.001, Black 237.374 → gap **29.63**. **2022:** White 268.443, Black 243.902 → gap **24.54**. Confirms ED-1 exactly: the gap is ~24 points, not 20. Convergence 5.09 points in 30 years → **~144 years to parity**, not 64. |
| Humphreys County, MS (FIPS 28053) | Census ACS 5-year profile | Current release reports 27% ±6.3 poverty, median household income $33,731, population 7,395. Wide margin of error at this population size disclosed in text. |
| Homeownership by race | ACS 2023 via NAR *Snapshot of Race and Home Buying in America* (2025) | Black 44.7%, White 72.4% → 27.7 pp. Confirms direction; updates the vintage. |

**Note on API access.** The Census Bureau data API now requires a registered key for programmatic access; the figures above were verified against the Bureau's published profiles and released tables rather than by unauthenticated API call. The vault's underlying ACS pulls (committed April 2026) remain the citation of record for the series tables, and each is footnoted to its table number.

---

## D. STRUCTURAL ADDITIONS

| Item | Action |
|---|---|
| Chapters 5, 6, 7, 8 | **Drafted** from the locked outline; previously stubs. |
| Introduction | **Drafted**; previously a stub. |
| Appendices A–H | **Drafted**; previously stubs. |
| Report 3 drafting directives 3–8 | Executed inside the new chapters (unemployment distribution, maternal mortality reversal, COVID reversal, housing headline, Shelby inflection, three historical anchors). |
| Scope statement (Adj. 1) | Introduction now states the nested window: 1991–2024 core, with series to 1900 (health), 1925 (justice), 1940 (housing), 1964 (political), 1514 (historical). |
| Chapter 2 longitudinal claim (Adj. 2) | Added. |

---

## E. WHAT A REVIEWER SHOULD STILL CONTEST

Disclosed, not concealed. A sovereign record that hides its soft edges is promotional, not empirical.

1. **The `% Black` variable at 15% weight in the county FDI.** Defended as a structural-exposure proxy in Appendix E; a reviewer may reasonably argue it makes the instrument partly tautological with respect to racial concentration. The tract instrument excludes it — compare the two.
2. **Equal weighting in the tract FDI.** A transparent baseline, not an empirically derived one. PCA weighting is the stated v3.0 path.
3. **The Humphreys decomposition reproduces 79.7 against the decomposition's stated endpoints, and 80.69 against the actual full Phase 3 corpus bounds — not the published 87.25.** The earlier formulation ("The published score stands on the full-corpus normalization") is withdrawn: the full-corpus normalization does not reproduce the published score either. The 87.25 figure is the organization's published output, not an independently verified result.
4. **D4 health imputed to zero** where CDC PLACES is unavailable — conservative, but it understates distress in data-sparse tracts.
5. **The food-desert proxy** substitutes an ACS income/poverty threshold for a FARA download that 404'd at collection. Rows are flagged.
6. **Mapping Police Violence is not a federal instrument.** It is the most complete public database of its kind, and it is labeled as non-federal wherever cited.
7. **Small-county ACS margins of error** — Humphreys' poverty estimate carries a ±6.3-point margin. Stated in text.
8. **The incarceration series' denominator is established as male imprisonment rates** (v1.4.4 forensics; BJS *Prisoners in 2022* Table 13). The series' 2022 ratio is 5.42 against BJS's all-adults 5.22. The pre-1980 Cahalan crosswalk is carried as compiled.
9. **The FDI computation is not independently reproducible** from the published package (see Appendix E.4a). The reviewer's characterisation is adopted verbatim.
10. **The pre-1933 maternal mortality rows were withdrawn in v1.4.3** (W-4, §G): the 1930 ratio of 1.48 traced to the neonatal-mortality literature, and complete national maternal reporting by race begins in 1933.
11. **Table 5.1 now depends on a single secondary presentation** of the SCF — the Federal Reserve's own FEDS Note — rather than on an extraction from SCF microdata performed by this project. That is an improvement in provenance and a reduction in independence. A microdata extraction with published code is owed.

## F. THIRD-WAVE CORRECTIONS — SECOND INDEPENDENT REVIEW (v1.4.2)

A second independent review (September 2026), conducted with full repository access, returned five findings. Two concerned the archived data snapshot and were corrected in the data layer; three concerned the manuscript text and are corrected here. No empirical finding changes.

| # | Finding | Resolution | Location |
|---|---|---|---|
| P-1 | The raw vault still served the withdrawn SCF splice as the operative wealth series, with no deprecation marker | The withdrawn key is retained byte-identical for audit history; a dated deprecation notice was added; the corrected 12-wave FEDS-Notes series (constant 2022 dollars) was added under `scf_wealth_gap_1989_2022_FEDS2023_constant2022`. Table 5.1 recomputed from the vault reproduces the printed figures exactly. | Vault JSON; Appendix A, item 5 |
| P-2 | The manuscript omitted the project's existing 17-state BDI ranking | The full ranking is now printed as Appendix I. | Appendix I |
| P-3 | The tract FDI's effective weights did not match the "equal weighting" description | Appendix E now discloses the effective digital-exclusion weight of 0.233 (nominal 1/6). No score changes. | Appendix E, §E.1 |
| P-4 | The sealed dataset's validation string still showed the stale Humphreys compound score of 83.5 | Dataset resealed as v1.1-RESEALED; the validation string now reads FDI 87.25 / compound 83.53. The two stale in-text figures (FarmBlock methodology chapter, claim-triage matrix) were corrected. | Sovereign dataset; Appendix A |
| P-5 | The narrowed incarceration population basis was not propagated consistently | The Conclusion and Appendix C now state the male-rates basis; the all-adults ratio of 5.22 is printed alongside the series ratio of 5.42 (corrected from 6.31 in v1.4.4). **Superseded in part by v1.4.3 (§G):** the 1926 series start taken from the review is corrected back to 1925 — 1926 begins BJS's *Prisoners report series*; the BJS Historical Corrections Statistics *data* covers yearend 1925. | Conclusion; Appendix C |

On the withdrawn series: it was replaced because the 1989 wave is not comparable to later waves for this purpose (the published ratio jumps from 0.056 to 0.142 in the single step to 1992) and because the series as stored was in mixed current-year dollars across waves. The replacement is the Federal Reserve's own constant-dollar presentation. This improves provenance at the cost of independence — see item 11 of Section E.

## G. FOURTH-WAVE CORRECTION — MATERNAL MORTALITY BASELINE (v1.4.3)

An independent verification review (September 2026) found that the 1930 maternal mortality ratio of 1.48, carried since the first edition, could not be verified as a maternal-mortality figure. The project's evidence-domain verification file (`review/verify_claims_by_evidence_domain.csv`) had already associated the 1.48 ratio with neonatal mortality; primary-source research confirmed 1.48 as the documented nonwhite/white neonatal mortality ratio for 1939–41 (Shin 1975, Table I), and confirmed that complete national maternal mortality reporting by race begins in 1933, not 1930 — the first year every state reported maternal deaths, with Black 1,000 and White 564 per 100,000 live births, a ratio of 1.8 (MacDorman et al. 2021). The 1915 row (1.75) was likewise pre-registration and unsourced. Both rows are withdrawn.

Table 6.1 now opens in 1933 (Black 1,000.0 / White 564.0 = 1.77; the 1933 classification is the period "negro" category). The cross-era widening is restated: 1.77 → 2.61, a factor of 1.47 over eighty-nine years, replacing the 1.76-fold figure. The direction of the finding — the ratio is higher in 2022 than in every earlier decade of the table — is unchanged, as is the fully-registered 2010→2022 rise (2.24 → 2.61). The vault file retains the withdrawn rows with dated withdrawal notices.

**The 1926 series start adopted in v1.4.2 is corrected back to 1925.** The second independent review stated that "BJS dates its series to 1926, not 1925," and v1.4.2 applied that to the Conclusion and Appendix C. Verification in this edition established the distinction: 1926 is the start of BJS's *Prisoners report series* ("the 95th report in a series that began in 1926," BJS via OJP); the underlying BJS Historical Corrections Statistics *data* covers yearend 1925 ("Historical Statistics on Prisoners in State and Federal institutions, Yearend 1925–1986"; Sourcebook Table 3-7, "1925–1982"). The series' first observation (1925: 142/22, ratio 6.45, via Cahalan 1986) is therefore genuine BJS historical data, and the manuscript is restored to 1925 / ninety-seven years throughout. The pre-1980 Cahalan crosswalk remains carried as compiled; the denominator question (W-3; Section E item 8) was resolved in v1.4.4 (§H.2) as male imprisonment rates.

## H. FIFTH-WAVE CORRECTIONS — "ROAD TO 10" FORENSIC PASS (v1.4.4)

A strict-gate audit scored this paper 7/10 and named four deductions: the FDI's reproducibility (−1.5), the incarceration denominator (−0.5), causal language exceeding the observational design (−0.5), and provenance/process gaps (−0.5). This edition resolves what can be resolved and writes down what cannot. Nothing below fabricates a reconciliation.

### H.1 FDI forensic pass: honestly unreproducible → demoted

An exhaustive forensic pass attempted the first independent reproduction of the flagship Humphreys County FDI score (87.25) from the published package using only documented methods. **The reproduction failed.** Findings:

- **No computation code exists in the package.** The only Python file is the print-edition builder. `fdi_methodology_v2.json` asserts a reproducibility command (`python3 farmblock_pipeline_v2.py`) for a script that does not exist anywhere in the repository. No R scripts, notebooks, or lockfiles exist.
- **Four recomputation attempts, all documented:** the documented county formula against true Phase 3 corpus bounds (42 counties) yields **80.69**; with obesity in the health burden, **80.69**; against Phase 2 corpus bounds (24 counties), **82.97**; the decomposition document's own hand calculation, **79.7**. None reproduces 87.25.
- **The decomposition's explanation is falsified.** Appendix E §E.3 attributed the gap to approximate range endpoints, asserting the published score normalizes against the full Phase 3 corpus. The full-corpus recomputation (80.69) disproves that. The §E.3 closing paragraph is replaced in this edition, the "citation of record" language struck, and Appendix H §E item 3 rewritten.
- **Imputed tracts confirmed** against the published file, with one new sub-finding: four tracts carry a no-internet fill of 5.879292 described as "the corpus mean," but the corpus mean is 7.863. The label is withdrawn (§E.4 correction).

Per the project's rule — strike what cannot be verified — the FDI is **demoted** from headline contribution to the organization's exploratory instrument. Chapter 7 now introduces it as such, with scores labeled published outputs, "not verified findings" and "not to be cited as findings"; the introduction's and conclusion's five-county passages are reframed accordingly; the abstract reports rather than contributes the index; Limitation 9 (Chapter 3) prints the failed recomputation. Appendix E §E.4a's standing ("cited as this organization's published outputs, not as independently verified results") is unchanged and now consistent with every FDI mention in the manuscript.

Unresolved: no pipeline code; no documented derivation of 87.25; circularity (E.2), effective-weight (E.1), and imputation-artifact (E.4) disclosures stand; methodology-file inconsistencies flagged but not in scope (the JSON's tract formula includes a racial variable §E.1 says is excluded; its 12,426/53 counts contradict the verified 15,507/49; BDI_QUANT_SPEC.md §2 cites 15,578/50).

### H.2 Denominator forensics: the series is male rates — and the 2022 endpoint was wrong

Cell-for-cell comparison against BJS Prisoners-series tables **definitively establishes** the 1925–2022 series as **male imprisonment rates** (sentenced state/federal prisoners per 100,000 same-race male residents): the vault's 2000, 2008, 2010 rows match *Prisoners in 2010* Appendix Table 14 male columns exactly; 2016 matches *Prisoners in 2016* Table 10; 2018 matches published male rates (2,272/392). The vault records this in a new `population_basis` field with a dated v1.4.4 note.

The same comparison exposed a material error: the vault's 2022 row (1,862/295, ratio 6.31) matched **neither** BJS Table 13 male rates (1,826/337) **nor** Table 6 all-adult rates (1,196/229, ratio 5.22). Corrected to **1,826/337/5.42**; the 2020 white rate corrected to BJS-published 332 (ratio 5.67). Consequences: the cross-era movement is **6.45 → 5.42, 1.03 points** (not 0.14); the series range is 5.42–7.70; decarceration from the 2000 peak is **47 percent** (not 46). Chapter 6, Chapter 4, the Conclusion, Chapter 8, the README, the abstract, and Appendix C are corrected throughout; the W-3 ledger row and P-5 are annotated as superseded; §E item 8 is updated. The core finding survives: a ratio above five-to-one for ninety-seven years. The "refused to move" framing, built on the erroneous 6.31, is withdrawn.

Boundary: pre-1980 rows remain carried from the Cahalan 1986 compilation (sex-scope docs not re-verified); the 2020 Black-male cell is consistent with BJS's published 5.7× ratio but not cell-verified — both flagged in the vault note.

### H.3 Provenance: §E.6 and the narrowed E.4a gap

New Appendix E §E.6 records what the package already contained but the manuscript never stated: ACS table IDs (poverty B17001, income B19013, % Black B02001, no-internet B28002, vacancy B25002), vintages (tracts ACS 5-Year 2023; counties ACS 5-Year 2022), geography (11-digit / 5-digit FIPS), with health components identified as CDC PLACES 2023 (not ACS) and the food-desert variable as an ACS-derived proxy. A six-item owed inventory for FDI v3.0 (cell definitions, county table audit, query strings, pull/transform code, raw inputs, PLACES attribution check) is printed. E.4a's finding stands, narrowed: identifiers, vintages, and geography codes are now public; inputs and code are still not.

### H.4 Integration sweep and frozen artifacts

Correcting the 2022 endpoint required propagating 5.42 / 1.03 / 47% through every live surface (manuscript, README, abstract, Appendix C, ledger annotations). Two artifacts could not be touched: `errata/RECOMPUTATION_LOG.md` and the `review/` verification files are read-only by project constraint and still carry the superseded 6.31/0.14 figures — they are frozen at v1.4.2/v1.4.3 and documented here as stale rather than silently left.

## APPENDIX I — THE 17-STATE BDI RANKING

The BDI composite index ranks seventeen states with sufficient Black-population data density for the full eight-pillar computation. The ranking is computed in the sealed sovereign dataset (`bdi-sovereign-dataset/bdi_sovereign_dataset_v1.json`, `data.bdi_composite_index.ranked`) and was previously cited in the text without being printed. It is printed here in full.

| Rank | State | BDI composite | Black share of state population |
|---|---|---|---|
| 1 | Michigan | 86.54 | 14.0% |
| 2 | Louisiana | 84.85 | 32.7% |
| 3 | Illinois | 84.44 | 14.7% |
| 4 | Ohio | 84.37 | 13.0% |
| 5 | Mississippi | 79.82 | 37.8% |
| 6 | Arkansas | 78.36 | 15.7% |
| 7 | Missouri | 76.91 | 11.8% |
| 8 | Alabama | 75.68 | 26.8% |
| 9 | New York | 75.29 | 17.6% |
| 10 | South Carolina | 73.46 | 26.5% |
| 11 | Tennessee | 72.91 | 17.1% |
| 12 | North Carolina | 67.45 | 21.5% |
| 13 | Texas | 66.97 | 12.9% |
| 14 | Georgia | 65.78 | 32.6% |
| 15 | Florida | 61.29 | 16.9% |
| 16 | Virginia | 58.70 | 19.9% |
| 17 | Maryland | 58.28 | 31.1% |

Read the ranking as the instrument reads it: Michigan's first-place score does not mean Michigan is "worse for Black people" in every dimension — it means the eight-pillar composite, as weighted, concentrates most severely there. The Deep South states that dominate the historical narrative (Mississippi 5th, Alabama 8th, Georgia 14th) rank below the industrial Midwest on the contemporary composite, which is itself a finding: the geography of structural distress has moved with the Great Migration's destinations.

---

*E5 Enclave Incorporated · EIN 99-3822441 · CC0 1.0 Universal*
