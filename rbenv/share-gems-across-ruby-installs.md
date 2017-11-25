Share gems across multiple rbenv Ruby installs
==============================================

rbenv installs gems by default per ruby version. This wastes a lot of disk space if you need to
work with multiple ruby versions at the same time. [Tpope] wrote [rbenv-communal-gems] for us
that solves exactly this need.

You can install the latest version with the following lines of code.

```sh
mkdir -p ~/.rbenv/plugins
git clone git://github.com/tpope/rbenv-communal-gems.git \
  ~/.rbenv/plugins/rbenv-communal-gems
rbenv communize --all
```

[rbenv-communal-gems]: https://github.com/tpope/rbenv-communal-gems
[tpope]: https://tpo.pe/
