Edit command line in editor
===========================

Sometimes I find myself chaining together various command line tools only to suddenly realize that
I would prefer to edit this now over hundred characters long line in my lovely Vim editor.

Fish already has a pretty good [command line editor][cle] Emacs and Vim keybinding support but
sometimes I really prefer a proper editor.

Today I learned that pressing `<ALT-e>` in [fish] I can accomplish exactly that. If this doesn't
open Vim for you as well then you might need to set your `$EDITOR` environment variable to your vim
binary.

Don't worry if you're using bash. You get the same behaviour in bash with `<CTRL-x><CTRL-e>`.

[fish]: https://fishshell.com/
[cle]: https://fishshell.com/docs/current/index.html#editor
