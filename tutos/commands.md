## Stage all modifications in the workspace

```
$ git add -A
```

## Checkout, Reset, Revert

{% hint style="info" %}
Documentation: <https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting>
{% endhint %}

### Discarding all changes in your workspace

Discard all changes in your workspace and go back to the latest commit state of the current branch:
```
$ git reset --hard
```

### Remove last unpushed (or local only) commit

If you did not pushed yet, you can remove a commit and discard its content using:

```
git reset --hard HEAD~1
```

### Remove an already pushed (or public) commit

```
git revert HEAD~1
```

## Re-sync a fork or using multiple remotes

When you fork a repository R1 on github, you get your own copy R2.
You can then clone R2, work locally, commit, push to R2 and then issue pull request from R2 to R1.

However, if R1 gets new commits, they are not automatically propagated to your fork R2.
Through the web interface of Github, it is now possible to re-sync a fork by clicking a button.

It is also possible to do it in commandline locally on your clone of R2 by adding the original repository as a new remote usually named `upstream`:

```
$ git clone https://www.github.com/me/R2
$ cd R2
$ git remote -v
origin https://www.github.com/me/R2

$ git remote add upstream https://www.github.com/other/R1
```

You can then fetch and pull from upstream (R1) and merge upstream branches into your branches to then push them on origin (R2).

{% hint style="info" %}
Documentation: <https://github.com/git-guides/git-remote>
{% endhint %}

## Github CLI `gh`

{% hint style="info" %}
Documentation: <https://cli.github.com/>
{% endhint %}

The `gh` CLI uses the Github API to achieve github operations from command line.
This is useful to issue pull request, review issues, ... directly from commandline.

