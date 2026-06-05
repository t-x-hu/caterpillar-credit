# Caterpillar Inc. (CAT) — Credit Analysis

A five-year sell-side credit profile of Caterpillar (FY2020–FY2024), built bottom-up from primary SEC filings. The analysis separates the industrial entity — Machinery, Energy & Transportation (ME&T) — from the captive finance arm, Cat Financial / Financial Products (FP), then reconciles to consolidated.

**Key finding.** Consolidated net leverage of ~2.1x at FY2024 (down from ~4.0x at FY2020) is almost entirely Cat Financial. Stripping out the finance book, ME&T runs ~0.2x net leverage with ~$9.5bn of free cash flow and ~28x interest coverage — consistent with CAT's high single-A ratings (Moody's A2 / S&P A / Fitch A+).

## Contents

| File | What it is |
|------|------------|
| `cat_credit_model.ipynb` | Data build for FY2020–FY2024, verified line-by-line against the filings, with accounting-identity checks |
| `cat_credit_model.xlsx` | Formula-driven 7-sheet credit model — income statement, balance sheet, cash flow, ME&T supplemental, credit ratios, Cat Financial |
| `CAT_Credit_Memo.pdf` | Three-page sell-side credit memo |

## Methodology

- **Primary sources only.** Every figure traces to a specific SEC filing; nothing is estimated or reconstructed from memory.
- **ME&T / Financial Products separation.** The two have opposite balance-sheet logic: ME&T is an industrial issuer that should carry modest leverage, while FP is a lender that funds a receivables book and is debt-heavy by design. Reading consolidated debt alone overstates industrial risk.
- **Identity checks.** Accounting identities are computed as explicit checks — the balance sheet balances to zero, and ME&T D&A + FP D&A ties back to consolidated D&A — so the data self-validates.

## Reproduce

```bash
pip install pandas openpyxl
# open the notebook and Run All — each identity check prints 0 where the identity holds
jupyter notebook cat_credit_model.ipynb
```

## Sources

- CAT 4Q 2021 earnings release — FY2020–FY2021 — SEC Form 8-K, Exhibit 99.1
  https://www.sec.gov/Archives/edgar/data/0000018230/000001823022000014/cat_exx991x4qx2021xearning.htm
- CAT 4Q 2023 earnings release — FY2022 — SEC Form 8-K, Exhibit 99.1
  https://www.sec.gov/Archives/edgar/data/0000018230/000001823024000005/cat_exx991x4qx2023xearning.htm
- CAT 4Q 2024 earnings release — FY2023–FY2024 — SEC Form 8-K, Exhibit 99.1
  https://www.sec.gov/Archives/edgar/data/18230/000001823025000004/cat_exx991x4qx2024xearning.htm
- CAT FY2022 Form 10-K — covenant compliance (cat-20221231.htm)
  https://www.sec.gov/Archives/edgar/data/0000018230/000001823023000011/
- CAT Free Writing Prospectus, May 2025 — issuer ratings
  https://www.sec.gov/Archives/edgar/data/0000018230/000110465925047369/tm2514175d3_fwp.htm

## Disclaimer

For analytical and educational purposes only. Not investment advice.
