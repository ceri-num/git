## Sensitive infos in public git repositories

git stores the history of your workspace and you usually push those commits publicly on github for example.

If you stored, committed and publicly pushed a sensitive info (SSH certificate, ...), you should change it. Removing the commit from github is __not__ a solution since the repository might already have been cloned or forked.

{% hint style="danger" %}
- Never store any password, token or credential in a git repository
- Change it immediatly if it happens
{% endhint %}

## .git directory of private repositories

Using a private git repository is not enough to ensure security.
You should not make the `.git` folder publicly accessible for example in the `DOCUMENT_ROOT` of a Web server.

