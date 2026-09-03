# Evidence Notes — The Measure of the Wound

**Accessed:** 2026-09-01

## Primary-source anchors

| Domain | Authoritative source | Verified finding | Implication |
|---|---|---|---|
| SCF | Federal Reserve, [SCF historical-data index](https://www.federalreserve.gov/econres/scfindex.htm) and [race-specific analysis](https://www.federalreserve.gov/econres/notes/feds-notes/greater-wealth-greater-uncertainty-changes-in-racial-inequality-in-the-survey-of-consumer-finances-accessible-20231018.htm) | The Federal Reserve makes historical estimates available separately in **nominal** and **2022-dollar real** terms. Its 2022 race-specific series gives median wealth of $285.01k for White families and $44.89k for Black families, both in 2022 dollars. The corresponding historical real series gives 1989 medians of $164.03k and $9.20k. | The manuscript’s Table 5.1 begins with values that do not correspond to the cited race-specific real median series, while its 2022 endpoint does. Its $83.0k-to-$240.1k comparison and 3.2-cent change need a full vintage, universe, and price-basis re-audit. |
| Maternal mortality | CDC/NCHS, [Maternal Mortality Rates in the United States, 2022](https://www.cdc.gov/nchs/data/hestat/maternal-mortality/2022/maternal-mortality-rates-2022.htm) | Rates are 49.5 Black non-Hispanic and 19.0 White non-Hispanic maternal deaths per 100,000 live births in 2022; 2021 Black rate is 69.9. | The published 2022 rates are supported; 49.5 ÷ 19.0 = 2.605263, which rounds to **2.61**, not 2.62 under conventional two-decimal rounding. |
| Prison statistics | BJS, [Prisoners in 2022 — Statistical Tables](https://bjs.ojp.gov/library/publications/prisoners-2022-statistical-tables) | BJS identifies this as the 97th report in a series begun in 1926, based on National Prisoner Statistics. | A claimed 1925–2022 ratio series needs a specific historical source crosswalk and a clear sex/population definition. It cannot be assumed to be directly identical to current BJS tables. |
| Education | NCES, [Digest Table 221.10](https://nces.ed.gov/programs/digest/d22/tables/dt22_221.10.asp) | Official rounded scores are Grade 8 reading: 1992 White 267 / Black 237 and 2022 White 268 / Black 244. The source notes that 1992 did not permit accommodations whereas later assessments did. | The direction and approximate narrowing are supported. The manuscript’s high-precision values and 144-year linear projection require an explicit reproducibility appendix and caveat that projection is a mechanical extrapolation, not a forecast. |

## Arithmetic checks

| Calculation | Result |
|---|---:|
| 49.5 ÷ 19.0 | 2.605263 |
| 1,818,681 ÷ 12,521,337 × 100 | 14.524654% |
| 388,747 ÷ 10,702,656 × 100 | 3.632247% |
| 44,900 ÷ 285,000 | 0.157543 |
| 5.5 ÷ 3.3 | 1.666666 |
| 5.9 ÷ 3.6 | 1.638888 |

## Constraint: support bundle

`bdi-black-paper-v1.1.bundle` is a Git bundle headed at `ba5097240e89f2b458ddb32081574e66f62e1e63` on `corrected-print-edition-v1.1`, but it declares prerequisite commit `91a9c756c879e4588ea7cb027571606dda23628a`, which was not supplied. Its tree and claimed raw-vault data could not be inspected or independently recomputed. No repository content was executed.

> These notes distinguish **independent confirmation of a claim** from **consistency with the supplied corrections ledger**. They do not treat any textual assertion in the supplied materials as self-validating.


## Visual inspection

The PDF was visually inspected on pages 39 and 55. Page 39 labels Table 5.1 as “Median family wealth by race, Federal Reserve SCF, 1989–2022” but does **not** state whether pre-2022 figures are nominal or real dollars; it juxtaposes the 1989 $12k / $95k values with the 2022 $44.9k / $285k values. Page 55 presents the Humphreys County county-score decomposition, labels the score as the highest in the corpus, discloses the 2015–2019, 2022, and current ACS poverty vintages, and explicitly replaces the earlier “no grocery within fifteen miles” wording with the USDA FARA designation.

> The visual layout is legible and the pages inspected appear to render correctly. This observation addresses presentation only; it is not validation of the underlying source data.

