# Reports Generator - Challenge 2!

## Proposal
The proposal for this project is to complete a challenge and pursuant to the knowledge of previous studies (PLUS Parallelism).<br>

### ReportsGeneratorChallenge2.build/1
When running, it returns 1 map with 3 key-values: "all_hours", "hours_per_month" and "hours_per_year", which contains the total hours worked, the total hours per month and the total hours per year of each employee, respectively.

```elixir
iex> ReportsGeneratorChallenge2.build("gen_report.csv")
...> %{"all_hours" => %{...}, "hours_per_month" => %{...}, "hours_per_year" => %{...}}
```

### ReportsGeneratorChallenge2.build_from_many/1
Same of `build/1`, but waits for a list and builds them in parallel.

#### Success
```elixir
iex> ReportsGeneratorChallenge2.build_from_many(["part_1.csv", "part_2.csv", "part_3.csv"])
...> %{:ok, %{"all_hours" => %{...}, "hours_per_month" => %{...}, "hours_per_year" => %{...}}}
```

#### Error
```elixir
iex> ReportsGeneratorChallenge2.build_from_many("banana")
...> {:error, "Please provide a list of strings"}
```

### ReportsGeneratorChallenge2.Parser.parse_file/1

```elixir
iex> "part_min.csv" |> ReportsGeneratorChallenge2.Parser.parse_file() |> Enum.map(& &1)
...> [["Daniele", 7, 29, 4, 2018], ...]
```

## Tests

This project has tests, just enter the command below at your terminal, in the same folder in this project.
```sh
.../reports_generator_challenge2> mix test
```