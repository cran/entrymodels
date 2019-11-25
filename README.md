
<!-- README.md is generated from README.Rmd. Please edit that file -->

# entrymodels

<!-- badges: start -->

![CRAN version](https://www.r-pkg.org/badges/version/entrymodels)
[![Travis build
status](https://travis-ci.org/gnjardim/entrymodels.svg?branch=master)](https://travis-ci.org/gnjardim/entrymodels)
<!-- badges: end -->

Tools for measuring empirically the effects of entry in concentrated
markets, based in Bresnahan and Reiss (1991)
<https://www.jstor.org/stable/2937655>.

## Installation

You can install the released version of entrymodels from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("entrymodels")
```

And the development version from
[GitHub](https://github.com/gnjardim/entrymodels) with:

``` r
# install.packages("devtools")
devtools::install_github("gnjardim/entrymodels")
```

Which should return something similar to:

``` r
* installing *source* package 'entrymodels' ...
** using staged installation
** R
** inst
** byte-compile and prepare package for lazy loading
** help
*** installing help indices
  converting help for package 'entrymodels'
    finding HTML links ... done
    aux_matrix                              html  
    br1                                     html  
    br2                                     html  
    em_2var                                 html  
    em_basic                                html  
    load_example_data                       html  
** building package indices
** testing if installed package can be loaded from temporary location
*** arch - i386
*** arch - x64
** testing if installed package can be loaded from final location
*** arch - i386
*** arch - x64
** testing if installed package keeps a record of temporary installation path
* DONE (entrymodels)
```

Please note that you should have
[Rtools](https://cran.r-project.org/bin/windows/Rtools/) installed.

## Examples

### Basic Model

This is a basic example which shows you how to estimate a basic entry
model with our sample data.

``` r
library(entrymodels)

tb <- load_example_data()
(em <- em_basic(tb, "Populacao", "n_agencias"))
#> # A tibble: 5 x 2
#>   n_competitors critical_values[,1]
#>           <int>               <dbl>
#> 1             1               5238.
#> 2             2              18961.
#> 3             3              42038.
#> 4             4              75638.
#> 5             5             162958.
```

### Two-Variable Model

This is a basic example which shows you how to estimate a two-variable
entry model with our sample data.

``` r
library(entrymodels)

tb <- load_example_data()
(em <- em_2var(tb, "Populacao", "RendaPerCapita", "n_agencias"))
#> # A tibble: 5 x 2
#>   n_competitors critical_values[,1]
#>           <int>               <dbl>
#> 1             1               5127.
#> 2             2              19265.
#> 3             3              44458.
#> 4             4              79959.
#> 5             5             169059.
```