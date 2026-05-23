# devops-platform-standards

[![CI](https://github.com/MujahidAbdul/devops-platform-standards/actions/workflows/ci.yml/badge.svg)](https://github.com/MujahidAbdul/devops-platform-standards/actions/workflows/ci.yml)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg)](https://conventionalcommits.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Engineering standards for DevOps and platform teams — shipped as code, not wikis.

Pre-commit hook stack, conventional commit enforcement, PR templates, branch protection rules, and automated changelog generation. Drop this into any team and you have consistent, auditable, automated standards from day one.

## What's in here

| File / folder | Purpose |
|---------------|---------|
| `.pre-commit-config.yaml` | Full Terraform hook stack: fmt, validate, docs, tflint, checkov + secrets scan |
| `pyproject.toml` | Commitizen config: semver versioning, auto-changelog |
| `CONVENTIONAL-COMMITS.md` | Commit message guide with examples and type reference |
| `.github/pull_request_template.md` | PR checklist: Terraform, security, docs, changelog |
| `docs/branch-protection.md` | GitHub branch protection ruleset configuration |
| `CONTRIBUTING.md` | How to set up, branch, commit, and raise a PR |
| `CHANGELOG.md` | Auto-generated on every merge to main |
| `.github/workflows/ci.yml` | CI: runs pre-commit on every PR |
| `.github/workflows/changelog.yml` | Auto-bumps version and updates CHANGELOG on merge |

## Quick start

pip install pre-commit commitizen
pre-commit install --hook-type commit-msg
pre-commit install
pre-commit run --all-files

## Pre-commit hook stack

terraform_fmt, terraform_validate, terraform_docs, terraform_tflint, terraform_checkov,
trailing-whitespace, end-of-file-fixer, check-yaml, detect-private-key,
check-added-large-files, gitleaks, commitizen

## Related repos

| Repo | What it is |
|------|-----------|
| [terraform-aws-platform-modules](https://github.com/MujahidAbdul/terraform-aws-platform-modules) | Terraform module library — VPC, ECS, EKS, RDS, CloudWatch |
| [github-actions-terraform-platform](https://github.com/MujahidAbdul/github-actions-terraform-platform) | Reusable GitHub Actions for Terraform pipelines |
| [aws-platform-self-service-hub](https://github.com/MujahidAbdul/aws-platform-self-service-hub) | Self-service AWS provisioning via workflow_dispatch |
