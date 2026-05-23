# Contributing

## Prerequisites

pip install pre-commit commitizen

You also need: Terraform >= 1.5.0, tflint, terraform-docs, checkov

On macOS: brew install terraform tflint terraform-docs && pip install checkov

## Workflow

1. Branch from main: git checkout -b feat/your-feature
2. Make changes
3. Commit using conventional format: feat(scope): description
4. Open a PR — the PR template will guide you
5. CI runs pre-commit, validate, tflint, checkov automatically
6. One approval required to merge

## Running pre-commit locally

pre-commit run --all-files
pre-commit run terraform_fmt --all-files
pre-commit run gitleaks --all-files

## Generating changelogs

cz bump                    # bump version and update CHANGELOG.md
cz changelog --dry-run     # preview without bumping
