# install-nhost-cli

Github action to install Nhost CLI

## Usage

To install the latest Nhost CLI:

```yaml
    - name: Install Nhost CLI
      id: install-nhost-cli
      uses: nhost-actions/install-nhost-cli@v1
```

To install a specific version of the Nhost CLI you can use instead:

```yaml
    - name: Install Nhost CLI
      id: install-nhost-cli
      uses: nhost-actions/install-nhost-cli@v1
      with:
        version: v1.2.0
```

## Outputs

The action provides the `version` output with the version installed. For instance:

```yaml
---
name: "test action"
on:
  push:
  pull_request:

jobs:
  tests:
    runs-on: ubuntu-latest

    steps:
    - name: "Check out repository"
      uses: actions/checkout@v3

    - name: Install Nhost CLI
      id: install-nhost-cli
      uses: nhost-actions/install-nhost-cli@v1

    - name: Verify version
      run: echo "${{ steps.install-nhost-cli.outputs.version }}"
      shell: bash
```
