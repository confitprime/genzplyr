# No cap summary stats

Get the real stats, no cap (summarise equivalent)

## Usage

``` r
no_cap(.data, ...)
```

## Arguments

- .data:

  A data frame or tibble

- ...:

  Name-value pairs of summary expressions

## Value

A data frame with summary statistics

## Examples

``` r
mtcars |> no_cap(avg_mpg = mean(mpg), max_hp = max(hp))
#>    avg_mpg max_hp
#> 1 20.09062    335
```
