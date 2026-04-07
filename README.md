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
      - uses: actions/checkout@v6
        with:
          fetch-depth: 0
          fetch-tags: true
      - uses: commitizen-tools/setup-cz@main
        with:
          python-version: "3.x"
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
|`extra-requirements`|Install extra dependencies|n/a|no|
|`extra_requirements`|DEPRECATED, use `extra-requirements` instead. Install extra dependencies|n/a|no|
|`python-version`|Version range or exact version of Python or PyPy to use, using SemVer's version range syntax. Reads from .python-version if unset. Passed directly to setup-python|n/a|no|
|`set-git-config`|Set git config|`true`|no|
## Outputs
None
<!--doc_end-->


## Troubleshooting

### A ruleset is blocking the release

You have 2 options:

1. Create a Github App (**recommended**)
2. Create a Personal Access Token (PAT)

A PAT is associated to your personal account, while the Github App is like a bot.
Whichever you choose, you'll have to add it to the exemption list in the ruleset.

For the Github App, you can find the instructions to create one in [Registering a Github App](https://docs.github.com/en/apps/creating-github-apps/registering-a-github-app/registering-a-github-app) and a detail tutorial in [this discussion](https://github.com/orgs/community/discussions/25305#discussioncomment-8256560)
