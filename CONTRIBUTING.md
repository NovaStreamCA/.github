---
policy_id: NS-GOV-CONTRIB-001
title: NovaStream Contribution Policy
version: 1.0.0
status: Active
effective_on: 2025-01-01
owner: legal@novastream.ca
---

# Contributing to NovaStream Projects

Thank you for your interest in contributing to NovaStream projects.
This guide defines our professional engineering standards for all
contributors.

---

## Contributor Requirements

To contribute to any NovaStream repository, you must:

- Use a valid GitHub account.
- Agree to the NovaStream Code of Conduct.
- Submit only original work or properly licensed contributions.
- Follow all security, privacy, and compliance requirements.

---

## Development Workflow

All changes follow the **Pull Request workflow**.

1. **Fork or branch from `main`.**
2. **Commit your work using signed commits (GPG or SSH signing required).**
3. **Submit a Pull Request.**
4. **Pass all automated checks.**
5. **Receive required CODEOWNERS approval.**
6. **Merge via protected branch rules.**

Direct pushes to protected branches are prohibited.

---

## Commit Standards

### Signed Commits

All commits to NovaStream projects must be cryptographically signed.

Unsigned commits are rejected by branch protection rules.

---

### Commit Format

Use clear, descriptive commit messages:

Optional body explaining context or risks

Examples:

- `Fix: sanitize file upload handler`
- `Feature: add OAuth2 login`
- `Infra: tighten CI artifact retention`

## Branching Model

- `main` — Production
- `develop` — Active development when used
- `feature/<short-name>` — Feature work
- `fix/<short-name>` — Bug fixes
- `hotfix/<short-name>` — Production emergencies

Rebases and force-pushes to protected branches are prohibited.

## Pull Request Requirements

All PRs must:

- Reference the related issue or ticket where applicable.
- Include appropriate tests, validation steps, or documentation.
- Complete the PR template checklist:
  - Risk assessment completed
  - Security impact reviewed
  - Privacy compliance reviewed (if applicable)

---

## Code Standards

### General

- Code must pass all project linting rules.
- Prefer clarity over cleverness.
- Avoid breaking APIs or data migrations without explicit approval.

---

### Documentation

Any change that affects:

- API behavior
- Configuration options
- Deployment
- Compliance requirements

**Must include documentation updates.**
Documentation may reside in:

- `README.md`
- VitePress docs
- Architecture or ADR files
- Policy docs in `.github/`

---

## Testing

All changes must meet testing standards defined by the project:

- Unit tests where applicable.
- Manual testing verification included in the PR description.

CI failures must be resolved before review.

## Compliance and Privacy

NovaStream handles regulated data in some projects (PHIA / PIPEDA).

Contributors must:

- Avoid posting personal, health, or confidential data into public
  commits or issues.
- Flag any suspected compliance impact in PR descriptions.
- Adhere to policies in `.github/COMPLIANCE.md` when present.
  
## Licensing

By submitting contributions, you certify that:

- You have the right to submit the work.
- NovaStream may distribute the contribution under the project license.

## Getting Help

- For support issues: See `.github/SUPPORT.md`
- For development questions: Open a GitHub Discussion (if enabled)

Security issues must never be submitted as public tickets.

---

Thank you for helping us build secure, compliant software.
