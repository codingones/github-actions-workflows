### Node Validation Matrix

Example with npm

```yml
  validation:
    name: Validation
    uses: codingones/github-actions-workflows/.github/workflows/node-validation-matrix.yml@main
    with:
      validation-commands: '["npm run build", "npm run lint.es", "npm run lint.commit", "npm run prettier.check", "npm run test"]'
```

Example with yarn
```yml
  validation:
    name: Validation
    uses: codingones/github-actions-workflows/.github/workflows/node-validation-matrix.yml@main
    with:
      validation-commands: '["npm run build", "npm run lint.es", "npm run lint.commit", "npm run prettier.check", "npm run test"]'
```