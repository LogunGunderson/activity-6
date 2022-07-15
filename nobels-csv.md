Nobel winners
================
Logun Gunderson

``` r
library(tidyverse)
```

Let’s first load the data:

``` r
nobel <- read_csv("data-raw/nobel.csv")
```

Then let’s split the data into two:

``` r
# stem laureates
nobel_stem <- nobel %>%
  filter(category %in% c("Physics", "Medicine", "Chemistry", "Economics"))

# non-stem laureates
nobel_stem <- nobel %>%
  filter(!(category %in% c("Physics", "Medicine", "Chemistry", "Economics")))
```

And finally write out the data:

``` r
write_csv(nobel_stem, file = "data/nobel-stem.csv")

write_csv(nobel_nonstem, file = "data/nobel-nonstem.csv")
```
