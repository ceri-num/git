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

## Authentification

Accessing a github remote repository, requires either an https or ssh remote URL (cf. [doc](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories)).
In both cases, you need to deal with authentication: [Personal Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) using https or [SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).

The SSH method in a nutshell without a passphrase:

```
$ ssh-keygen -t ed25519 -f ~/.ssh/id_github -C "bob@leponge.fr"

$ ls ~/.ssh/id_github*
id_github           # <- private key, never ever share it
id_github.pub       # <- public key
```

Then, you should set the public key in your Github Settings under the SSH and GPG keys section.

You can then use SSH URLs to access remote git repositories on github such as:

```
$ git remote -v
origin	git@github.com:xxx/yyy.git (fetch)
origin	git@github.com:xxx/yyy.git (push)
```

## Operations involving remote repositories

### Clone and Fork

Create local copy of a remote repository.

```
git clone https://github.com/mivinci/pacman.git
```

You can commit your own modifications to this game locally.
However, you cannot push your commits directly to this repository nor propose them.

To contribute to a repository on which you do not have rights, you should:
1. Through github, __fork__ this repository on your github account
2. Clone your own repository locally
3. Push your commits to your repository
4. Through github, you can then issue a pull request from one of your branch to the originally forked repository

### **Push**

{% hint style="info" %}
Documentation: <https://github.com/git-guides/git-push>
{% endhint%}

You must have rights on the remote repository to oush your local commits into it.

Send local commits on the current branch to a remote repository:

```
$ git status
git status
On branch bugFix
nothing to commit, working tree clean

$ git branch -a
* bugFix
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
```

We worked on the bugFix branch and committed everything locally (our workspace is clean).
By default, git push send commits to the remote named origin.
But, we cannot push directly since origin does not contain any bugFix branch.

```
$ git push
fatal: The current branch bugFix has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin bugFix

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.
```

If the current branch does not exist on origin, you should specify it:

```
$ git push --set-upstream origin bugFix
```

If the branch already exists on the remote, git push is enough.

### **Pull**

{% hint style="info" %}
Documentation: <https://github.com/git-guides/git-pull>
{% endhint%}

Get remote commits into a local repository and checkout the corresponding workspace.

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

The first time you do a git pull, git may ask some default policies: rebase, ff, ...
In my case, I usually select those policies:

- `git config --global pull.ff true`: allowing fast-forward
- `git config --global pull.rebase true`: allowing rebasing my local commits when pulling remote commits

## Take away

Typical work session innvolving one branch only:

1. `git pull`, resync your local repository and workspace with origin (get commits from others)
2. work
3. `git commit` (go back to 2 if more work is needed)
4. `git pull` resync and resolve conflicts if needed
5. `git push` send all your new commits to origin
6. you can stop working here since your workspace is clean and all your commits have been pushed remotely
