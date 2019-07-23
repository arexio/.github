# PR Rules

When done working on a **feature branch** you are expected to open a PR to the **develop branch**.

If you wish to create a PR before your code is ready to be reviewed you just need to mark your PR as a [draft](https://github.blog/2019-02-14-introducing-draft-pull-requests/).

Then a small set of rules applies to all PRs.

## PR Title

When creating a PR on GitHub the title is expected to have the format `{{ JIRA-TASK }}: {{ MESSAGE }}`. E.g., `ARX-1058: add filter by vat number`

## Branch Name

All the branches should be named following the standard: `feature/{{ JIRA_TASK }}(-{{ MESSAGE }})?`. The message is optional and when defined use `-` to separate words. E.g., `feature/ARX-1058` or `feature/ARX-1058-filter-by-vat-number`.

## Commit Messages

Commit messages **must** be meaningful and **must** follow the same standard: `{{ JIRA-TASK }} ({{ CHANGE }}): {{ MESSAGE }}`.

Luckily you can easily follow this guidelines easily because each repo you work in should have a `.cmf.yaml` file on its root with the standard. To use it you just need to run `npm i -g go-cmf`. Then when you want to commit your staged changes just type `cmf` and follow the instructions.

All you need to make sure is that when you create commit messages is that the **Jira Task ID** when you are working on a feature branch only has the jira task number. E.g., the feature branch `feature/ARX-1234-some-branch-description` should have `ARX-1234`. For now the CMF tool does not support a way for us to automate that but there is a [discussion open](https://github.com/walmartdigital/commit-message-formatter/issues/10) to add that functionality to the config files.
