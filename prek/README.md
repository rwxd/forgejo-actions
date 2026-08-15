# Prek

Run [prek](https://github.com/rwxd/prek) (pre-commit) checks in Forgejo workflows.

## Usage

```yaml
- name: Run prek
  uses: https://${{ secrets.FORGEJO_TOKEN }}@git.chaops.de/rwxd/forgejo-actions/prek@main
  with:
    args: "run --all-files"
```

## Inputs

| Name | Description | Default |
|------|-------------|---------|
| `args` | Arguments to pass to prek | `run --all-files` |
