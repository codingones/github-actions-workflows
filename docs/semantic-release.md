### Semantic release

Example with npm
```yml
name: Release

on:
  workflow_dispatch:
  push:
    branches:
      - 'main'

jobs:
  release:
    uses: codingones/github-actions-workflows/.github/workflows/semantic-release.yml@main
    secrets:
      PAT: ${{ secrets.PAT }}
```

Example with yarn
```yml
name: Release

on:
  workflow_dispatch:
  push:
    branches:
      - 'main'

jobs:
  release:
    uses: codingones/github-actions-workflows/.github/workflows/semantic-release.yml@main
    with:
      install-dependencies-command: "yarn install --frozen-lockfile"
      cache-dependency-path: "yarn.lock"
    secrets:
      PAT: ${{ secrets.PAT }}
```