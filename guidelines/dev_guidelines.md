# Development Guidelines

# Development Flow

> Moved from dev_flow.md

For our development process we use Gitflow as the guiding compass. That doesn't mean that we follow the entire flow to the exhaustion but we do follow key aspects of it.

It's recommended that you read through this [Gitflow Explanation](https://datasift.github.io/gitflow/IntroducingGitFlow.html).

The things we will not be following are:

* The `deploy -> test -> fix -> redeploy -> retest` cycle will be done not on a release but on the **develop branch**. This means that from time to time that branch will be frozen until all the features being tested are approved;
* Once we are happy with the **develop branch** we will merge it into the **master branch**. We will not have **release branches** and we will not tag the release version;

## Flow Checklist

* **feature branch** is created from the **develop branch**;
* **feature branch** has PRs created into the **develop branch**;
* Always rebase your **feature branch** with the **develop branch** before opening a new PR;
* **hotfix branch** is created from the **master branch**;
* **hotfix branch** has PRs created into the **develop branch** and **master branch**;

# PR Rules

When done working on a **feature branch** you are expected to open a PR to the **develop branch**.

If you wish to create a PR before your code is ready to be reviewed you just need to mark your PR as a [draft](https://github.blog/2019-02-14-introducing-draft-pull-requests/).

Then a small set of rules applies to all PRs.

## PR Title

> Moved from prs.md

When creating a PR on GitHub the title is expected to have the format `{{ JIRA-TASK }}: {{ MESSAGE }}`. E.g., `ARX-1058: add filter by vat number`

## Branch Name

All the branches should be named following the standard: `feature/{{ JIRA_TASK }}(-{{ MESSAGE }})?`. The message is optional and when defined use `-` to separate words. E.g., `feature/ARX-1058` or `feature/ARX-1058-filter-by-vat-number`.

## Commit Messages

Commit messages **must** be meaningful and **must** follow the same standard: `{{ JIRA-TASK }} ({{ CHANGE }}): {{ MESSAGE }}`.

Luckily you can easily follow this guidelines easily because each repo you work in should have a `.cmf.yaml` file on its root with the standard. To use it you just need to run `npm i -g go-cmf`. Then when you want to commit your staged changes just type `cmf` and follow the instructions.

All you need to make sure is that when you create commit messages is that the **Jira Task ID** when you are working on a feature branch only has the jira task number. E.g., the feature branch `feature/ARX-1234-some-branch-description` should have `ARX-1234`. For now the CMF tool does not support a way for us to automate that but there is a [discussion open](https://github.com/walmartdigital/commit-message-formatter/issues/10) to add that functionality to the config files.
