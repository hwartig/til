Merge Hashes of Arrays
======================

Today I ended up in a situation where I had multiple hashes of arrays that I wanted to merge in a
way that `{a: [1], b: [2]}` merged with `{b: [3], c: [4]}` should result in
`{a: [1], b: [2, 3], c: [4]}`. This is possible by passing a block to the `Hash#merge` method.

```ruby
  one = {a: [1], b: [2]}
  two = {b: [3], c: [4]}

  one.merge(two) do |key, old, new|
    old | new  # simpler than (old + new).uniq
  end
```

The ability to pass a block allows us to do even fancier things like to be more generic and handle
non array values.

```ruby
  one.merge(two) do |key, old, new|
    (new.is_a?(Array) ? (old + new) : (old << new)).uniq
  end
```
