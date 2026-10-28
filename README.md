# OUJAI — `.github` Organization Governance Repository

## 1. Project Name and Summary
**OUJAI — `.github`** is the organization-level metadata and governance repository for the **OUJAI — Hospital Digital Twin** graduation project (Academic Year 2026–2027). It renders the public/organization profile README and provides default community health files, issue templates, and pull-request templates inherited across all eight OUJAI repositories.

## 2. Purpose and Responsibilities
- Host `.github/profile/README.md` displayed on `https://github.com/oujai`.
- Define organization-wide `CONTRIBUTING.md`, `SECURITY.md`, and `CODE_OF_CONDUCT.md`.
- Provide standardized GitHub Issue Templates (Bug Report, Feature/Task, Documentation) and `PULL_REQUEST_TEMPLATE.md`.
- Maintain the organization `CODEOWNERS` reference template.

## 3. Scope and Explicit Exclusions
- **In Scope:** Organization profile markdown, issue/PR templates, contribution rules, synthetic-data security policies.
- **Explicit Exclusions:** No application source code, no database schemas (owned by `oujai-docs` and `oujai-backend`), no Docker configurations (owned by `oujai-infrastructure`), and no secrets or tokens.

## 4. Primary Owner and Supporting Contributors
- **Primary Owner:** Member 1 — IT Student (`<GITHUB_USERNAME_IT>`)
- **Supporting Contributors:** Member 2 — DS-1 (`<GITHUB_USERNAME_DS1>`), Member 3 — DS-2 (`<GITHUB_USERNAME_DS2>`), Member 4 — DS-3 (`<GITHUB_USERNAME_DS3>`)

## 5. Technology Stack and Prerequisites
- GitHub Flavored Markdown (GFM)
- YAML (for GitHub Issue Forms)
- Git 2.40+

## 6. Installation and Setup Instructions
```bash
git clone https://github.com/oujai/.github.git
cd .github
```

## 7. Required Environment Variables
None. This repository contains static governance and template files only.

## 8. Exact Commands to Run Locally
Preview Markdown files locally using any Markdown viewer or linter:
```bash
ls -la profile/README.md ISSUE_TEMPLATE/ PULL_REQUEST_TEMPLATE.md
```

## 9. Expected Successful Startup Result
All template files exist and validate as UTF-8 Markdown/YAML. When pushed to the `main` branch of `oujai/.github`, GitHub automatically renders `profile/README.md` on the `https://github.com/oujai` landing page.

## 10. Testing Commands and Expected Results
Verify that no secrets, tokens, or clinical PII strings exist in governance files:
```bash
grep -rnE "(ghp_|sk-|BEGIN PRIVATE KEY)" . && echo "FAIL" || echo "PASS: No secrets detected"
```

## 11. Folder Structure
```text
.github/
├── CODEOWNERS                      # Template code ownership mapping
├── CODE_OF_CONDUCT.md              # Contributor Covenant v2.1 adapted for academic team
├── CONTRIBUTING.md                 # Branching, commit, PR, and review workflow
├── ISSUE_TEMPLATE/
│   ├── bug_report.md               # Standardized bug report template
│   ├── config.yml                  # Issue template chooser configuration
│   ├── documentation_task.md       # Documentation & contract update template
│   └── feature_task.md             # Feature / sprint task template
├── PULL_REQUEST_TEMPLATE.md        # PR checklist enforcing tests, contracts & synthetic data
├── README.md                       # This repository documentation file
├── SECURITY.md                     # Synthetic data mandate & secret protection policy
└── profile/
    └── README.md                   # Organization profile rendered at github.com/oujai
```

## 12. Interfaces Owned by This Repository
- Organization-wide GitHub Issue and Pull Request metadata structures.

## 13. Dependencies on Other OUJAI Repositories
- Links to all 7 sibling repositories (`oujai-docs`, `oujai-backend`, `oujai-web`, `oujai-mobile`, `oujai-data-science`, `oujai-iot-simulator`, `oujai-infrastructure`).

## 14. How to Contribute
1. Create a branch from `main` using `docs/<short-description>`.
2. Submit a Pull Request and request review from Member 1 (IT).
3. Merge via Squash and Merge once formatting is verified.

## 15. Troubleshooting
- **Profile README not showing on `github.com/oujai`:** Verify the file is placed at `profile/README.md` (at the root of the `.github` repository) and that the repository is named exactly `.github`.

## 16. Security and Synthetic-Data Requirements
Never commit real hospital floor plans with restricted security layouts, student personal phone numbers, or API tokens to the organization profile.

## 17. Definition of Done
- [x] `profile/README.md` renders all 9 features, 30-bed breakdown, tech stack, and 4-member matrix.
- [x] Issue and PR templates include mandatory synthetic-data verification checkboxes.

## 18. Related Repositories
- Central Documentation: [`oujai-docs`](https://github.com/oujai/oujai-docs)
- Infrastructure & Bootstrap: [`oujai-infrastructure`](https://github.com/oujai/oujai-infrastructure)
