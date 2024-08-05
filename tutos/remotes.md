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

## Added

Key features:
  - **Pull Request**: A request to merge changes from one branch to another, often used for code review.
  - **Fork**: A personal copy of someone else's repository.
  - **Clone**: A local copy of a remote repository.


