# Development Flow

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
