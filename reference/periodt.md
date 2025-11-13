# Periodt - keep distinct rows

Remove duplicate rows, and that's on periodt (distinct equivalent)

## Usage

``` r
periodt(.data, ...)
```

## Arguments

- .data:

  A data frame or tibble

- ...:

  Optional columns to determine uniqueness

## Value

A data frame with unique rows

## Examples

``` r
mtcars |> periodt(cyl)
#>                   cyl
#> Mazda RX4           6
#> Datsun 710          4
#> Hornet Sportabout   8
```
