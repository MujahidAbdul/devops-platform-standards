# Conventional Commits

This repo enforces [Conventional Commits](https://www.conventionalcommits.org/) on every commit message.
The `commitizen` pre-commit hook rejects any commit that doesn't follow the format.

## Format

<type>(<scope>): <description>

[optional body]

[optional footer(s)]

## Types

| Type | When to use |
|------|-------------|
| `feat` | A new feature or capability |
| `fix` | A bug fix |
| `docs` | Documentation changes only |
| `style` | Formatting, whitespace — no logic change |
| `refactor` | Code restructuring — no feature/fix |
| `perf` | Performance improvement |
| `test` | Adding or fixing tests |
| `chore` | Build process, tooling, dependencies |
| `ci` | CI/CD pipeline changes |
| `revert` | Reverts a previous commit |

## Examples

feat(vpc): add IPv6 support to VPC module
fix(ecs): correct task definition memory calculation
docs(contributing): update pre-commit setup instructions
chore(deps): bump pre-commit-terraform to v1.88.0
feat!: remove deprecated legacy outputs — BREAKING CHANGE: output names updated

## Scopes

Optional but recommended: vpc, ecs, eks, rds, iam, s3, alb, cloudwatch, ci, docs

## Setup

pip install pre-commit commitizen
pre-commit install --hook-type commit-msg
pre-commit install
