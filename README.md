# ICAI AI Skills Library

**A community-driven library of reusable AI Skills for OpenAI and Claude.**

Welcome to the **ICAI AI Skills Library**, an initiative to encourage the development, sharing, and responsible reuse of AI-powered workflows for Chartered Accountants, students, finance professionals, educators, and other interested contributors.

The library accepts Skills designed for OpenAI and/or Claude. Contributions are proposed via a **GitHub fork and pull request** and become part of the main library only after maintainer review and approval.

> **Note:** Inclusion in this repository does not constitute official certification, endorsement, or security assurance of a contributed Skill by ICAI, OpenAI, or Anthropic.

## Objectives

- Build a searchable, practical collection of community-contributed AI Skills.
- Encourage innovation across accounting, auditing, taxation, finance, compliance, analytics, education, and professional productivity.
- Promote reusable, documented workflows and collaborative improvement.
- Review submissions for relevance, documentation quality, appropriate licensing, and basic security and privacy concerns before merging.

## Repository Structure

```text
icai-ai-skills-library/
├── README.md
├── CONTRIBUTING.md             # Optional expanded contributor guidance
├── LICENSE                     # Repository license, selected by maintainers
├── skills/
│   ├── accounting/
│   │   └── sample-skill/
│   │       └── SKILL.md
│   ├── audit/
│   ├── taxation/
│   ├── finance/
│   ├── data-analytics/
│   ├── compliance/
│   ├── education/
│   └── productivity/
└── .github/
    └── PULL_REQUEST_TEMPLATE.md
```

Each Skill must have its **own uniquely named folder** inside one relevant category. The Skill folder must contain `SKILL.md`; optional `scripts/`, `references/`, and `assets/` folders may be included where necessary. Avoid placing secrets, client data, or other sensitive content in any files.

## How to Contribute: Fork → Add Skill → Pull Request → Merge

1. **Fork the repository.** Sign in to GitHub, open this repository, and select **Fork** to create a copy under your account.
2. **Create a branch in your fork.** Use a descriptive branch name such as `add-gst-reconciliation-skill`.
3. **Upload or create your Skill.** Place it at `skills/<category>/<skill-name>/SKILL.md`, together with any required supporting files. Use lowercase kebab-case names, such as `invoice-reconciliation`.
4. **Document and test it.** Describe what the Skill does, when it should be used, required inputs, procedure, outputs, dependencies, and limitations. Test it in the OpenAI and/or Claude environment claimed to be supported.
5. **Commit your changes** to your branch and **open a Pull Request** to the main repository's `main` branch. In the PR, explain the purpose, platform compatibility, sample use case, testing performed, and any scripts or external services used.
6. **Respond to review feedback.** Maintainers may ask for revisions, request additional evidence, or decline submissions.
7. **Merge after approval.** Only designated repository maintainers can approve and merge contributions. A submitted PR is not automatically accepted.

If you are new to GitHub, refer to the [GitHub guide to creating a pull request from a fork](https://docs.github.com/en/pull-requests/how-tos/create-pull-requests/creating-a-pull-request-from-a-fork).

## Minimum Skill Format

Create a file named **`SKILL.md`** inside your Skill folder:

```markdown
---
name: invoice-reconciliation
description: Reconcile invoice records against ledger entries and identify exceptions. Use when a user asks to compare invoice and accounting data.
---

# Invoice Reconciliation

## Purpose
Explain what the Skill accomplishes.

## Inputs
Describe the input files or information required.

## Workflow
1. Validate inputs and required columns.
2. Compare records and identify discrepancies.
3. Generate an exception report.

## Output
Describe the expected deliverable.

## Limitations and Safeguards
Explain review requirements, data handling, and known limitations.
```

The YAML frontmatter must include `name` and `description`. The description should clearly indicate the Skill's purpose and when it should be invoked. Keep Skill instructions concise, specific, and verifiable.

## Submission Checklist

- [ ] My contribution is original or I have the necessary rights and have identified third-party licenses and attribution.
- [ ] The Skill has a valid `SKILL.md` with a clear `name` and `description`.
- [ ] The folder uses lowercase kebab-case and is in the appropriate category.
- [ ] Instructions, dependencies, inputs, outputs, and limitations are documented.
- [ ] I have identified whether the Skill supports OpenAI, Claude, or both, and described how it was tested.
- [ ] I have checked all scripts and links; no malware, unauthorized data collection, or unsafe instructions are included.
- [ ] No passwords, API keys, tokens, personal data, confidential client records, or proprietary materials have been committed.
- [ ] Sample data is synthetic, anonymized appropriately, or authorized for public distribution.
- [ ] Any financial, tax, audit, legal, or regulatory outputs require appropriate professional review and must not imply guaranteed compliance.

## Review and Acceptance

Maintainers will assess submissions for relevance, clarity, originality, usability, documentation, licensing, privacy, security, and responsible AI practices. They may request edits, reject a Skill, or remove a previously merged Skill if concerns arise. Contributors remain responsible for the accuracy, permissions, and maintenance of their submissions.

## Using Skills

Browse the `skills/` directory and inspect the `SKILL.md` and any executable code before using a Skill. Download or copy the relevant Skill folder and install/import it following the instructions for your specific OpenAI or Claude product. **A Skill being listed here does not mean it will run automatically in every OpenAI or Claude interface.** Requirements and support vary by platform and environment.

## Responsible Use

Do not upload client-confidential information or personal data to this public repository. Treat downloaded scripts and third-party dependencies as untrusted until reviewed. Use appropriate data-protection controls, test with non-sensitive sample data, and apply professional judgment before relying on outputs.

## Community and Support

Use **GitHub Issues** to report documentation gaps, bugs, suggested enhancements, or security concerns that are safe to disclose publicly. Do not publish exploit details, credentials, or confidential information in an Issue; contact the maintainers privately instead.

**Initiative:** ICAI AI Committee  
**Contact:** ai@icai.in

---

**Contribute a Skill. Share knowledge. Strengthen the AI ecosystem for professionals.**
