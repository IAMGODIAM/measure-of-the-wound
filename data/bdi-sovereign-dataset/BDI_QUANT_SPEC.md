# BDI QUANTITATIVE SPECIFICATION
**Publisher:** E5 Enclave Incorporated | EIN 99-3822441
**Version:** v1.0 | **Date:** April 18, 2026
**DAG:** bdi-quant-spec-v1-2026-0418
**License:** CC0 1.0 Universal

---

## 1. SCOPE AND PHILOSOPHY

The Black Distress Index is a **layered forensic system**, not a single flat score.

It is designed to serve three simultaneous functions:
1. Document long-run structural pattern (Product A — National Structural Record)
2. Synthesize across pillars into comparable scores (composite layer)
3. Operationalize distress at the place level for intervention prioritization (Product B — Place Distress Instrument)

**Primary framing:** Place-based structural intervention prioritization system
**Secondary framing:** Structural distress index
**Historical framing:** Black community disinvestment targeting framework (contextual use only)

This index is a **correlation instrument**, not a causal model. It identifies co-occurrence of structural conditions. It does not claim any dimension causes any other.

---

## 2. LAYERED ARCHITECTURE

### Layer 1 — Sovereign Raw Evidence
**Repo:** `bdi-raw-data-vault`
**Unit:** Series-level observations (annual, decennial, event-count, aggregate)
**Rule:** Primary source committed unmodified before analysis. No scoring at this layer.
**Content:** BLS unemployment, Census poverty/income/homeownership, NCHS life expectancy/maternal mortality, BJS incarceration, MPV police killings, NAEP education, HMDA mortgage denial, Slave Voyages aggregate, Tier 1/2/3 geographic expansion

### Layer 2 — Pillar Metric Layer
**Repo:** `bdi-sovereign-dataset`
**Unit:** Flagship metrics per pillar — disparity ratios, percentage-point gaps, absolute burden metrics
**Rule:** Each pillar contains 1–3 core metrics with explicit source, vintage, geography, and transform documentation
**Formula:** See Section 4

### Layer 3 — Place-Level Compound Distress Layer
**Repo (tract):** `farmblock-data` — 15,578 tracts, 50 priority cities
**Repo (county):** `farmblock-dataset` — county-level scored release
**Unit:** FDI composite score 0–100 per tract or county
**Formula:** See Section 5

### Layer 4 — Forensic Narrative
**Repo:** `bdi-raw-data-vault/reports/`
**Unit:** Analytical reports, manuscript adjustment memos, scientific record

---

## 3. DATA POINT COUNTING RULE

**Definition:** One data point = one row in a time series or one unique observation record.

**Explicit inclusions:**
- Annual unemployment series: each year = 1 point
- Decennial homeownership: each census decade = 1 point
- Life expectancy by race by year: each year × race = 1 point
- Maternal mortality by year: each year = 1 point
- NAEP score by year by grade: each year × grade = 1 point

**Explicit exclusions from the "data point" count:**
- JSON metadata keys (source, pillar, notes, verification_note, etc.)
- Text-only records with no numeric observation
- Duplicate series committed from the same source in different files

**Counting result (v1.0):**
- Raw vault: ~14,811 observations across 17 files (see VAULT_MANIFEST.json)
- Sovereign dataset (empirical observations only): 1,574 counted records
- Previously claimed 1,855: included metadata keys as data points — this was incorrect
- Corrected public claim: "1,574 verified empirical observations across 8 pillars"

---

## 4. BDI NATIONAL COMPOSITE — FORMULA AND WEIGHTS

### Formula (Product A — National/State scoring)
```
BDI_score = Economic×0.20 + Health×0.20 + CriminalJustice×0.20 +
            Education×0.15 + Housing×0.10 + Environmental×0.10 + Political×0.05
```

### Weighting rationale
| Pillar | Weight | Rationale |
|--------|--------|-----------|
| Economic | 20% | Foundational structural driver; wealth/income/unemployment are upstream of most other disparities |
| Health | 20% | Life expectancy and maternal mortality represent irreversible outcomes of structural burden |
| Criminal Justice | 20% | Incarceration and police violence represent direct state-imposed structural harm |
| Education | 15% | Transmission mechanism of inequality across generations |
| Housing | 10% | Shelter security and homeownership are wealth-building prerequisites |
| Environmental | 10% | Toxin exposure is concentrated in Black communities by documented policy (see EJScreen) |
| Political | 5% | Participation data is noisier and more subject to voter registration complexity |

### Normalization
Each pillar score normalized 0–100 (100 = highest burden).
Within each pillar: min-max normalization across comparison universe.

### Sensitivity analysis
Three weighting scenarios are published alongside the baseline:
1. **Equal weights (1/7 each)** — most conservative, fully auditable
2. **Analyst weights** — as above (20/20/20/15/10/10/5)
3. **Outcome-weighted** — Education and Health at 25% each, others proportional

---

## 5. FDI PLACE-LEVEL FORMULA (Product B)

### Tract-level formula (farmblock-data)
```
FDI = (D1_poverty + D2_income_inv + D3_food_access + D4_health + D5_vacancy + D6_digital) / 6 × 100
```
- Equal weight 1/6 each
- Min-max normalized per dimension across all tracts in dataset
- **% Black population is NOT included** in the tract formula
- Missing D4 (CDC health): set to 0 and flagged (conservative)

### County-level formula (farmblock-dataset)
```
FDI_county = (poverty×0.25 + health_burden×0.25 + digital_exclusion×0.20 +
              vacancy×0.15 + Black_pct_proxy×0.15)
```
- **% Black population IS included** at 15% weight as a structural exposure proxy
- This captures the geographic concentration of communities with documented disproportionate disinvestment exposure
- It is NOT a biological claim. It is NOT a causal variable.
- See `methodology/race_variable_note.md` for full documentation

### Why the two formulas differ
- Tract formula: designed for precision operational targeting — % Black would artificially concentrate scores in already-selected majority-Black cities; the six structural dimensions are sufficient
- County formula: designed for broad distress detection across diverse geographies — % Black as exposure proxy helps identify counties that institutional indices under-weight

---

## 6. % BLACK POPULATION — CANONICAL TREATMENT

When `% Black population` appears in any FDI or BDI score:
- It is a **structural exposure proxy** — a geographic marker
- It identifies places where populations with documented disproportionate disinvestment exposure are concentrated
- It does NOT assert that racial composition causes distress
- It does NOT make a biological claim
- It is consistent with a 100-year federal data record of racialized policy outcomes

**Sensitivity test:** Rankings computed with % Black weight zeroed. Counties whose rank changes by >2 deciles are flagged as "race-exposure-sensitive" in the manifest.

---

## 7. HISTORICAL PILLAR TREATMENT

The historical pillar (Slave Voyages, land loss, wealth extraction) functions as **foundational evidence architecture**, not as a symmetric annually-normalized score input.

It is preserved fully in the evidence system. It informs the "1514–2024" span claim as historical context. It is NOT force-fit into the same annual normalization pipeline as BLS unemployment or NAEP scores.

The "1514–2024" language in public communication means:
- The empirical scoring window is 1991–2024 (33 years of structured comparable data)
- The historical evidence pillar spans 1514–1866 (Slave Voyages) and 1910–2024 (land loss, Census wealth data)
- These are not comparable units and are not added to the same normalization pool

---

## 8. COMPARISON UNIVERSE

**Tract FDI:** All tracts in the 50 priority cities within the dataset. Not a national universe — this is a stated limitation.
**County FDI:** 17 priority states. Not all 3,222 US counties — full county data is in bdi-raw-data-vault Tier 3 and will be used in v2.0.
**National BDI:** National series with state-level resolution for 17 priority states.

---

*E5 Enclave Incorporated | By Grace, perfect ways.*
