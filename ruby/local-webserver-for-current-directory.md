Start a local web server for serving static files in current directory
=====================================================================

You might have come across the python one-liner that will start a local web server that will serve
all static files.

```sh
python -m SimpleHTTPServer 8080
```

Today I learned there is a ruby equivalent for that.

```sh
ruby -run -e httpd . -p 8080
```

After looking at it more closely, I wondered how it worked, as I had never before heard about the
option `-run` for ruby. So I checked the man page and indeed there is no such option. It turns out
`ruby -run` is just short for `ruby -r un` where `-r` is the good old require a library option.
Ruby apparently ships with a [`un.rb` file](https://github.com/ruby/ruby/blob/trunk/lib/un.rb) out
of the box.

If you interested in what else it can do, you should check its integrated help.

```sh
ruby -run -e help        # docs of all commands
ruby -run -e help httpd  # docs of a single command
```
