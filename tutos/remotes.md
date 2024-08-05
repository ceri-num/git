## Remote repositories

A git repository can have remotes i.e. distant git repositories to exchange with.

Obviously, a locally created repository (using git init for example) doesn't have any remote.

List remotes of a local git repository:
```
$ git remote -v
```

To simplify the management of remote git repositories, let's use github.

## GitHub

{% hint style="info" %}
Documentation: <https://docs.github.com/>
{% endhint %}

**GitHub** is a web-based platform that hosts git repositories and give access to it.
It allows you to store your repositories online and collaborate with others.


## Creating and cloning your first Github repository

1. Create an account on <https://www.github.com>
2. Create a repository named MyFirstRepository
3. Copy the HTTPS URL of this new repository
4. Clone this repository on your machine using this https URL

```
$ git clone https://github.com/LucFabresse/MyFirstRepository.git
$ cd MyFirstRepository
$ git remote -v
origin	https://github.com/LucFabresse/MyFirstRepository.git (fetch)
origin	https://github.com/LucFabresse/MyFirstRepository.git (push)
```

Contrary to a locally created repository (using git init), a cloned repository has remote repository named __origin__ automatically configured.
This allows you to **fetch**, **push** or **pull** from this remote repository.

{% hint style="info" %}
Documentation: <https://www.atlassian.com/git/tutorials/syncing>
{% endhint %}

![Git operations ([credit to glasskube.dev](https://glasskube.dev/guides/git/))](../imgs/git-operations.png)

Speficic Github operations:
- **Fork**: A personal copy of someone else's repository.
- **Pull Request**: A request to merge changes from one branch to another, often used for code review.

## Operations involving remote repositories

- **Clone**: A local copy of a remote repository.
- **Push**: Send local commits to a remote repository.
- **Pull**: Get remote commits into a local repository and checkout the corresponding workspace.

Example:
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


