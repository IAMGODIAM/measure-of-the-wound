# The Measure of the Wound
### A Sovereign Empirical Record of Black American Structural Distress, 1991–2024

**Israel Lee Armstead** · E5 Enclave Incorporated · Liberty City, Miami, Florida
**Corrected Print Edition v1.4 — Submission Edition** · September 2026
**License: CC0 1.0 Universal** — public domain. No permission, attribution or fee required.

> This is the **publication package** — the frozen, citable release of the paper together with everything needed to check it. The living manuscript repository is [`IAMGODIAM/bdi-black-paper`](https://github.com/IAMGODIAM/bdi-black-paper).

---

## Read the paper

**[`The_Measure_of_the_Wound.pdf`](The_Measure_of_the_Wound.pdf)** — 91 pages, print-ready, US Letter.

Abstract, keywords, JEL codes, author of record and the AI-assistance disclosure are on page 3. A consolidated References list follows Chapter 8. Appendix H is the complete corrections ledger.

**Verify the file you are holding:** `sha256sum The_Measure_of_the_Wound.pdf` should match [`The_Measure_of_the_Wound.pdf.sha256`](The_Measure_of_the_Wound.pdf.sha256). The PDF is produced by a deterministic container build (`build/REPRODUCING.md`), so anyone can regenerate the identical bytes from the sources in this package.

## What is in this package

| Path | Contents |
|---|---|
| `The_Measure_of_the_Wound.pdf` · `.pdf.sha256` | The paper, v1.4, and the SHA-256 of the deterministic build |
| `manuscript/` | The 12 markdown sources the PDF is built from, in reading order |
| `build/` | The typesetting pipeline (`build.py`, `print.css`) and a pinned container (`Dockerfile`, `requirements.txt`, `rebuild.sh`/`rebuild.ps1`, `REPRODUCING.md`). `./build/rebuild.sh` regenerates the PDF **byte-for-byte**; compare with `The_Measure_of_the_Wound.pdf.sha256` |
| `data/` | **Frozen snapshot** of every raw federal source file the paper's tables are computed from, copied verbatim from `bdi-raw-data-vault` and the FarmBlock repositories at release time, with a SHA-256 manifest |
| `errata/CORRECTIONS_LEDGER.md` | Every figure changed between drafts and print, with original claim and verified value |
| `errata/RECOMPUTATION_LOG.md` | The unedited output of recalculating every derived statistic from the raw series |
| `review/` | The independent verification review (Manus AI, Sept 1 2026), its evidence notes, and the author's point-by-point response |
| `CITATION.cff` · `.zenodo.json` | Machine-readable citation and archive metadata |
| `CHANGELOG.md` | v1.0 → v1.4 |

## How to cite

> Armstead, Israel Lee. 2026. *The Measure of the Wound: A Sovereign Empirical Record of Black American Structural Distress, 1991–2024.* Corrected Print Edition v1.4. E5 Enclave Incorporated. CC0 1.0. https://github.com/IAMGODIAM/measure-of-the-wound

A DOI will be added to this README when the Zenodo archive of the first release is minted.

## The finding in one paragraph

Across eight pillars and up to 122 years of federal data, the same shape recurs: **absolute conditions improve while the ratio between Black and white outcomes holds or widens.** In constant 2022 dollars Black median family wealth rose 388 percent since 1989 and the absolute wealth gap is nonetheless at its widest point in the survey's history. The Black/white unemployment ratio has never inverted in fifty-four years. The maternal mortality ratio is higher in 2022 than it was under legal segregation in 1930. The imprisonment ratio moved 0.14 points in ninety-seven years. The homeownership gap is wider than when the Fair Housing Act was signed.

## What a reviewer should still contest

Stated up front, not buried. See Appendix H §E and Appendix E.4a.

- **The FarmBlock Distress Index outputs are not independently reproducible from this package.** The scored CSVs, formulas, weights and normalization method are public; the pre-scoring raw inputs, normalization bounds and transformation code are not yet released. The 87.25 Humphreys County score should be cited as this organization's published output, not as an independently verified result. Stated in the paper at §7.1 where the index is introduced, and in Appendix E.4a. The chapter is kept on that footing rather than withdrawn; §7.3 prints this project's own failed reproduction (79.7) beside it.
- The county-level index includes Black population share at 15% weight as a structural-exposure proxy; the tract-level index deliberately excludes it. Compare the two.
- The incarceration series' denominator is probably male rates; the BJS all-adults ratio (5.22) is printed beside it (6.31).
- Pre-1933 maternal mortality figures rest on the birth-registration states only.
- Eight tracts in the published FDI file carry imputation artifacts, including the top-ranked tract; enumerated in Appendix E.

## Disclosure of AI assistance

Generative AI (Claude, Anthropic) was used substantially to draft and revise prose, recompute derived statistics from the raw source series, build the typesetting pipeline and compile the corrections ledger, under the direction of the author, who set the research questions, selected and approved every source, reviewed every figure and is accountable for all content. An independent verification review was performed by Manus AI. No AI system is an author.

## The data stack this paper sits on

| Layer | Repository | Contents |
|---|---|---|
| 1 — raw evidence | `IAMGODIAM/bdi-raw-data-vault` | 18 unmodified federal source files, ~14,811 observations |
| 2 — synthesized | `IAMGODIAM/bdi-sovereign-dataset` | 1,574 verified observations, 8 pillars; sealed on Base Mainnet |
| 3 — tract | `IAMGODIAM/farmblock-data` | 15,507 census tracts, 49 cities |
| 3 — county | `IAMGODIAM/farmblock-dataset` | 24-county published pilot |
| 4 — manuscript | `IAMGODIAM/bdi-black-paper` | Working drafts, outline, peer review |
| **release** | **`IAMGODIAM/measure-of-the-wound`** | **This package** |

**Related campaign record:** the DC Package — nine policy packets delivered to congressional leaders and to Justice Clarence Thomas, July 2026 — at [dc.e5enclave.com](https://dc.e5enclave.com). This paper is the empirical instrument underlying that record.

---

*E5 Enclave Incorporated · 820 NW 64th Street, Miami, FL 33150 · EIN 99-3822441 · UEI H8NGXEYE2HH8*
*Nil satis nisi optimum. By Grace, perfect ways.*
