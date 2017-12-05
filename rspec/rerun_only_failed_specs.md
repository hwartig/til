Rerun only failed specs
=======================

In a big test suite it can be tedious to rerun only the failing tests manually on the command line.
Usually I go through the failing tests one by one to fix them. So I used to copy the filenames of
failing specs into a long rspec command line and rerun that command till all where fixed before
running the whole test suite again.

Today I learned that rspec already supports an [`--only-failures`][rspecdoc] option that reruns only
the failing specs. The neat thing is that it will run fewer specs each time you fixed one. It also
supports a command line option `--next-failure` that will allow you to focus on only one failing
spec at a time.

For it to work you have to enable a persistence file in your rspec config (within your spec helper)
first.

```ruby
RSpec.configure do |c|
  c.example_status_persistence_file_path = "failed_rspec_examples.txt"
end
```

I would also recommend adding this file to your various ignore files `.gitignore`, `.agignore` etc.

[rspecdoc]: https://relishapp.com/rspec/rspec-core/docs/command-line/only-failures
