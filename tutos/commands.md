## Checkout, Reset, Revert

{% hint style="info" %}
https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting
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

https://github.com/git-guides/git-remote

TODO