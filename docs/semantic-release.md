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
      package-manager: 'yarn'
      install-dependencies-command: "yarn install --frozen-lockfile"
      cache-dependency-path: "yarn.lock"
    secrets:
      PAT: ${{ secrets.PAT }}
```

Example with npm for ecr
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
      AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
      AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
      AWS_DEFAULT_REGION: ${{ vars.AWS_DEFAULT_REGION }
```