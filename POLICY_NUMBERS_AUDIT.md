# HCCA Policy Numbers Audit — Basis Verification

> **Purpose:** This document audits every specific number (dollar thresholds, time limits, percentages, counts) appearing in HCCA's primary English policy documents, and classifies each by its legal basis. Items in Category C must be verified by a NZ solicitor or Charities Services before the policy is formally adopted.
>
> **Date of audit:** 2026-06-26
> **Scope:** All primary English `.md` policy files. GitHub templates and `_ZH_REF.md` files excluded.

---

## Summary Table

| # | Number | Document | Clause | Category | Source |
|---|--------|----------|--------|----------|--------|
| 1 | 75% special resolution majority | constitution_template.md | 10.5, 15.1, 20.1 | ✅ A — Statutory | ISA 2022 s.24 |
| 2 | 18 years — minimum officer age | constitution_template.md / committee_eligibility.md | const.11.2 / elig.3 | ✅ A — Statutory | ISA 2022 s.47(1)(a) |
| 3 | 5 years — dishonesty conviction lookback | constitution_template.md / committee_eligibility.md | const.11.2(e) / elig.3 | ✅ A — Statutory | ISA 2022 s.47(1)(d) |
| 4 | 20 working days — notify Registrar of constitutional amendment | constitution_template.md | 15.2 | ✅ A — Statutory | ISA 2022 (Registrar notification obligations) |
| 5 | 6 months — AGM must be held after financial year end | constitution_template.md | 8.1 | ⚠️ B — Verify | ISA 2022 s.26(1)(f) requires AGM provision; 6-month window is common NZ practice but exact timeframe to verify against s.126 or constitution model rules |
| 6 | 16 years — minimum member age | constitution_template.md | 3.1 | 🔴 C — Internal | No statutory minimum; chosen internally |
| 7 | 30 days — subscription notice period | constitution_template.md | 4.1 | 🔴 C — Internal | Not in ISA 2022; internal policy choice |
| 8 | 60 days — subscription arrears before removal | constitution_template.md | 4.3 | 🔴 C — Internal | Not in ISA 2022; internal policy choice |
| 9 | 14 days — notice before removing lapsed member | constitution_template.md | 4.3 | 🔴 C — Internal | Not in ISA 2022; internal policy choice |
| 10 | 10% of members or 10 members — SGM request threshold | constitution_template.md | 9.1(b) | 🔴 C — Internal | Not in ISA 2022; internal policy choice (ISA 2022 only requires constitution to specify a process) |
| 11 | 28 days — SGM must be held after request | constitution_template.md | 9.2 | 🔴 C — Internal | Not in ISA 2022; internal policy choice |
| 12 | 14 days — general meeting notice | constitution_template.md | 10.1 | ⚠️ B — Verify | ISA 2022 Schedule 1 cl.3 sets minimum notice rules; verify whether 14 days meets or exceeds the statutory minimum |
| 13 | 21 days — special resolution meeting notice | constitution_template.md | 10.1, 7.2(a), 13.1(a), 15.1(a) | ⚠️ B — Verify | Common NZ practice; verify against ISA 2022 Schedule 1 |
| 14 | 10 members or 20% quorum (min. 5) | constitution_template.md | 10.3 | 🔴 C — Internal | ISA 2022 requires quorum provision in constitution; actual numbers are internal choice |
| 15 | 4 times per year — Committee meetings | constitution_template.md | 14.4 | 🔴 C — Internal | Not in ISA 2022; internal policy choice |
| 16 | 2 years — officer term | constitution_template.md | 12.2 | 🔴 C — Internal | Not in ISA 2022; internal policy choice |
| 17 | NZD 500 — dual signatory threshold for payments | financial_control_policy.md / overseas_funding_rules.md | fcp.3.4 / ofr.7 | 🔴 C — Internal | No statutory amount; widely recommended in NZ charitable sector guidance but not mandated |
| 18 | NZD 200–500 — Treasurer sole approval range | financial_control_policy.md | 3.4 | 🔴 C — Internal | No statutory basis; internal policy choice |
| 19 | Under NZD 200 — Treasurer quarterly self-authorise | financial_control_policy.md | 3.4 | 🔴 C — Internal | No statutory basis; internal policy choice |
| 20 | 20% or NZD 300 — budget variance requiring Committee resolution | financial_control_policy.md | 4.2 | 🔴 C — Internal | No statutory basis; internal policy choice |
| 21 | 30 days — post-event financial summary deadline | financial_control_policy.md / event_compliance_checklist.md | fcp.4.3 / ecc.3.1 | 🔴 C — Internal | No statutory basis; internal policy choice |
| 22 | 60 days — expense reimbursement claim deadline | financial_control_policy.md / volunteer_management_policy.md | fcp.5.1 / vmp.5.3 | 🔴 C — Internal | No statutory basis; internal policy choice |
| 23 | NZD 500 — reimbursement requiring Committee resolution | financial_control_policy.md | 5.2 | 🔴 C — Internal | No statutory basis; same threshold as dual signatory (consistent) |
| 24 | 7 years — financial record retention | financial_control_policy.md | 7.2 | ⚠️ B — Verify | IRD requires 7 years for tax records; AML/CFT Act requires 5 years for AML records; Companies Act 1993 uses 7 years. Charitable entities should verify under Charities Act 2005 and IRD rules. 7 years is likely correct but basis should be stated explicitly. |
| 25 | NZD 1,500 — single overseas donation AML self-assessment trigger | overseas_funding_rules.md | 4.2, 6.1(c) | 🔴 C — Internal | **No direct statutory provision at this amount.** HCCA may not even be a "reporting entity" under AML/CFT Act 2009. Threshold was set as a conservative internal compliance measure. Must be verified with Charities Services or a solicitor. |
| 26 | NZD 5,000 — cumulative 12-month overseas funding AML trigger | overseas_funding_rules.md | 4.2 | 🔴 C — Internal | **No direct statutory provision at this amount.** Same basis issue as item 25 above. |
| 27 | 30 days — Overseas Funding Register entry deadline | overseas_funding_rules.md | 5.1 | 🔴 C — Internal | No statutory basis; internal policy choice |
| 28 | NZD 2,000 — Committee approval for overseas fund expenditure | overseas_funding_rules.md | 7 (Financial Isolation table) | 🔴 C — Internal | No statutory basis; internal policy choice |
| 29 | 15 working days — informal resolution attempt period | dispute_resolution_policy.md | 4.4 | 🔴 C — Internal | ISA 2022 Schedule 2 requires a dispute resolution process but does not specify timeframes; internal choice |
| 30 | 5 working days — Secretary acknowledgment of complaint | dispute_resolution_policy.md | 5.3 | 🔴 C — Internal | Internal policy choice |
| 31 | 10 working days — respondent response period | dispute_resolution_policy.md | 5.4 | 🔴 C — Internal | Internal policy choice |
| 32 | 20 working days — Committee must convene hearing | dispute_resolution_policy.md | 6.1 | 🔴 C — Internal | Internal policy choice |
| 33 | 10 working days — Committee written decision after hearing | dispute_resolution_policy.md | 6.4 | 🔴 C — Internal | Internal policy choice |
| 34 | 15 working days — appeal filing window | dispute_resolution_policy.md | 7.1 | 🔴 C — Internal | Internal policy choice |
| 35 | 30 working days — general meeting must be held for appeal | dispute_resolution_policy.md | 7.3 | 🔴 C — Internal | Internal policy choice |
| 36 | 2 years — policy review cycle | dispute_resolution_policy.md / conflict_of_interest_policy.md | drp.11 / coi.9 | 🔴 C — Internal | Internal policy choice; no statutory review cycle specified in ISA 2022 for these policies |
| 37 | 5 working days — Interests Register update deadline | conflict_of_interest_policy.md | 5.1 | ⚠️ B — Verify | ISA 2022 s.68 requires the register to be maintained; "5 working days" is the internal implementation of "as soon as practicable" — verify whether ISA 2022 s.68 imposes any timeframe |
| 38 | 60 minutes — event coordinator pre-event arrival | event_compliance_checklist.md | 2.1 | 🔴 C — Internal | Operational guideline; no statutory basis or requirement |
| 39 | 2 business days — cash deposit deadline | event_compliance_checklist.md | 2.3, 3.1 | 🔴 C — Internal | Internal financial control; not statutory |
| 40 | 7 days — checklist filing with Secretary | event_compliance_checklist.md | preamble note | 🔴 C — Internal | Internal policy choice |
| 41 | 4 hours — volunteer meal reimbursement eligibility threshold | volunteer_management_policy.md | 5.2 | 🔴 C — Internal | Internal policy choice; no statutory basis |
| 42 | President's report suggested 300–500 words | agm_report_template.md | A3 | 🔴 C — Internal | Drafting guidance only; no legal significance |

---

## Category Definitions

| Category | Meaning | Action Required |
|----------|---------|----------------|
| ✅ **A — Statutory** | Number is directly sourced from a specific section of NZ legislation | No change needed; cite the section in the policy |
| ⚠️ **B — Verify** | Number is likely correct based on common practice or adjacent legislation, but the exact statutory source was not verified at time of drafting | Verify with solicitor or against the specific Act before adoption |
| 🔴 **C — Internal** | Number is an internal policy choice with no specific statutory mandate | Document the internal rationale; these are legally permissible internal controls but should be reviewed by the Committee for suitability |

---

## Priority Issues for Legal Review

These items carry the highest risk because they could create a false impression of statutory obligation:

### 1. AML/CFT Thresholds (Items 25–26)

**Location:** `overseas_funding_rules.md` clauses 4.2 and 6.1(c)

The NZD 1,500 and NZD 5,000 thresholds are presented in the policy without citing a specific legal source. They were set as conservative internal limits. HCCA should confirm:
- Whether HCCA is a "reporting entity" under the AML/CFT Act 2009 (most small charities are not)
- If HCCA is not a reporting entity, what overseas funding due diligence obligations actually apply
- Whether to retain these thresholds as internal policy or replace them with reference to Charities Services guidance

**Recommended fix:** Add a note to clause 4.2 stating these are conservative internal thresholds, and cite the specific Charities Services or DIA guidance document that informed them.

### 2. AGM Timing — 6 Months (Item 5)

**Location:** `constitution_template.md` clause 8.1

This is almost certainly correct (ISA 2022 s.126 or equivalent), but the precise section was not verified. The constitution is the most legally critical document — all statutory citations here should be exact.

### 3. General and Special Meeting Notice Periods — 14 and 21 Days (Items 12–13)

**Location:** `constitution_template.md` clause 10.1

ISA 2022 Schedule 1 sets minimum notice requirements for general meetings. The 14/21-day periods used here are common in NZ constitutions but the exact ISA 2022 minimums should be confirmed to ensure the constitution is compliant.

### 4. Financial Record Retention — 7 Years (Item 24)

**Location:** `financial_control_policy.md` clause 7.2

7 years is widely accepted in NZ, but the specific legal basis applicable to HCCA as a registered charity should be cited (likely a combination of IRD requirements and Charities Act 2005 reporting obligations).

---

## Items Confirmed as Internally Consistent

The following internal thresholds appear consistently across multiple documents (they cross-reference correctly, even if their absolute values are internal choices):

| Threshold | Appears in |
|-----------|-----------|
| NZD 500 dual signatory | financial_control_policy.md (cl. 3.4, 5.2) and overseas_funding_rules.md (cl. 7) |
| 60 days reimbursement | financial_control_policy.md (cl. 5.1) and volunteer_management_policy.md (cl. 5.3) |
| 30 days post-event financial summary | financial_control_policy.md (cl. 4.3) and event_compliance_checklist.md (cl. 3.1) |
| 2-year review cycle | dispute_resolution_policy.md (cl. 11) and conflict_of_interest_policy.md (cl. 9) |

---

*Audit Version: 1.0 | Generated: 2026-06-26 | For internal governance use — not a legal opinion.*
