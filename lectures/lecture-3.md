lecture-3
================
Ruxandra Iliescu
2026-10-08

## Some commands

``` r
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
unique(mtcars$vs)
```

    ## [1] 0 1

``` r
mtcars %>% group_by(vs, am) %>% summarise(mpg_mean = mean(mpg), mpg_sd = sd(mpg), 
                                      mpg_n = n())
```

    ## `summarise()` has regrouped the output.
    ## ℹ Summaries were computed grouped by vs and am.
    ## ℹ Output is grouped by vs.
    ## ℹ Use `summarise(.groups = "drop_last")` to silence this message.
    ## ℹ Use `summarise(.by = c(vs, am))` for per-operation grouping
    ##   (`?dplyr::dplyr_by`) instead.

    ## # A tibble: 4 × 5
    ## # Groups:   vs [2]
    ##      vs    am mpg_mean mpg_sd mpg_n
    ##   <dbl> <dbl>    <dbl>  <dbl> <int>
    ## 1     0     0     15.0   2.77    12
    ## 2     0     1     19.8   4.01     6
    ## 3     1     0     20.7   2.47     7
    ## 4     1     1     28.4   4.76     7

## ggplot

- take into consideration the type of the variable you display (discrete
  / continuous color palette)
