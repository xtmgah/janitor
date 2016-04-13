<!-- README.md is generated from README.Rmd. Please edit that file -->
janitor
=======

janitor helps fix common dirty data issues. Functions are human-readable - think `clean_names()` instead of re-using code like`gsub("[.]+", "_", .) ...`.

Use with the `%>%` pipe from [magrittr](https://github.com/smbache/magrittr) immediately after reading in data for most elegant results.

``` r
# load demo packages using the pacman package
if (!require("pacman")) install.packages("pacman"); library(pacman)
p_load(janitor, dplyr, readr)

# read sample dirty data file
starting_df <- read_csv("http://www.github.com/sfirke/janitor/sample/dirty_data.csv")

# the initial names are malformed.  Duplicate names will cause dplyr calls to fail.
names(starting_df)

# clean the data with janitor:
clean_df <- starting_df %>%
  clean_names %>%
  remove_empty_rows %>%
  remove_empty_cols

# names are now clean:
names(clean_df)
```

Overview
--------

The janitor functions are:

-   Clean data.frame names with `clean_names()`.

-   Remove entirely empty rows with `remove_empty_rows()` and empty columns with `remove_empty_cols()`.

Installation
------------

janitor isn't on CRAN yet. Install the development version from GitHub:

``` r
# install.packages("devtools")
install_github("sfirke/janitor")
```
