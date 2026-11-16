# CA Financial Statement Analyzer

**An AI Skill for Chartered Accountants and finance professionals**  
*Demo contribution for the ICAI AI Skills Library*

This reusable Skill guides compatible AI assistants, including **ChatGPT** and **Claude** where Skills are supported, to analyse a Balance Sheet and Statement of Profit & Loss (P&L). It produces consistent ratio calculations, year-on-year (YoY) comparisons, evidence-based financial insights, and matters for further enquiry.

> **Demo status:** This is a sample Skill for internal testing, training and review. It is not an ICAI-issued accounting standard, audit methodology, or assurance opinion.

## Key features

- **Financial ratios:** profitability, liquidity, leverage, interest coverage, working capital, and selected efficiency/return measures.
- **YoY analysis:** revenue, EBITDA, profit after tax (PAT), balance-sheet movements, and margin changes in percentage points.
- **Financial insights:** identify and explain significant movements with supporting figures.
- **Potential red flags:** highlight issues for follow-up, not allegations of fraud or misstatement.
- **Data validation:** check whether the Balance Sheet reconciles and disclose missing or inconsistent figures.
- **Professional reporting:** generate a concise management-facing report with assumptions and suggested follow-up questions.

## Repository structure

```text
ca-financial-statement-analyzer/
├── SKILL.md                         # Main instructions for the AI assistant
├── README.md                        # Overview and usage guide
├── agents/
│   └── openai.yaml                  # Display metadata for ChatGPT
├── references/
│   ├── ratio-definitions.md         # Formulas and calculation conventions
│   └── demo-test.md                 # Demo prompts and numerical checkpoints
└── assets/
    └── demo-financials.md           # Fictional two-year financial statements
```

**Start with [`SKILL.md`](SKILL.md)**. It contains the actual instructions that define the Skill's behaviour. This README explains the Skill to GitHub visitors and testers.

## How to test

1. Open the Skill in your ChatGPT or Claude environment using its available Skills/import mechanism. Installation steps depend on the product and plan. Alternatively, for a simple instruction-following demo, provide the contents of `SKILL.md` together with the relevant reference files in your chat.
2. Copy or attach the **fictional** Balance Sheet and P&L from [`assets/demo-financials.md`](assets/demo-financials.md).
3. Paste this prompt:

   > Use the CA Financial Statement Analyzer Skill to analyse the attached financial statements. Prepare a two-year comparison, financial ratio dashboard, key insights, up to three potential red flags, and management recommendations. Explain calculation assumptions, disclose unavailable metrics, and verify whether the Balance Sheet balances.

4. Compare the response against [`references/demo-test.md`](references/demo-test.md). If any key calculation or interpretation is incorrect, revise the Skill instructions and test again.

### Expected demo results

The included sample is for **ABC Manufacturing Pvt Ltd** (entirely fictional). Monetary amounts are in **INR lakh**, with FY 2025-26 compared against FY 2024-25.

| Measure | FY 2024-25 | FY 2025-26 | Interpretation |
|---|---:|---:|---|
| Revenue | 1,600 | 1,800 | **12.50% growth** |
| Gross profit margin | 32.50% | 30.00% | **2.50 percentage-point decline** |
| EBITDA margin | 13.75% | 12.22% | Margin compression |
| Profit after tax (PAT) | 79 | 78 | **1.27% decline** |
| Current ratio | 2.00 | 1.89 | Some weakening in liquidity ratio |
| Debt-to-equity ratio | 0.56 | 0.44 | Lower interest-bearing leverage |

The Skill should flag the combination of **rising revenue and declining margins** for management enquiry, without asserting wrongdoing. It should also explain that a cash-flow assessment requires a cash-flow statement.

## Inputs and outputs

**Supported inputs, subject to the AI platform's file-reading capabilities:** pasted financial tables, structured text, CSV, Excel spreadsheets and PDFs. Both single-period and multi-period analysis are possible, but YoY comparison needs comparable periods.

**Report sections:** executive summary; key financial movements; ratio dashboard; insights; potential red flags or matters for enquiry; data-quality notes; suggested management actions; and an appropriate professional-use disclaimer.

## Calculation and interpretation safeguards

- Use **only supplied figures**. Never fabricate missing items, benchmarks or prior-year balances.
- Maintain consistent currencies, units, sign conventions and reporting periods.
- Show unsupported ratios as **N/A**, and label any approximations clearly.
- Distinguish **percentage changes** from **percentage-point movements** in margins.
- Treat illustrative ratio thresholds as screening prompts, **not** sector-specific standards or conclusive findings.
- Do not present the output as an audit opinion, assurance report or independent verification.

See [`references/ratio-definitions.md`](references/ratio-definitions.md) for detailed formulas and caveats.

## Feedback and contributions

Faculty members and testers can help improve this Skill by:

1. Testing the fictional sample and checking calculations against the expected values.
2. Reporting unclear instructions, inconsistent ratios, or omitted disclosures.
3. Proposing additional relevant, well-defined analysis checks with reproducible example data.
4. Submitting a GitHub issue or pull request to the [ICAI AI Skills Library](https://github.com/aiinicai/icai-ai-skills-library), according to repository permissions.

**Suggested review criteria:** accuracy, traceability, clarity, reusability, compatibility, privacy, and professional relevance.

## Confidentiality and responsible use

**Do not upload confidential client financial statements, personal information, or unpublished company records into a public GitHub repository.** Use synthetic data for public demonstrations. When using AI tools with real client information, follow applicable confidentiality, data-protection, contractual and organisational requirements.

## Disclaimer

This Skill supports preliminary financial analysis and professional judgement. It does **not** replace verification against source records, applicable accounting standards, audit procedures, or review by a qualified professional.

---

*Prepared as a demonstration resource for the AI Committee of ICAI's AI Skills Library initiative.*

