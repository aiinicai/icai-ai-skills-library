---
name: ca-financial-statement-analyzer
description: Analyze a company's Balance Sheet and Profit & Loss Statement for Chartered Accountants, finance teams, auditors, and business owners. Use when the user provides financial statements, annual accounts, comparative financial figures, or financial data tables and requests financial ratios, year-on-year comparison, profitability and liquidity trends, working-capital analysis, financial health commentary, red flags, or an executive financial analysis report. Supports INR and other currencies, including amounts expressed in lakh or crore.
---

# CA Financial Statement Analyzer

Turn financial statements into a traceable, decision-useful analysis. Use only supplied financial information; identify assumptions, missing inputs and anomalies. Do not treat a numerical signal as evidence of fraud or non-compliance.

## 1. Accept and normalize inputs

- Accept pasted tables, CSV, Excel, PDFs, or structured text if the host application makes their contents accessible. If a file cannot be read, request figures in text or a supported format; never pretend it was analyzed.
- Record company, sector if supplied, currency, unit scale (e.g., INR lakh), financial periods, accounting basis if specified, and whether figures are consolidated or standalone.
- Map equivalent line items carefully; distinguish trade payables, short-term borrowings, current portion of long-term borrowings, equity, and non-current borrowings. Do not double count components already included in totals.
- Preserve reported values and financial statement signs. Treat parentheses as negatives when the source does. Normalize year labels before computing YoY changes. Do not mix crore/lakh/absolute amounts without explicit conversion.
- Use the provided figures only. Do not silently fabricate revenue, debt, cash flows, opening balances, tax rates, industry benchmarks, or prior-year comparatives.
- If only one period is provided, compute available single-period ratios; state that YoY analysis needs comparative figures. If only P&L or Balance Sheet is provided, compute only supported metrics.

## 2. Validate financial statement logic

Before ratios, reconcile where data permits:

- Balance Sheet: Total assets = Total equity + Total liabilities. Show any difference in source units, and flag material mismatches; do not force it to balance.
- P&L: Revenue - cost of goods sold = gross profit; gross profit - operating expenses = EBITDA only if the expense classification excludes depreciation, interest and tax; EBITDA - depreciation/amortization = EBIT; EBIT + non-operating income - finance costs +/- other gains/losses = profit before tax; profit before tax - tax = profit after tax. Respect the presented statement's classification, and do not impose a simplified bridge when figures include other items.
- Report inconsistencies, missing figures, implausible signs, accounting classification uncertainties, and division-by-zero issues in **Data Quality Notes**. Do not infer a missing line item merely to make totals tie.

## 3. Calculate ratios correctly

Use `references/ratio-definitions.md` for formulas, denominator rules, and caveats. Select ratios only where underlying amounts are present. For working-capital days, make clear if closing balances are being used as a proxy because opening balances are unavailable. Use an explicit annual day count convention (365 unless requested otherwise).

At minimum, when information permits, include:

1. **Growth:** revenue and PAT YoY %.
2. **Profitability:** gross profit margin, EBITDA margin, net profit margin, EBIT margin.
3. **Liquidity:** current ratio, quick ratio, working capital.
4. **Leverage and servicing:** gross interest-bearing debt/equity, interest coverage.
5. **Working-capital efficiency:** approximate receivable, inventory, payable days and cash conversion cycle when suitable figures are available.
6. **Returns:** ROE/ROA only when the relevant average balances can be determined; otherwise mark N/A or explicitly label any ending-balance proxy rather than presenting it as standard ROE/ROA.

Compute with full precision and display percentages to 1-2 decimal places, multiples to 2 decimals, days to 1 decimal. Use `N/A` when a metric is unsupported. Do not convert an undefined or negative-denominator ratio into a meaningful-looking number; explain the limitation.

## 4. Compare periods and detect signals

- For monetary line items, calculate YoY % = (current - previous) / ABS(previous) * 100 when previous is nonzero, and note if signs change. For prior-year zero or ambiguous sign changes, show absolute movement and mark % N/A.
- For margins, state movements in **percentage points**, not percent. For ratios, show current vs previous and the direction of change.
- Use thresholds only as *illustrative triage triggers*, never as auditing standards or a substitute for entity-specific materiality: revenue/PAT movement >= 15%, gross/EBITDA/PAT margin movement >= 2.0 percentage points, current ratio below 1.5, debt/equity above 2.0, and interest coverage below 2.0. Do not claim a benchmark applies without sector/context.
- Prioritize meaningful trends and combined patterns: sales rising but margins shrinking; debt increasing while interest coverage declines; receivable days growing faster than credit terms; inventory days rising; negative working capital; persistent losses. A trigger is an **area for enquiry**, not a finding of misstatement, fraud, financial distress, or regulatory breach.
- For every flagged issue, quote supporting figures, explain possible business reasons in conditional language, and suggest a practical follow-up request or management question.

## 5. Return a concise professional report

Use this structure, adapting sections if data is incomplete:

### Financial Statement Analysis — [Company] — [Periods]
**Basis:** [currency, scale, standalone/consolidated, sources, data limitations]

**Executive summary:** 3-5 lines with major strengths, pressures, and overall direction.

**Key financial movements**: table with Metric | Prior year | Current year | Change | Interpretation. Include revenue, EBITDA, PAT, total assets, equity, debt, and other material lines if supplied.

**Financial ratio dashboard**: table with Ratio | Prior year | Current year | What it indicates. Show formula definitions on request.

**Key insights**: 3-5 evidence-backed observations about profitability, liquidity, leverage, and operating efficiency.

**Red flags / matters for further enquiry**: numbered findings; each with evidence, possible interpretation, and next question. If no notable signals are detected, say so without implying an audit conclusion.

**Data Quality Notes**: missing items, mismatches, approximate proxies, and assumptions.

**Suggested management actions**: 3-5 specific follow-ups, prioritized by observed evidence.

**Professional-use note:** This is an analytical review, not an audit opinion, valuation, assurance report, or independent verification of financial information. Results require review of source records and management context.

## 6. Test scenario

Use `assets/demo-financials.md` for a fictional two-year Indian-company test case and `references/demo-test.md` for test prompts and expected numerical checkpoints. Do not treat example figures as actual company information. To test, provide that sample statement data to the model with: "Apply CA Financial Statement Analyzer and generate a comparative financial analysis, ratio dashboard, key insights and red flags."

## 7. Quality check before answering

- Confirm unit consistency, period order and correct signs.
- Recalculate major values independently when calculation tooling is available; otherwise show calculation logic for important ratios.
- Check that totals reconcile, margins are not confused with rupee movements, and percentage-point changes are clearly labelled.
- Never output invented source figures, invented management responses, or unsupported legal/accounting assertions.
- Remove or anonymize sensitive company/client financial information from public demos and repositories.
