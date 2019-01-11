Use bundler without Gemfile
===========================

Today I learned that you can [use bundler in a single-file ruby script](https://bundler.io/v2.0/guides/bundler_in_a_single_file_ruby_script.html).
This is possible by requiring `bundler/inline` and defining your gem dependencies in a block thats
passed to the `gemfile` method using the familiar Gemfile syntax.

```ruby
require 'bundler/inline'

gemfile do
  source 'https://rubygems.org'

  gem 'pry', require: false
  gem 'rest-client', '~> 2'
end
```
