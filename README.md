# Trie

A [trie](https://en.wikipedia.org/wiki/Trie) is a data structure for efficiently storing and retrieving strings with identical prefixes, like "**mee**t" and "**mee**k".

## Installation

1. Add the dependency to your `shard.yml`:

   ```yaml
   dependencies:
     tries:
       github: cadmiumcr/trie
   ```

2. Run `shards install`

## Usage

```crystal
require "trie"
```
```crystal
trie = Cadmium.trie.new

trie.add("meet")
trie.size
# => 5

trie.add("meek")
trie.size
# => 6

trie.contains?("meet")
# => true

trie.find_prefix("meeting")
# => {"meet", "ing"}
trie.find_prefix("meet")
# => {"meet", ""}
trie.find_prefix("me")
# => {nil, "me"}

trie.keys_with_prefix("me")
# => ["meet", "meek"]

trie.add(["m", "me"])
trie.matches_on_path("meeting")
# => ["m", "me", "meet"]
```

## Contributing

1. Fork it (<https://github.com/cadmiumcr/trie/fork>)
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## Contributors

- [Chris Watson](https://github.com/watzon) - creator and maintainer
