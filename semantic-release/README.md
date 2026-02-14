# Semantic Release Action

Runs semantic-release for Forgejo/Gitea.

## Usage

```yaml
- uses: https://git.chaops.de/rwxd/forgejo-actions/semantic-release@main
  with:
    gitea_token: ${{ secrets.FORGEJO_TOKEN }}
    gitea_url: ${{ github.server_url }}
```

Requires `.releaserc.yml` and conventional commits.
