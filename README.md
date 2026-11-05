# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) presets for the [hononeko](https://github.com/hononeko) organization.

## Presets

### `default` (Base)
Included automatically when referencing `github>hononeko/renovate-config`:
* `config:recommended`
* Semantic commit conventions (`chore` for Renovate PRs)
* Merge confidence badges
* SHA-pinning for third-party GitHub Actions (`helpers:pinGitHubActionDigests`)
* Reviewer assignment: `reviewersFromCodeOwners: true` and `additionalReviewers: ["vehkiya"]`

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>hononeko/renovate-config"
  ]
}
```

### `hononeko-actions`
Exempts `hononeko/actions` from SHA-pinning so consumers can follow the floating `@v1` major tag:
```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>hononeko/renovate-config",
    "github>hononeko/renovate-config:hononeko-actions"
  ]
}
```

### `actions-builder`
Regex managers for workflows and composite action files in repositories that author GitHub Actions:
```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>hononeko/renovate-config",
    "github>hononeko/renovate-config:actions-builder"
  ]
}
```
