Partition Enumerator into good and bad elements
===============================================

Today I relearned about `[Enumerable#partition][partition]`. It allows you to divide the elements of
an `Enumerable` into good and bad elements using a block. My problem today was that I wanted to
remove a bunch of elements from an `Array` and also get the removed elements to process them
further. I ended up writing code similar to the following

```ruby
config = ['option1', 2, 'option3']
valid_config, invalid_config = config.partition { |v| v.is_a? String }
puts "Cannot Process: #{other.inspect}"
```

[partition]: https://ruby-doc.org/core-2.4.2/Enumerable.html#method-i-partition
