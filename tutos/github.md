## What is GitHub?

- **GitHub** is a web-based platform that uses Git for version control.
- It allows you to store your repositories online and collaborate with others.
- Key features:
  - **Pull Request**: A request to merge changes from one branch to another, often used for code review.
  - **Fork**: A personal copy of someone else's repository.
  - **Clone**: A local copy of a remote repository.


```
 git pull
remote: Enumerating objects: 17, done.
remote: Counting objects: 100% (17/17), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 15 (delta 1), reused 15 (delta 1), pack-reused 0
Unpacking objects: 100% (15/15), 1.97 KiB | 503.00 KiB/s, done.
From github.com:ceri-num/git
   5647bb3..26292da  master     -> origin/master
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint:
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint:
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
fatal: Need to specify how to reconcile divergent branches.
```