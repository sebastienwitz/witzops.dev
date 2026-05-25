# Repository Hardening

Recommended GitHub repository settings for witzops.dev. These steps protect
the main branch and enable automated security scanning.

## Branch protection and ruleset

### Recommended GitHub ruleset for `main`

Apply a ruleset at the repository level targeting the `main` branch.

- **Require a pull request before merging**
  - 1 approval required
  - Dismiss stale pull request approvals when new commits are pushed
  - Require conversation resolution before merging
- **Require status checks to pass before merging**
  - `Build Astro site` (CI workflow)
  - `CodeQL Analyze` (after first successful run)
- **Block force pushes**
- **Block branch deletion**
- **Prefer squash merge** (add at the repository settings level or via the
  ruleset merge queue configuration)

### Manual setup checklist

Settings must be configured in the GitHub UI (repository Settings > Rules >
Rulesets):

- [ ] Create a ruleset targeting `main`
- [ ] Enable "Require a pull request before merging" with 1 approval
- [ ] Enable "Dismiss stale pull request approvals when new commits are pushed"
- [ ] Enable "Require conversation resolution before merging"
- [ ] Add `Build Astro site` as a required status check
- [ ] Add `CodeQL Analyze` as a required status check (after first successful run)
- [ ] Enable "Block force pushes"
- [ ] Enable "Restrict deletions"
- [ ] Configure squash merge as the default merge method

## Secret scanning

### Recommended

Enable secret scanning and push protection in the GitHub UI (repository
Settings > Code Security):

- [ ] Enable secret scanning
- [ ] Enable push protection (blocks pushes containing secrets)

## Dependabot alerts

### Recommended

Enable Dependabot alerts and auto-updates in the GitHub UI (repository
Settings > Code Security):

- [ ] Enable Dependabot alerts
- [ ] Enable Dependabot security updates

## Code scanning (CodeQL)

### Post-PR setup

After merging the CodeQL workflow (`.github/workflows/codeql.yml`):

- [ ] Confirm the first CodeQL run completes successfully
- [ ] Add `CodeQL Analyze` as a required status check in the main ruleset

## Public content safety

This is a public repository. All contributors must follow the content safety
rules in [docs/publication-rules.md](publication-rules.md). The PR template
includes a public-safety checklist that must be verified before merging.
