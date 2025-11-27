# setup-cz

This workflow sets up the commitizen CLI for use in your GitHub workflows.
Unlike `commitizen-action`, this workflow only installs the CLI.
It does not automatically bump, commit or push changes.
This workflow, instead, gives more flexibility to the user by letting them
use the full range of commitizen commands.

## Usage

```yaml
jobs:
  bump:
    runs-on: ubuntu-latest
    permissions:
      contents: write
      actions: write
    steps:
      - uses: actions/checkout@v5
        with:
          fetch-depth: 0
          fetch-tags: true
      - uses: commitizen-tools/setup-cz@main
        with:
          python-version: "3.x"
      - name: Set up git config
        run: |
          git config --global user.name "github-actions[bot]"
          git config --global user.email "41898282+github-actions[bot]@users.noreply.github.com"
      - run: |
          cz version -p
          cz bump --yes --annotated-tag
          git push --follow-tags
```

<!--doc_begin-->
## Inputs
|Input|Description|Default|Required|
|-----|-----------|-------|:------:|
|`version`|Version of commitizen to install|`latest`|no|
|`extra_requirements`|Install extra dependencies|n/a|no|
## Outputs
None
<!--doc_end-->
