## Sensitive infos in public git repositories

git stores the history of your workspace and you usually push those commits publicly on github for example.

If you stored, committed and publicly pushed a sensitive info (SSH certificate, ...), you should change it. Removing the commit from github is __not__ a solution since the repository might already have been cloned or forked.

{% hint style="danger" %}
- Never store any password, token or credential in a git repository
- Change it immediatly if it happens
{% endhint %}

## Sensite infos in private git repositories

Using a private git repository is not enough to ensure security.
You should ensure that the `.git` folder is not publicly accessible.
For example, cloning a git repository directly in the `DOCUMENT_ROOT` of a Web server to deploy a web app may make the `.git` folder public accessible.

## Using a GUI

Once you understood the basics of git using the git CLI, you can use one of the many [git Client GUI](https://git-scm.com/downloads/guis). You can even use the built in [VSCode code git support](https://code.visualstudio.com/docs/sourcecontrol/overview).

