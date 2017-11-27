Use Vim non-interactively
=========================

There are various ways to use vim non-interactively. The first is using the `ex` alias or the
`-e` command line parameter.

```sh
echo example | ex +%s/^e/E/ -sc '%p|q!' /dev/stdin > output.txt
echo example | vim -e +%s/^e/E/ -sc '%p|q!' /dev/stdin > output.txt
```

Another way is using `vipe` a tool from the [moreutils][] package. It will read from `stdin` open
your editor with that content so that you can manually edit it and after you closed your editor it
will print the contents to `stdout`.

```sh
echo Example | vipe > output.txt
```

For even more examples visit this [amazing answer on stackoverflow][soa]

[moreutils]: https://joeyh.name/code/moreutils/
[soa]: https://vi.stackexchange.com/a/789
