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