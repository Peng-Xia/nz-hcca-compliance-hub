# HCCA Compliance Git Flow
# HCCA 合规变更管理流程

**NZ Chinese Heritage & Community Alliance Inc. (HCCA)**

> This document defines how HCCA uses GitHub to manage constitutional and policy changes in a transparent, auditable, and legally compliant manner — ensuring that the **main branch always reflects duly adopted and democratically approved governance documents**.

---

## 1. Branch Strategy / 分支策略

```
main (protected)
│  ← Only via approved PR + required Committee/member vote
│
├── drafts/[year]-[topic]     ← Working drafts (open to all Committee members)
├── review/[year]-[topic]     ← Ready for Committee review / vote
└── hotfix/[correction-desc]  ← Minor corrections (typos, formatting)
```

| Branch Type | Who can create | Who can merge to main | Approval required |
|-------------|---------------|----------------------|-------------------|
| `main` | N/A (protected) | Secretary or President only | See Section 3 |
| `drafts/...` | Any Committee member | — | No (working branch) |
| `review/...` | Secretary or President | Secretary or President | Committee resolution |
| `hotfix/...` | Secretary | Secretary | Secretary approval only |

**Branch Protection Rules for `main` (configure in GitHub Settings → Branches):**
- Require pull request reviews: minimum **2 approving reviews** for constitutional amendments; **1** for policy amendments
- Dismiss stale reviews when new commits are pushed: ✅
- Require status checks to pass: ✅ (`nz-act-compliance-check` workflow must pass)
- Require linear history: ✅
- Restrict who can push to matching branches: Committee officer accounts only
- Do not allow force pushes: ✅

---

## 2. Types of Changes and Required Process / 变更类型与流程要求

### 2A. Minor Corrections (Typos, Formatting, Non-Substantive Clarifications)

1. Secretary (or any officer) creates a `hotfix/[description]` branch.
2. Makes the correction and opens a Pull Request.
3. Secretary reviews and approves.
4. Secretary merges to `main`.
5. Change noted in next Committee meeting minutes.

**Automated check:** GitHub Actions compliance keyword check must pass before merge.

---

### 2B. Policy Amendment (Substantive change to any non-constitutional policy)

**Requires: Committee resolution (simple majority of Committee members)**

**Step-by-step process:**

```
1. DRAFT PHASE
   ┌──────────────────────────────────────────────────────┐
   │ Any officer creates drafts/[year]-[policy-topic]     │
   │ branch from main.                                    │
   │ Drafts changes. Opens DRAFT pull request.            │
   └──────────────────────────────────────────────────────┘
                          ↓
2. COMMITTEE REVIEW
   ┌──────────────────────────────────────────────────────┐
   │ PR shared with all Committee members (via GitHub     │
   │ review request or email notification).               │
   │ Committee discusses at a Committee meeting.          │
   │ Each member reviews the PR on GitHub.                │
   └──────────────────────────────────────────────────────┘
                          ↓
3. COMMITTEE RESOLUTION
   ┌──────────────────────────────────────────────────────┐
   │ Committee votes (simple majority required).          │
   │ Resolution recorded in meeting minutes.              │
   │ Resolution number entered in PR description.         │
   │ Interested officers recused from vote (per COI       │
   │ Policy).                                             │
   └──────────────────────────────────────────────────────┘
                          ↓
4. APPROVAL AND MERGE
   ┌──────────────────────────────────────────────────────┐
   │ PR marked "Ready for Review" (remove DRAFT status).  │
   │ Minimum 1 Committee member approves via GitHub       │
   │ review.                                              │
   │ GitHub Actions compliance check passes.              │
   │ Secretary or President merges to main.               │
   └──────────────────────────────────────────────────────┘
                          ↓
5. POST-MERGE
   ┌──────────────────────────────────────────────────────┐
   │ PR link recorded in Committee minutes.               │
   │ Members notified of policy change.                   │
   └──────────────────────────────────────────────────────┘
```

---

### 2C. Constitutional Amendment (Any change to constitution_template.md)

**Requires: Special Resolution (75% of votes cast at a General Meeting, with 21 days' notice)**

**This is the most stringent process and must not be shortcut.**

```
1. PROPOSAL
   ┌──────────────────────────────────────────────────────┐
   │ Officer or member submits proposed amendment in      │
   │ writing to Secretary.                                │
   │ Committee reviews feasibility and ISA 2022           │
   │ compliance.                                          │
   └──────────────────────────────────────────────────────┘
                          ↓
2. DRAFT BRANCH
   ┌──────────────────────────────────────────────────────┐
   │ Secretary creates drafts/[year]-constitution-[topic] │
   │ branch.                                              │
   │ Proposed amendment committed to branch.              │
   │ DRAFT PR opened — clearly labelled                   │
   │ "[CONSTITUTIONAL AMENDMENT — NOT YET ADOPTED]"       │
   └──────────────────────────────────────────────────────┘
                          ↓
3. MEMBER NOTICE
   ┌──────────────────────────────────────────────────────┐
   │ Secretary gives ALL financial members at least       │
   │ 21 days' notice of the proposed amendment.           │
   │ Notice includes: full text of proposed amendment     │
   │ and date/location of General Meeting.                │
   │ Link to the DRAFT PR included in notice.             │
   └──────────────────────────────────────────────────────┘
                          ↓
4. GENERAL MEETING — SPECIAL RESOLUTION VOTE
   ┌──────────────────────────────────────────────────────┐
   │ Members debate and vote at the General Meeting.      │
   │ Special Resolution requires ≥75% of votes cast.     │
   │ Result recorded in signed General Meeting minutes.   │
   └──────────────────────────────────────────────────────┘
                          ↓
5. MERGE (only if Special Resolution PASSED)
   ┌──────────────────────────────────────────────────────┐
   │ PR description updated with: resolution date,        │
   │ vote count (FOR/AGAINST), quorum present.            │
   │ Minimum 2 Committee member approvals via GitHub      │
   │ review (must include President).                     │
   │ GitHub Actions compliance check MUST pass.           │
   │ Secretary merges to main.                            │
   └──────────────────────────────────────────────────────┘
                          ↓
6. STATUTORY NOTIFICATIONS (within 20 working days)
   ┌──────────────────────────────────────────────────────┐
   │ Notify Registrar of Incorporated Societies.          │
   │ Notify Charities Services (if applicable).           │
   │ Record in HCCA Annual Report.                        │
   └──────────────────────────────────────────────────────┘
```

---

## 3. Commit Message Convention / 提交信息规范

All commits to policy/constitutional documents should follow this format:

```
[TYPE] Brief description of change

TYPE options:
  DRAFT      — Work in progress, not yet adopted
  POLICY     — Adopted policy amendment (include resolution no.)
  CONST      — Adopted constitutional amendment (include resolution no. + vote count)
  HOTFIX     — Minor non-substantive correction
  TEMPLATE   — Change to a template or checklist

Examples:
  DRAFT: Revise overseas funding AML threshold to NZD 2,000
  POLICY: Update financial control dual-signatory threshold — Resolution 2025-03
  CONST: Amend Section 2.1 to add digital literacy purpose — Res 2025-AGM-01, 34Y/4N
  HOTFIX: Fix broken link to Interests Register in COI Policy
```

---

## 4. GitHub Recommended Settings / GitHub推荐设置

Configure the following in GitHub repository Settings:

### General
- Default branch: `main`
- Automatically delete head branches after merge: ✅

### Branch Protection (main)
- Require a pull request before merging: ✅
- Required approving reviews: **2** (constitutional), **1** (policy)
- Dismiss stale pull request approvals when new commits are pushed: ✅
- Require status checks to pass before merging: ✅
  - Required status check: `compliance-keyword-check`
  - Required status check: `section26-check`
- Require branches to be up to date before merging: ✅
- Restrict who can push to matching branches: Secretary, President
- Allow force pushes: ❌ (never)
- Allow deletions: ❌

### Collaborators and Teams (suggested)
| GitHub Team | Members | Permission |
|-------------|---------|-----------|
| `hcca-committee` | All officers | Write (branches) |
| `hcca-officers` | President, Secretary, Treasurer | Admin (PR approval, merge to main) |
| `hcca-members` | Financial members | Read |

---

## 5. Audit Trail / 审计追踪

The git history of this repository constitutes an **immutable audit trail** of all governance changes. Every adopted policy and constitutional change can be traced to:

- The commit where it was introduced (including author, date, and commit message);
- The Pull Request where it was reviewed and approved;
- The comments and reviews on the PR (Committee members' GitHub reviews = electronic approval record);
- The GitHub Actions compliance check result; and
- The PR description, which must record the resolution number and vote outcome.

**This audit trail is considered part of HCCA's governance records** and must be preserved for the life of the organisation.

---

## 6. Bilingual Document Management & Sync Rule / 双语文件管理与同步规则

### 6.1 Document Language Structure

All policy and constitutional documents in this repository exist in two versions:

| File Suffix | Version Type | Authority | Use Case |
|-------------|-------------|-----------|----------|
| `<filename>.md` | **Primary English** — Official | **Legally operative** | Official submission, regulatory reporting, governance decisions |
| `<filename>_ZH_REF.md` | **Chinese Reference** — 参考译本 | Reference only / 仅供参考 | Member communication, reading comprehension |

**In case of any discrepancy between the English and Chinese versions, the English primary version prevails.**

若中英文版本存在任何差异，**以英文主版本为准**。

### 6.2 Mandatory Chinese Reference File Sync / 强制同步规则

> **Every update to a primary English document MUST be accompanied by a corresponding update to its `_ZH_REF.md` Chinese reference file in the same Pull Request.**
>
> **每次对英文主版本文件的更新，必须在同一 Pull Request 中同步更新对应的 `_ZH_REF.md` 中文参考版本。**

This rule exists to prevent members who rely on the Chinese reference version from acting on outdated or incorrect information.

**Pull Requests that modify a primary English document without updating the corresponding `_ZH_REF.md` file MUST NOT be merged.**

Chinese reference file updates must:

*(a)* Reflect **all substantive changes** made to the English primary file;
*(b)* Maintain the same structure, clause numbering, and cross-references as the English primary;
*(c)* Retain all **legal terms, policy names, Act/Section references, and officer titles in English** (do not translate these);
*(d)* Be included in the **same PR** as the English change — separate "sync" PRs are not acceptable, as they break the audit trail; and
*(e)* Be reviewed for translation accuracy by at least one bilingual Committee member before the PR is merged.

### 6.3 Checklist for PR Approvers / PR审核方核查清单

Before approving any PR that modifies policy or constitutional documents:

- [ ] The corresponding `_ZH_REF.md` file has been updated **in this PR**
- [ ] The Chinese translation accurately reflects all substantive changes to the English primary
- [ ] Legal terms, Section references, policy names, and officer titles are retained in English in the Chinese file
- [ ] The PR description includes the Chinese sync confirmation (Section 3.5 of the PR template)
- [ ] No separate "Chinese sync" PR is outstanding or planned — the sync is complete here

---

*GOVERNANCE.md Version: 1.0 | Adopted: [DATE] | See git history for amendments.*
