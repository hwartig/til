Replace insecure git:// urls with ssh or https://
=================================================

Git has a config setting [url.<base>.insteadOf](https://git-scm.com/docs/git-config#git-config-urlltbasegtinsteadOf)
that can be used to replace insecure git:// urls with https or ssh.

```sh
# for https
git config --global url."https://github.com".insteadOf git://github.com

# for ssh
git config --global url."git@github.com:".insteadOf git://github.com
```
