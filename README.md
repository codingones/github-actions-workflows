# CodingOnes GitHub Actions Workflows

## About

CodingOnes GitHub Actions Workflows is a toolkit providing a collection of reusable GitHub Actions Workflows.

See [workflows directory](.github/workflows) for a list of all available workflows.

## Table of contents

- 🪧 [About](#about)
- 🛠️ [Usage](#usage)
- 🙌 [Contributing](#contributing)
- 📝 [Licence](#licence)

## Usage

### Create Terraform Cloud Workspace for AWS ephemeral environment

```yml
create-feature-branch-workspace:
  name: Create feature branch workspace
  uses: codingones/github-actions-workflows/.github/workflows/create-terraform-cloud-workspace-for-aws-ephemeral-environment.terraform.yml@main
  with:
    product: 'codingones' # todo: replace with your own product name
    service: 'invoice-api' # todo: replace with your own service name
    branch: ${{ github.event.ref }}
  secrets:
    TF_API_TOKEN: ${{ secrets.TF_API_TOKEN }}
    AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
    AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
```

### Apply Terraform

```yml
deploy-feature-branch-environment:
  name: Deploy feature branch environment
  needs:
    - create-feature-branch-workspace
  uses: codingones/github-actions-workflows/.github/workflows/apply.terraform.yml@main
  with:
    infrastructure-repository: 'codingones/invoice-api-infrastructure' # todo: replace with your own repository to deploy
    workspace-name: ${{ needs.create-feature-branch-workspace.outputs.tf-workspace }}
  secrets:
    TF_API_TOKEN: ${{ secrets.TF_API_TOKEN }}
```

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) file in this repository.

## Licence

See [LICENSE.md](./LICENSE.md) file in this repository.
