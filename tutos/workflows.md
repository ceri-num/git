## Workflows

{% hint style="info" %}
Documentation: https://www.atlassian.com/git/tutorials/comparing-workflows
{% endhint %}

Git does not enforce a specific way of working.
Developpers of a team must define a common way of managing branches, ... to minimize conflicts and standardize development.

Most well-known workflows:

- The [feature branch model](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow): Complexity and overhead in managing multiple long-lived branches.
Integration challenges during feature merges.
- The [gitflow model](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow):
- The [trunk-based development](https://www.atlassian.com/continuous-delivery/continuous-integration/trunk-based-development). Should solve the [merge hell problem](https://connect2grp.medium.com/branching-strategies-for-the-development-teams-95cafd7806c4) in models with long-live feature branches.

## Code Review

Despite the workflow, Github eases code review through __pull request__.

Scenario: Julia develops in a branch named `feature/persistence`.
At some point, Julia will [create a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) from her branch `feature/persistence` to `main` for example.

Then, Lisa will review the pull request code, she can ask for modifications (Julia will add more commits), and she may integrate it in `main`.