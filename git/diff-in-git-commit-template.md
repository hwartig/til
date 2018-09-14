Show diff in git commit template
================================

I strongly believe in reviewing your own code like you would the code of your colleagues. Today I
learned about a nifty flag that helps exactly with that. When you run `git commit -v` git will
include the diff of staged changes in your commit message template.

You can also run the following command to make this behaviour your default across projects.

```sh
git config --global commit.verbose true
```

The parameter `-v` can also be appended twice. Git would then also show the diff of unstaged
changes.
