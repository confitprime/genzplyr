# Main character energy - pull a column

Extract a column as a vector (pull equivalent)

## Usage

``` r
main_character(.data, var)
```

## Arguments

- .data:

  A data frame or tibble

- var:

  Column to extract

## Value

A vector

## Examples

``` r
mtcars |> main_character(mpg)
#>  [1] 21.0 21.0 22.8 21.4 18.7 18.1 14.3 24.4 22.8 19.2 17.8 16.4 17.3 15.2 10.4
#> [16] 10.4 14.7 32.4 30.4 33.9 21.5 15.5 15.2 13.3 19.2 27.3 26.0 30.4 15.8 19.7
#> [31] 15.0 21.4
```
