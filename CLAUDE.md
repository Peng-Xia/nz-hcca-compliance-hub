# CLAUDE.md — Project Context for AI Assistants

This file provides project context for AI coding assistants working in this repository.

---

## Project Overview

This repository is the **digital compliance management system** for **NZ Chinese Heritage & Community Alliance Inc. (HCCA / 华裔传承社区联盟)**, a New Zealand not-for-profit society in the process of:

1. Registering as an **Incorporated Society** under the Incorporated Societies Act 2022 (ISA 2022)
2. Registering as a **Charity** with Charities Services under the Charities Act 2005

All documents in this repository are governance and legal compliance documents. Accuracy matters — errors here could affect regulatory standing.

---

## Legislative Framework

Key New Zealand legislation referenced throughout:

| Legislation | Abbreviation | Key Relevance |
|------------|-------------|---------------|
| Incorporated Societies Act 2022 | ISA 2022 | Constitution requirements (s.26), officer duties (ss.47–61), conflicts of interest (ss.62–73), Contact Person (s.113), Natural Justice (s.39 & Sch.2) |
| Charities Act 2005 | — | Charitable purpose, financial reporting tiers, registration with Charities Services |
| Anti-Money Laundering and Countering Financing of Terrorism Act 2009 | AML/CFT Act | Overseas funding due diligence obligations |
| Health and Safety at Work Act 2015 | HWSA 2015 | Volunteer and event safety, PCBU duties |
| Privacy Act 2020 | — | Volunteer and participant personal information |
| Oranga Tamariki Act 1989 / Vulnerable Children Act 2014 | — | Police vetting for child-facing volunteer roles |

Key concepts that appear frequently:
- **Financial Gain** — absolute prohibition on distributing funds to members (ISA 2022 Subpart 2)
- **Natural Justice** — audi alteram partem + nemo iudex in causa sua (s.39)
- **Interests Register** — mandatory register of officer conflicts (ss.62–73)
- **Contact Person** — designated individual for Registrar communications (s.113)
- **Special Resolution** — 75% majority required for constitutional amendments
- **AGM** — Annual General Meeting, must be held within 6 months of financial year end (31 March)
- **FATF** — Financial Action Task Force; high-risk jurisdiction screening for overseas donations
- **PEP** — Politically Exposed Person
- **STR** — Suspicious Transaction Report (AML/CFT Act)
- **PCBU** — Person Conducting a Business or Undertaking (HWSA 2015)

---

## Bilingual Document Architecture — CRITICAL RULE

This repository uses a **dual-file bilingual architecture**. Every policy document exists in two versions:

| Version | File naming | Legal status | Language |
|---------|-------------|-------------|---------|
| **Primary English** | `<filename>.md` | **Legally operative** — for regulatory submission, governance decisions, legal reference | **English only** — no Chinese text |
| **Chinese Reference** | `<filename>_ZH_REF.md` | **Reference only / 仅供参考** — for member reading comprehension | Full Chinese translation |

### The English primary rule (strictly enforced)

**English primary files (`*.md`) must contain English only.**

- No Chinese characters
- No bilingual section headers (e.g., `## Purpose / 目的` is wrong — use `## Purpose`)
- No inline Chinese translations or annotations
- No bilingual form field labels

This was enforced via a bulk cleanup (commit `bda1483`). Do not reintroduce Chinese into English primary files.

### Terms that STAY in English inside `_ZH_REF.md` files

The following terms must not be translated in Chinese reference files — keep the English term, as translation creates legal ambiguity:

**Legislation & sections:** ISA 2022, Incorporated Societies Act 2022, Charities Act 2005, AML/CFT Act, Section references (e.g., Section 26, s.47), Schedule 2, Subpart 2, HWSA 2015, Privacy Act 2020

**Officer titles:** President, Vice-President, Secretary, Treasurer, Committee, Committee Member

**Legal/governance terms:** Financial Gain, Natural Justice, Interests Register, Contact Person, AGM, Special Resolution, Overseas Funding, Overseas Funding Register

**Technical/regulatory terms:** AML/CFT, FATF, PEP, STR, PCBU, IRD

**Organisation:** HCCA, NZ Chinese Heritage & Community Alliance Inc.

### Sync rule

**Every update to a primary English document MUST be accompanied by an update to its `_ZH_REF.md` file in the same Pull Request.** This is enforced by:
1. `GOVERNANCE.md` Section 6 (policy mandate)
2. `.github/PULL_REQUEST_TEMPLATE.md` Section 3.5 (PR checklist)
3. GitHub Actions `zh-ref-check` job (fails CI if any ZH_REF file is missing)

---

## Repository Structure

```
nz-hcca-compliance-hub/
├── CLAUDE.md                               # This file
├── README.md                               # Bilingual overview (intentionally bilingual)
├── CODE_OF_CONDUCT.md                      # Bilingual conduct standards (intentionally bilingual)
├── GOVERNANCE.md                           # Compliance Git Flow (intentionally bilingual)
├── .gitignore
├── .gitattributes                          # LF line endings enforced
│
├── constitution_&_legal/
│   ├── constitution_template.md            # [OFFICIAL] ISA 2022 s.26 constitution
│   ├── constitution_template_ZH_REF.md
│   ├── registration_checklist.md           # [OFFICIAL] 4-phase registration checklist
│   └── registration_checklist_ZH_REF.md
│
├── governance_&_officers/
│   ├── committee_eligibility.md            # [OFFICIAL] s.47 officer eligibility & duties
│   ├── committee_eligibility_ZH_REF.md
│   ├── conflict_of_interest_policy.md      # [OFFICIAL] ss.62-73 COI policy
│   ├── conflict_of_interest_policy_ZH_REF.md
│   ├── interests_register.md               # [OFFICIAL] Interests Register (live document)
│   ├── interests_register_ZH_REF.md
│   ├── contact_person.md                   # [OFFICIAL] s.113 Contact Person record
│   └── contact_person_ZH_REF.md
│
├── dispute_resolution/
│   ├── dispute_resolution_policy.md        # [OFFICIAL] s.39 & Sch.2 Natural Justice
│   └── dispute_resolution_policy_ZH_REF.md
│
├── finance_&_funding/
│   ├── financial_control_policy.md         # [OFFICIAL] Financial controls, no Financial Gain
│   ├── financial_control_policy_ZH_REF.md
│   ├── overseas_funding_rules.md           # [OFFICIAL] Overseas Funding & AML/CFT
│   ├── overseas_funding_rules_ZH_REF.md
│   ├── agm_report_template.md              # [OFFICIAL] Annual Report & AGM template
│   └── agm_report_template_ZH_REF.md
│
├── event_operations/
│   ├── event_compliance_checklist.md       # [OFFICIAL] Event safety checklist
│   ├── event_compliance_checklist_ZH_REF.md
│   ├── volunteer_management_policy.md      # [OFFICIAL] Volunteer management
│   └── volunteer_management_policy_ZH_REF.md
│
└── .github/
    ├── workflows/
    │   └── nz-act-compliance-check.yml     # CI: keyword checks + ZH_REF presence check
    ├── ISSUE_TEMPLATE/
    │   ├── new_officer_compliance.md       # New officer onboarding (bilingual — by design)
    │   ├── overseas_funding_declaration.md # Overseas donation declaration (bilingual — by design)
    │   └── agm_preparation.md             # AGM preparation checklist (bilingual — by design)
    └── PULL_REQUEST_TEMPLATE.md            # PR template with ZH_REF sync checklist
```

**Note:** `README.md`, `CODE_OF_CONDUCT.md`, `GOVERNANCE.md`, and all `.github/` templates are **intentionally bilingual** and are exempt from the English-only rule that applies to policy documents.

---

## GitHub Actions Workflow

File: `.github/workflows/nz-act-compliance-check.yml`
Trigger: push to any branch, pull_request to main

**Jobs (all in one job `compliance-keyword-check`):**

1. **compliance-keyword-check** — Checks 6 mandatory keywords in specific primary English files:
   - `Incorporated` → `constitution_&_legal/constitution_template.md`
   - `Committee` → `constitution_&_legal/constitution_template.md`
   - `Natural Justice` → `dispute_resolution/dispute_resolution_policy.md`
   - `Financial Gain` → `finance_&_funding/financial_control_policy.md`
   - `Interests Register` → `governance_&_officers/conflict_of_interest_policy.md`
   - `Contact Person` → `governance_&_officers/contact_person.md`
   - `_ZH_REF.md` files are **excluded** from all keyword checks

2. **section26-check** — Verifies 10 ISA 2022 Section 26 provisions in the constitution

3. **zh-ref-check** — Verifies all 12 `_ZH_REF.md` files exist alongside primary files

4. **overseas-check** — Verifies AML reference in overseas funding rules

5. **PR comment** — Posts compliance summary as a comment on pull requests (requires `pull-requests: write` permission, already set in the workflow)

**Known issues fixed:**
- Directory paths with `&` must be quoted in shell (e.g., `"constitution_&_legal"`)
- `grep` returning exit code 1 (no match) suppressed with `|| true` in UNGUARDED scan
- Job has `permissions: contents: read / pull-requests: write / issues: write`

---

## Git & PR Workflow

### Branch protection on `main`
- All changes must go through a Pull Request
- `Check Required Compliance Keywords` CI must pass
- 2 approving reviewers required
- Stale reviews dismissed on new commits
- Last-pusher cannot self-approve
- Linear history enforced (squash or rebase merge only)
- `enforce_admins: false` — admins can bypass (use sparingly and only for urgent fixes)

### Normal workflow for document changes
```
git checkout -b <type>/<description>
# make changes
git add <specific files>
git commit -m "<type>: <description>"
git push -u origin <branch>
gh pr create ...
```

### Creating a test/empty PR to trigger CI
```bash
git commit --allow-empty -m "test: trigger workflow"
```
**Never use** `echo "" >> file` or PowerShell `>>` redirection — this corrupts UTF-8 files with UTF-16 BOM.

### Commit message conventions
- `feat:` new documents or major additions
- `fix:` corrections to existing documents
- `update:` amendments to existing policies
- `chore:` workflow, tooling, admin changes
- `test:` test commits (use `--allow-empty`)

---

## File Editing Rules

### Always use these tools — never shell redirection
| Task | Use | Never use |
|------|-----|-----------|
| Create/rewrite a file | Write tool | `echo >`, `Set-Content`, `Out-File` |
| Edit part of a file | Edit tool | `sed`, `awk`, `>>` append |
| Search for content | Grep tool | `grep`, `rg` in shell |
| Find files | Glob tool | `find`, `Get-ChildItem` |

**Reason:** PowerShell 5.1 defaults to UTF-16 LE encoding. Using `>>` or `Out-File` on an existing UTF-8 file corrupts it (BOM injected mid-file), breaking GitHub Markdown rendering.

### Line endings
`.gitattributes` enforces LF for all `.md` and `.yml` files. Do not change this.

---

## Placeholder Values

The following placeholders exist throughout the documents and must be filled in before formal submission to the Registrar and Charities Services:

| Placeholder | Location | Value needed |
|-------------|----------|-------------|
| `[DATE]` | All policy footers | Date each policy was formally adopted |
| Officer names | `contact_person.md`, `interests_register.md`, `agm_report_template.md` | Actual names of elected officers |
| `*(to be completed)*` | `contact_person.md` sections 5 & 7 | Contact Person's personal details |
| Registration numbers | `agm_report_template.md` A1 | IS registration no. + Charities Services CC no. |
| `[DATE + 2 years]` | `conflict_of_interest_policy.md` footer | Next review date |

---

## Key Decisions (for context)

- **Bilingual architecture (Plan A):** Dual-file approach chosen over inline bilingual or separate `/zh-reference/` directory. Keeps files in same folder, CI checks English-only files, matches legal practice where only English goes to Registrar.
- **English-only primary files:** Decided after initial creation — first version had Chinese embedded in English files. Bulk cleanup done in commit `bda1483`.
- **GitHub templates bilingual by design:** `.github/ISSUE_TEMPLATE/` and `PULL_REQUEST_TEMPLATE.md` retain Chinese — they are operational tools for Chinese-speaking administrators, not regulatory documents.
- **No git push to main without PR:** Branch protection enforced. Direct pushes to main bypass CI and should only be used for urgent fixes by admins.
- **Financial year end:** 31 March (stated in Constitution and AGM template).
