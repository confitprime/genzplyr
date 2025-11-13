# genzplyr 💅

> dplyr but make it bussin fr fr no cap

## What is this?

`genzplyr` is an alternative syntax for `dplyr` that replaces boring old
function names with GenZ slang. Your data wrangling is about to hit
different.

## Installation

``` r
pak::pak("hadley/genzplyr")
```

## The translation guide

| dplyr verb                                        | genzplyr verb                                                                       | Meaning                                                                            |
|---------------------------------------------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| [`filter()`](https://rdrr.io/r/stats/filter.html) | [`yeet()`](https://hadley.github.io/genzplyr/reference/yeet.md)                     | Remove rows that don’t pass the vibe check                                         |
| `select()`                                        | [`vibe_check()`](https://hadley.github.io/genzplyr/reference/vibe_check.md)         | Keep only columns that matter                                                      |
| `mutate()`                                        | [`glow_up()`](https://hadley.github.io/genzplyr/reference/glow_up.md)               | Transform your data into its best self                                             |
| `summarise()`                                     | [`no_cap()`](https://hadley.github.io/genzplyr/reference/no_cap.md)                 | Get real summary stats, no lies                                                    |
| `arrange()`                                       | [`slay()`](https://hadley.github.io/genzplyr/reference/slay.md)                     | Sort by slay factor                                                                |
| `group_by()`                                      | [`squad_up()`](https://hadley.github.io/genzplyr/reference/squad_up.md)             | Group data into squads                                                             |
| `ungroup()`                                       | [`disband()`](https://hadley.github.io/genzplyr/reference/disband.md)               | Break up the squad                                                                 |
| `rename()`                                        | [`lowkey()`](https://hadley.github.io/genzplyr/reference/lowkey.md)                 | Change names on the down-low                                                       |
| `distinct()`                                      | [`periodt()`](https://hadley.github.io/genzplyr/reference/periodt.md)               | Remove duplicates, and that’s on periodt                                           |
| `pull()`                                          | [`main_character()`](https://hadley.github.io/genzplyr/reference/main_character.md) | Extract a column (give it main character energy)                                   |
| `slice_head()`                                    | [`send_it()`](https://hadley.github.io/genzplyr/reference/send_it.md)               | Take the top rows and send it                                                      |
| `count()`                                         | [`its_giving()`](https://hadley.github.io/genzplyr/reference/its_giving.md)         | Count occurrences (it’s giving statistics)                                         |
| `left_join()`                                     | `link_up()`                                                                         | Merge datasets but keep all your day-ones (left table stays main squad)            |
| `right_join()`                                    | `clout_chase()`                                                                     | Merge, but the other chums call the shots on who stays (right table is main squad) |
| `inner_join()`                                    | `mutuals_only()`                                                                    | Merge, but only keep rows where both tables are mutually following each other      |
| `full_join()`                                     | `everyone_in_the_groupchat()`                                                       | Bring everyone, even if messy (keeps all rows)                                     |
| `anti_join()`                                     | `ghost()`                                                                           | Forget about those who don’t vibe with you (remove non-matching rows)              |
| `semi_join()`                                     | `only_the_reals()`                                                                  | Just keep the rows that vibe with both tables (matching rows only)                 |

## Examples that slap

### Basic workflow

**Old way (cringe):**

``` r
mtcars |>
  filter(mpg > 20) |>
  select(mpg, cyl, hp) |>
  mutate(kpg = mpg * 1.6) |>
  arrange(desc(mpg))
```

**New way (bussin):**

``` r
mtcars |>
  yeet(mpg > 20) |>
  vibe_check(mpg, cyl, hp) |>
  glow_up(kpg = mpg * 1.6) |>
  slay(desc(mpg))
```

### Grouped summaries

**Old way:**

``` r
mtcars |>
  group_by(cyl) |>
  summarise(
    avg_mpg = mean(mpg),
    max_hp = max(hp)
  ) |>
  arrange(desc(avg_mpg))
```

**New way (hits different):**

``` r
mtcars |>
  squad_up(cyl) |>
  no_cap(
    avg_mpg = mean(mpg),
    max_hp = max(hp)
  ) |>
  slay(desc(avg_mpg))
```

### Complex analysis

``` r
# Find high-performance 4-cylinder cars
mtcars |>
  yeet(cyl == 4, hp > 90) |>           # Only 4-cyl with decent power
  vibe_check(mpg, hp, wt, qsec) |>     # Relevant columns only
  glow_up(                              # Add some calculations
    power_to_weight = hp / wt,
    efficiency_score = mpg * hp / wt
  ) |>
  slay(desc(efficiency_score)) |>      # Sort by best score
  send_it(5)                            # Top 5
```

### Renaming columns lowkey

``` r
mtcars |>
  lowkey(
    miles_per_gallon = mpg,
    horse_power = hp,
    weight = wt
  ) |>
  vibe_check(miles_per_gallon, horse_power, weight)
```

### Getting unique values periodt

``` r
# See what cylinder options exist
mtcars |>
  periodt(cyl) |>
  slay(cyl)

# Count cars by cylinder and gear combo
mtcars |>
  its_giving(cyl, gear) |>
  slay(desc(n))
```

### Extract main character data

``` r
# Get all MPG values as a vector
mpg_values <- mtcars |>
  yeet(cyl == 4) |>
  main_character(mpg)

mean(mpg_values)  # Average MPG for 4-cylinder cars
```

### The full send

``` r
# Complete analysis that's absolutely bussin
mtcars |>
  yeet(hp > 100) |>                    # Yeet the weak cars
  vibe_check(mpg, cyl, hp, wt) |>      # Vibe check our columns
  glow_up(                              # Glow up the data
    hp_per_ton = hp / (wt / 2),
    efficiency = mpg / (hp / 100)
  ) |>
  squad_up(cyl) |>                     # Squad up by cylinders
  no_cap(                               # Get the real stats
    avg_hp = mean(hp),
    avg_mpg = mean(mpg),
    avg_efficiency = mean(efficiency),
    squad_size = n()
  ) |>
  disband() |>                         # Disband the squads
  slay(desc(avg_efficiency)) |>        # Sort by slay factor
  send_it(10)                          # Send it!
```

## Run the demo

``` r
demo_genzplyr()
```

## Why tho?

Because data science should be fun and your code should reflect your
personality. Also, imagine the look on your professor’s face when you
submit an analysis using
[`yeet()`](https://hadley.github.io/genzplyr/reference/yeet.md) and
[`squad_up()`](https://hadley.github.io/genzplyr/reference/squad_up.md).

## Is this production ready?

Bestie, this is for vibes only. Maybe don’t use this in your Fortune 500
company’s quarterly earnings report.

## Contributing

PRs welcome! Got better GenZ slang? Submit a pull request and let’s make
this even more bussin.

## Slang glossary

- **Bussin**: Really good, excellent
- **Fr fr**: For real for real (emphasizing truth)
- **No cap**: No lie, being truthful
- **Yeet**: To throw away or discard
- **Vibe check**: To assess if something is acceptable
- **Glow up**: A transformation to a better version
- **Slay**: To do something exceptionally well
- **Squad**: A group of people/things
- **Lowkey**: Subtle, on the down-low
- **Periodt**: Emphasis at the end of a statement (like “period” but
  more)
- **Main character**: The protagonist, the one in focus
- **Send it**: Go for it, commit fully
- **It’s giving…**: It’s giving off vibes of…
- **Hits different**: Has a unique, special quality

## License

MIT but like, do whatever you want with this, it’s just for fun fr fr

------------------------------------------------------------------------

*This package is satire but the code actually works no cap*
