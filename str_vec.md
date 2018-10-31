vector\_str
================
Shan Jiang
10/30/2018

## R Data Type

R has five basic or “atomic” classes of objects.

  - character
  - numeric
  - integer
  - complex
  - logical(True/False)

The basic object is a **vector**. Everything in a vector has to be the
**same class**. But the only exception is a *list*, which is represented
as a vector but can contain objects of different classes(indeed, that’s
why we use them).

#### Numbers

  - The Numbers are treated as double precision real value.

<!-- end list -->

``` r
cha_1 = c("1")
class(cha_1)
```

    ## [1] "character"

``` r
num_1 = c(1)
class(num_1)
```

    ## [1] "numeric"

  - If you expilicitly wants to have an interger, then add an *L* as a
    suffix.

<!-- end list -->

``` r
# int_1 as integer, capitalized L gets you the integer 
int_1 = c(1L)
class(int_1)
```

    ## [1] "integer"

``` r
# Infinity in the special number, stands for infinity
inf_1 = c(1/Inf)
inf_1 
```

    ## [1] 0

The objects can have alot of attributes and can be shown as:

``` r
# length, which you can determine with length().
x <- list("a", "b", 1:10)
length(x)
```

    ## [1] 3

``` r
# Scalars may have 
x <- c("a", "b", 1:10)
length(x)
```

    ## [1] 12

``` r
# Its type, which you can determine with typeof().
typeof(letters)
```

    ## [1] "character"

``` r
typeof(1:10)
```

    ## [1] "integer"

  - *NaN* stands for “not a number”.

#### C Function

concatenate =
    c

``` r
library(tidyverse)
```

    ## ── Attaching packages ────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ── Conflicts ───────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
string_vec = c("my", "name", "is", "jeff")

str_detect(string_vec, "jeff")
```

    ## [1] FALSE FALSE FALSE  TRUE

``` r
## [1] FALSE FALSE FALSE  TRUE

str_replace(string_vec, "jeff", "Jeff")
```

    ## [1] "my"   "name" "is"   "Jeff"

  - Explicit Coercion in the R.

<!-- end list -->

``` r
string_vec = as.logical(string_vec)
```

## list

list can be of anything and can be consisted of any type of data.

``` r
model_ls = list("a", "90", "T")
```

## Factor

``` r
x <- factor(c("yes", "no", "yes", "no", "yes"))
table(x)
```

    ## x
    ##  no yes 
    ##   2   3

``` r
unclass(x)
```

    ## [1] 2 1 2 1 2
    ## attr(,"levels")
    ## [1] "no"  "yes"

``` r
## tell r to use the yes as the baseline level
x <- factor(c("yes", "no", "yes", "no", "yes"), levels = c("yes", "no"))
x
```

    ## [1] yes no  yes no  yes
    ## Levels: yes no
