---
title: "Heart"
author: "Matthew"
date: "1/6/2022"
output: 
  html_document:
    keep_md: true
    toc: true
    toc_float: true
editor_options:
  chunk_output_type: console
---



# Explore

## Sex
![](heart_files/figure-html/unnamed-chunk-1-1.png)<!-- -->

## Max Heart rate
![](heart_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

## Resting ECG
![](heart_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

## Cholesterol 
![](heart_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

```
## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.
```

![](heart_files/figure-html/unnamed-chunk-4-2.png)<!-- -->

```
## 
## 	Welch Two Sample t-test
## 
## data:  heart$cholesterol by heart$heartdisease
## t = 7.6269, df = 844.36, p-value = 6.481e-14
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##  38.00953 64.35249
## sample estimates:
## mean in group 0 mean in group 1 
##        227.1220        175.9409
```

## Checking Numeric columns

```
## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.
```

![](heart_files/figure-html/unnamed-chunk-5-1.png)<!-- -->

## Oldpeak

```
## # A tibble: 53 x 2
##    oldpeak     n
##      <dbl> <int>
##  1    -2.6     1
##  2    -2       1
##  3    -1.5     1
##  4    -1.1     1
##  5    -1       2
##  6    -0.9     1
##  7    -0.8     1
##  8    -0.7     1
##  9    -0.5     2
## 10    -0.1     2
## # ... with 43 more rows
```

![](heart_files/figure-html/unnamed-chunk-6-1.png)<!-- -->

## Exercise
![](heart_files/figure-html/unnamed-chunk-7-1.png)<!-- -->


# Model

```
## Registered S3 method overwritten by 'tune':
##   method                   from   
##   required_pkgs.model_spec parsnip
```

```
## -- Attaching packages -------------------------------------- tidymodels 0.1.4 --
```

```
## v broom        0.7.10     v rsample      0.1.1 
## v dials        0.0.10     v tune         0.1.6 
## v infer        1.0.0      v workflows    0.2.4 
## v modeldata    0.1.1      v workflowsets 0.1.0 
## v parsnip      0.1.7      v yardstick    0.0.9 
## v recipes      0.1.17
```

```
## -- Conflicts ----------------------------------------- tidymodels_conflicts() --
## x scales::discard() masks purrr::discard()
## x dplyr::filter()   masks stats::filter()
## x recipes::fixed()  masks stringr::fixed()
## x dplyr::lag()      masks stats::lag()
## x yardstick::spec() masks readr::spec()
## x recipes::step()   masks stats::step()
## * Use suppressPackageStartupMessages() to eliminate package startup messages
```

```
## # A tibble: 2 x 4
##   .metric  .estimator .estimate .config             
##   <chr>    <chr>          <dbl> <chr>               
## 1 accuracy binary         0.845 Preprocessor1_Model1
## 2 roc_auc  binary         0.912 Preprocessor1_Model1
```

![](heart_files/figure-html/unnamed-chunk-8-1.png)<!-- -->







