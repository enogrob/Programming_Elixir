### One Function, Multiple Bodies

Exercise: Functions-2
```elixir
fizzbuzz0 = fn
  (0, 0, _) -> "FizzBuzz"
  (_, 0, _) -> "Buzz"
  (0, _, _) -> "Fizz"
  (_, _, c) -> c
end
```

Exercise: Functions-3
```elixir
fizzbuzz1 = fn(n) ->
  fizzbuzz0.(rem(n,3),rem(n,5),n)
end
```
```elixir
fizzbuzz1.(10)
fizzbuzz1.(11)
fizzbuzz1.(12)
fizzbuzz1.(13)
fizzbuzz1.(14)
fizzbuzz1.(15)
fizzbuzz1.(16)
```

### Parameterized Functions

Exercise: Functions-4
```elixir
prefix = fn(name1) ->
  fn(name2) -> "#{name1} #{name2}" end
end
```
```elixir
mrs = prefix.("Mrs")
mrs.("Smith")

prefix.("Elixir").("Rocks")
```
