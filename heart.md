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
## * Dig deeper into tidy modeling with R at https://www.tmwr.org
```

```
## # A tibble: 2 x 4
##   .metric  .estimator .estimate .config             
##   <chr>    <chr>          <dbl> <chr>               
## 1 accuracy binary         0.882 Preprocessor1_Model1
## 2 roc_auc  binary         0.925 Preprocessor1_Model1
```

![](heart_files/figure-html/unnamed-chunk-8-1.png)<!-- -->

```
## # A tibble: 16 x 5
##    term                           estimate std.error statistic  p.value
##    <chr>                             <dbl>     <dbl>     <dbl>    <dbl>
##  1 st_slope_Up                      1.31       0.690     1.90  0.0569  
##  2 sex_M                           -1.21       0.368    -3.30  0.000982
##  3 age                             -1.06       0.357    -2.97  0.00300 
##  4 cholesterol                     -1.01       0.382    -2.64  0.00823 
##  5 exerciseangina_Y                -0.992      0.336    -2.95  0.00314 
##  6 restingecg_ST                    0.905      0.423     2.14  0.0324  
##  7 restingecg_Normal                0.843      0.353     2.39  0.0170  
##  8 st_slope_Flat                   -0.611      0.628    -0.973 0.331   
##  9 restingbp                       -0.501      0.349    -1.44  0.151   
## 10 chestpaintype_Atypical.Angina    0.481      0.358     1.35  0.179   
## 11 chestpaintype_Non.Anginal.Pain   0.346      0.313     1.10  0.270   
## 12 maxhr                           -0.248      0.364    -0.681 0.496   
## 13 chestpaintype_Typical.Angina    -0.240      0.292    -0.821 0.412   
## 14 (Intercept)                      0.214      0.310     0.689 0.491   
## 15 oldpeak                         -0.148      0.371    -0.398 0.691   
## 16 fastingbs_X1                    -0.0782     0.327    -0.239 0.811
```

## Model of Largestest Estimates


## Plot both
![](heart_files/figure-html/unnamed-chunk-10-1.png)<!-- -->

### Metrics

```
## # A tibble: 2 x 4
##   .metric  .estimator .estimate .config             
##   <chr>    <chr>          <dbl> <chr>               
## 1 accuracy binary         0.882 Preprocessor1_Model1
## 2 roc_auc  binary         0.925 Preprocessor1_Model1
```

```
## # A tibble: 2 x 4
##   .metric  .estimator .estimate .config             
##   <chr>    <chr>          <dbl> <chr>               
## 1 accuracy binary         0.850 Preprocessor1_Model1
## 2 roc_auc  binary         0.911 Preprocessor1_Model1
```



