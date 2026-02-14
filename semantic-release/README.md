# Semantic Release Action

Runs semantic-release for Forgejo/Gitea.

## Usage

```yaml
- uses: https://git.chaops.de/rwxd/forgejo-actions/semantic-release@main
  with:
    gitea_token: ${{ secrets.FORGEJO_TOKEN }}
    gitea_url: ${{ github.server_url }}
```

## Example .releaserc.yml

```yaml
plugins:
  - "@semantic-release/commit-analyzer"
  - "@semantic-release/release-notes-generator"
  - "@saithodev/semantic-release-gitea"

branches:
  - "main"
```

Requires conventional commits.
