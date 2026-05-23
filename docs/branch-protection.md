# Branch Protection Configuration

## Required settings (GitHub UI → Settings → Branches → Add branch ruleset)

### Ruleset: protect-main — apply to `main`

| Setting | Value |
|---------|-------|
| Require a pull request | ✅ |
| Required approvals | 1 (increase to 2 for production repos) |
| Dismiss stale reviews on push | ✅ |
| Require review from code owners | ✅ |
| Require status checks to pass | ✅ |
| Required checks | terraform-validate, tflint, checkov |
| Require branches to be up to date | ✅ |
| Block force pushes | ✅ |
| Restrict deletions | ✅ |

### Ruleset: protect-release — apply to `release/*`

| Setting | Value |
|---------|-------|
| Require a pull request | ✅ |
| Required approvals | 2 |
| Block force pushes | ✅ |

## CODEOWNERS

Create .github/CODEOWNERS:

* @your-org/platform-team
modules/ @your-org/platform-team
.github/workflows/ @your-org/devops-team

## Environments (Settings → Environments)

| Environment | Required reviewers | Deployment branches |
|-------------|-------------------|---------------------|
| dev | None | main, feature/* |
| staging | 1 platform engineer | main |
| prod | 2 platform engineers | main (tags only) |
