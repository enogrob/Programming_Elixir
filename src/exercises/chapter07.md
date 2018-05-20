### Lists and Recursion

__Exercise: ListsAndRecursion-1__
Write a `mapsum` function that takes a list and a function. It applies the function to each element of the list and then sums the result, so
```elixir
iex> MyList.mapsum [1, 2, 3], &(&1 * &1)
14
```

```elixir
defmodule MyList do
  def mapsum(list, func) do
    list
    |> map(func)
    |> sum
  end

  defp sum([]), do: 0
  defp sum([head|tail]), do: head + sum(tail)

  defp map([],_func), do: []
  defp map([head|tail], func), do: [func.(head) | map(tail, func) ]
end
```


__Exercise: ListsAndRecursion-2__
Write a `max(list)` that returns the element with the maximum value in the list. (This is slightly trickier than it sounds.)
```elixir
defmodule MyList do
  def mmax(list), do: mmax(list, 0)

  defp mmax([], value), do: value
  defp mmax([head|tail], value) when head > value, do: mmax(tail, head)
  defp mmax([head|tail], value) when head < value, do: mmax(tail, value)
end
```


__Exercise: ListsAndRecursion-3__
An Elixir single-quoted string is actually a list of individual character codes. Write a `caesar(list, n)` function that adds n to each list element, wrapping if the addition results in a character greater than z.
```elixir
iex> MyList.caesar('ryvkve', 13)
?????? :)
```

```elixir
defmodule MyList do
  def caesar(list), do: list
end
```
