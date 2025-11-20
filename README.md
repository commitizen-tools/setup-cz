# setup-cz

> Github action to only configure cz CLI

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
      - uses: actions/setup-cz@main
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
<!--doc_end-->
