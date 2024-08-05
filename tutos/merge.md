## Merge and Conflicts

When merging 2 branches, we want to merge the history of one branch (its commits) into the another one.

## Fast-forward

Such a merge might be really easy if one branch is pointing a commit in the history of the other one (fast-forward).

![Simplest merge case: fast-forward](../imgs/git-merge-fastforward.png)

## Merge

![Typical merge case](../imgs/git-merge.png)

Regular merge creates a new commit usually called the merge commit.

## Rebase

![Rebase](../imgs/git-rebase.png)

You are working on a bugFix but main evolves (1 commit not in the bugFix branch).
You can rebase the bugFix branch on the latest commit in the main branch.
It means that all commits in the bugFix branch will be re-applied.
After the rebase, we could merge bugFix into main and it would always be a fast-forward.

## Take away

- Fast-forward is the simplest case
- Prefer rebase over merge locally
- Always merge (never rebase) public (pushed) branches (see later)

## Bibliography

- <https://www.atlassian.com/git/tutorials/merging-vs-rebasing>

