# Semantic Release Action

Composite action to run semantic-release for Forgejo/Gitea repositories.

## Usage

```yaml
- uses: rwxd/forgejo-actions/semantic-release@main
  with:
    gitea_token: ${{ secrets.FORGEJO_TOKEN }}
    gitea_url: ${{ github.server_url }}
```

## Inputs

- `gitea_token` (required): Forgejo/Gitea authentication token
- `gitea_url` (required): Forgejo/Gitea server URL

## Example Workflow

```yaml
jobs:
  release:
    runs-on: ubuntu-latest
    permissions:
      contents: write
      issues: write
      pull-requests: write
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0
          persist-credentials: false

      - uses: rwxd/forgejo-actions/semantic-release@main
        with:
          gitea_token: ${{ secrets.FORGEJO_TOKEN }}
          gitea_url: ${{ github.server_url }}
```

## What it does

- Installs Node.js 25
- Installs semantic-release and required plugins:
  - @semantic-release/changelog
  - @semantic-release/git
  - @saithodev/semantic-release-gitea
  - conventional-changelog-conventionalcommits
- Runs semantic-release to analyze commits and create releases

## Requirements

- Repository must have a `.releaserc.yml` configuration file
- Commits must follow conventional commit format
