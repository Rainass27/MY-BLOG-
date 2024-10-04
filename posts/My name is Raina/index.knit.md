---
title: "My name is RG"
author: "Raina"
---



## Introduction

This is a ridiculous piece I am writing in Arvind's class.He is making things difficult for me.

## My first piece of R code



::: {.cell}

```{.r .cell-code}
 library(tidyverse)
```

::: {.cell-output .cell-output-stderr}

```
── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
✔ dplyr     1.1.4     ✔ readr     2.1.5
✔ forcats   1.0.0     ✔ stringr   1.5.1
✔ ggplot2   3.5.1     ✔ tibble    3.2.1
✔ lubridate 1.9.3     ✔ tidyr     1.3.1
✔ purrr     1.0.2     
── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()
ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors
```


:::

```{.r .cell-code}
 library(ggformula)
```

::: {.cell-output .cell-output-stderr}

```
Loading required package: scales

Attaching package: 'scales'

The following object is masked from 'package:purrr':

    discard

The following object is masked from 'package:readr':

    col_factor

Loading required package: ggridges

New to ggformula?  Try the tutorials: 
	learnr::run_tutorial("introduction", package = "ggformula")
	learnr::run_tutorial("refining", package = "ggformula")
```


:::

```{.r .cell-code}
 library(babynames)
```
:::

::: {.cell}

```{.r .cell-code}
babynames
```

::: {.cell-output .cell-output-stdout}

```
# A tibble: 1,924,665 × 5
    year sex   name          n   prop
   <dbl> <chr> <chr>     <int>  <dbl>
 1  1880 F     Mary       7065 0.0724
 2  1880 F     Anna       2604 0.0267
 3  1880 F     Emma       2003 0.0205
 4  1880 F     Elizabeth  1939 0.0199
 5  1880 F     Minnie     1746 0.0179
 6  1880 F     Margaret   1578 0.0162
 7  1880 F     Ida        1472 0.0151
 8  1880 F     Alice      1414 0.0145
 9  1880 F     Bertha     1320 0.0135
10  1880 F     Sarah      1288 0.0132
# ℹ 1,924,655 more rows
```


:::
:::

::: {.cell}

```{.r .cell-code}
babynames%>% filter(name== "Raina")
```

::: {.cell-output .cell-output-stdout}

```
# A tibble: 70 × 5
    year sex   name      n       prop
   <dbl> <chr> <chr> <int>      <dbl>
 1  1946 F     Raina     5 0.0000031 
 2  1948 F     Raina     8 0.00000459
 3  1950 F     Raina    13 0.00000739
 4  1951 F     Raina    11 0.00000595
 5  1952 F     Raina    17 0.00000894
 6  1953 F     Raina     7 0.00000363
 7  1954 F     Raina    10 0.00000502
 8  1955 F     Raina    12 0.00000599
 9  1956 F     Raina    12 0.00000583
10  1957 F     Raina    10 0.00000477
# ℹ 60 more rows
```


:::
:::

::: {.cell}

```{.r .cell-code}
babynames %>% filter(name== "Aditi") %>% 
  gf_line(n ~ year)
```

::: {.cell-output-display}
![](index_files/figure-html/unnamed-chunk-4-1.png){width=672}
:::
:::



```         
```



::: {.cell}

```{.r .cell-code}
babynames %>% filter(name == "Raina" | name == "Rayna")
```

::: {.cell-output .cell-output-stdout}

```
# A tibble: 153 × 5
    year sex   name      n       prop
   <dbl> <chr> <chr> <int>      <dbl>
 1  1932 F     Rayna     5 0.00000452
 2  1936 F     Rayna     6 0.00000557
 3  1937 F     Rayna     8 0.00000726
 4  1938 F     Rayna    13 0.0000114 
 5  1939 F     Rayna     9 0.00000794
 6  1940 F     Rayna     9 0.00000762
 7  1941 F     Rayna    20 0.0000160 
 8  1942 F     Rayna    15 0.0000108 
 9  1943 F     Rayna    15 0.0000104 
10  1944 F     Rayna    17 0.0000124 
# ℹ 143 more rows
```


:::
:::

::: {.cell}

```{.r .cell-code}
babynames %>% filter(name == "Raina" | name == "Rayna") %>% 
  gf_line(n ~ year, color = ~name)
```

::: {.cell-output-display}
![](index_files/figure-html/unnamed-chunk-6-1.png){width=672}
:::
:::

