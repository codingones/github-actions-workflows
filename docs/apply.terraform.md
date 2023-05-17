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