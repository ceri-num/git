## What is Git?

**Git** is a *decentralized* version control system created in 2005 by Linus Torvalds.
Git tracks changes to files over time and do not prioritize one repository over others.
It allows you to revert to previous versions, collaborate with others, and keep a history of your work.

### Install git

Install git on you OS:
- Doc: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
- Add git to your `PATH`

```
$ git --version
git version 2.39.2
```

### Create your first local repository

cf. https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository

```
$ mkdir MyFirstRepository
$ cd MyFirstRepository
$ git init
Initialized empty Git repository in /tmp/MyFirstRepository/.git/
$ ls -a
.git
```

`git init` initialize a directory as a local git repository so that we can then track versions of files inside this directory.

### Local repository

A local repository contains 3 areas:
- a **workspace** or **working copy** that contains files on which you are working. Some of them may be tracked by git. Initially empty.
- a **stage area** or **index**  that stores information about what will go into your next commit (we will come to that later on). Initially empty.
- a **Local repository** (`.git` folder automatically created and managed by git) that contains the history i.e. all the versions of all tracked files.

Note: from the user perspective, a git repository is a regular folder that contains at least a .git subfolder.


[Git areas](imgs/git-areas.svg)


### Commit

Add a `README.md` file into it this **MyFirstRepository** folder that contains:
```
# My super

First try
```

We added a file named README.md and modified it in the workspace.
We now want to **commit** this change as a new version in the history.


- **Commit**: A snapshot of your project at a point in time.

### History

TODO

### Branches

- **Branch**: A separate line of development. The default branch is usually called `main` or `master`.
- **Merge**: Combining changes from different branches.


https://github.com/uriid1/ascii-c-game.git
