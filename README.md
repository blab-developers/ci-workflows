# ci-workflows

Shared GitHub Actions reusable workflows for the workspace's two repo families (`bidwej-*` and
`eai-*`). One implementation, one upgrade point: consumers keep an 8-line caller workflow and
pin nothing here.

## secret-scan

Full-history Betterleaks scan, owned here: the `dortort/betterleaks-action` SHA, the Betterleaks
version (v1.9.0, the eai-core pin), checkout config and scan mode all live in this file.

Caller (`.github/workflows/secret-scan.yml` in each consumer):

```yaml
name: secret-scan

on:
  push:
  pull_request:

jobs:
  secret-scan:
    uses: blab-developers/ci-workflows/.github/workflows/secret-scan.yml@v1
```

## Versioning

- `@v1` is the moving major tag; patch/minor releases move it within the major.
- Major releases (`v2`) may change inputs, permissions or behavior — consumers pin `@v1` and adopt deliberately.
- The third-party action is pinned by full commit SHA in this repository only.
