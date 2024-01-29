# Semantic Versioning GitHub Workflow

This repository contains a shared GitHub Actions workflow file for semantic versioning. The workflow automates the process of determining the new version, creating tags, and handling releases based on the specified release type.

## Usage

To use this shared semantic workflow in your repository, follow these steps:

### 1. Include Semantic Workflow File

Create a file named `.github/workflows/semantic.yml` in your repository with the following content:


### 2. Sample to use semantic workflow

```yaml
name: Build and Release

on:
  push:
    branches:
      - main

jobs:
  build-and-release:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Use Shared Semantic Versioning Workflow
        uses: ./.github/workflows/semantic.yml
        with:
          ReleaseType: ${{ github.event.inputs.ReleaseType }}
          Environment: ${{ github.event.inputs.Environment }}
          Release: ${{ github.event.inputs.Release }}