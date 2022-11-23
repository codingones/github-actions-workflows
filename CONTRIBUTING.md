# Contributing to CodingOnes GitHub Actions Workflows

## Table of contents

- 📦 [Prerequisites](#prerequisites)
- 🚀 [Installation](#installation)
- 🤝 [Requirements](#requirements)
- 🏗️ [Built with](#built-with)
- 🎉 [Releases](#releases)

## Prerequisites

- [Git](https://git-scm.com/): software for distributed version control
- [GitHub](https://github.com/): an Internet hosting service for software development

## Installation

```shell
git clone git@github.com:codingones/github-actions-workflows.git
```

## Requirements

### Branches naming rules

- Must be up-to-date with main (rebased, linear history)
- Must be prefixed with follow the `build/`, `chore/`, `ci/`, `docs/`, `feat/`, `fix/`, `perf/`, `refactor/`, `revert/`, `style/` or `test/` according to their content. See [Conventional Commits cheat sheet](https://kapeli.com/cheat_sheets/Conventional_Commits.docset/Contents/Resources/Documents/index)

### Commits rules

#### Format

Must follow conventional commits specification: [Commits Conventionnels](https://www.conventionalcommits.org/fr)

#### Verified

Commits must be verified: [About commit signature verification](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification)

#### Continuous integration check

All validation checks in workflow `Validate` must pass without failure

## Built with

### Tools

#### CI

- [GitHub Actions](https://docs.github.com/en/actions) is the continuous integration and deployment tool provided by GitHub
- No secrets required by this repository

## Releases

Release on GitHub are fully automated on merge on master with Semantic Release.
