# Squad up your data

Group by categories to analyze squads (group_by equivalent)

## Usage

``` r
squad_up(.data, ...)
```

## Arguments

- .data:

  A data frame or tibble

- ...:

  Variables to group by

## Value

A grouped data frame

## Examples

``` r
mtcars |> squad_up(cyl) |> no_cap(avg_mpg = mean(mpg))
#> # A tibble: 3 × 2
#>     cyl avg_mpg
#>   <dbl>   <dbl>
#> 1     4    26.7
#> 2     6    19.7
#> 3     8    15.1
```
