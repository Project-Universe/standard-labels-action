# Issue labels generator

Adds labels used by @Project-Universe

## Usage

To use this Action, you only need the yaml file below.

```yaml
name: Import Project Universe Standard Labels

on:
  push:
    branches: [ main, dev ]

jobs:
  labels:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/setup-node@v2
      with:
        node-version: '16'
    - uses: Project-Universe/standard-labels-action@main
      with:
        github-token: ${{ secrets.GITHUB_TOKEN }}
        owner-name: ${{ github.repository_owner }}
        repository-name: ${{ github.event.repository.name }}
```

## Contributing to this project

To add a new label, update the `labels.json` file and the GitHub Action will do the rest for everyone!

```json
[
    {
        "name": "good first issue",
        "color": "7f0799"
    },
    {
        "name": "💬 talk: discussion",
        "color": "f9bbe5"
    } 
]
```
