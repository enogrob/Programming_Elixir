### Function Calls and Pattern Matching

Exercise: ModulesAndFunctions-4
```elixir
defmodule ModuleAndFunctions4 do
  def sum(0, total), do: total
  def sum(n), do: sum(n, 0)
  def sum(n, total) do
    sum(n - 1, total + n)
  end
end
```

Exercise: ModulesAndFunctions-5
```elixir
defmodule ModuleAndFunctions5 do
  def gcd(x, 0), do: x
  def gcd(x, y), do: gcd(x, rem(x,y))
end
```

Exercise: ModulesAndFunctions-7
Find the library functions to do the following, and then use each in IEx. (If the word Elixir or Erlang appears at the end of the challenge, then you’ll find the answer in that set of libraries.)
– Convert a float to a string with two decimal digits. (Erlang)
```elixir
Float.to_string(1200.123, decimals: 2)
```

– Get the value of an operating-system environment variable. (Elixir)
```elixir
System.get_env("USER")
```

– Return the extension component of a file name (so return .exs if given "dave/test.exs"). (Elixir)
```elixir
Path.extname("dave/test.exs")
```

– Return the process’s current working directory. (Elixir)
```elixir
pwd
```

– Convert a string containing JSON into Elixir data structures. (Just find; don’t install.)
```elixir
Poison.decode!(~s({"name": "Devin Torres", "age": 27}))
#=> %{"age" => 27, "name" => "Devin Torres"}
```

– Execute a command in your operating system’s shell.
```elixir
System.cmd("tree",["-l", "1"])
|> Tuple.to_list
|> List.first
|> IO.puts
```
