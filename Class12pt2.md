# Class 12 Part 2
Maleeha Shaikh (PID: A18541405)

``` r
url <- "https://bioboot.github.io/bggn213_W19/class-material/rs8067378_ENSG00000172057.6.txt"
dat <- read.table(url, header = TRUE, stringsAsFactors = TRUE)
```

``` r
head(dat)
```

       sample geno      exp
    1 HG00367  A/G 28.96038
    2 NA20768  A/G 20.24449
    3 HG00361  A/A 31.32628
    4 HG00135  A/A 34.11169
    5 NA18870  G/G 18.25141
    6 NA11993  A/A 32.89721

``` r
str(dat)
```

    'data.frame':   462 obs. of  3 variables:
     $ sample: Factor w/ 462 levels "HG00096","HG00097",..: 170 424 165 37 299 219 96 285 138 17 ...
     $ geno  : Factor w/ 3 levels "A/A","A/G","G/G": 2 2 1 1 3 1 2 1 3 2 ...
     $ exp   : num  29 20.2 31.3 34.1 18.3 ...

``` r
table(dat$geno)
```


    A/A A/G G/G 
    108 233 121 

``` r
tapply(dat$exp, dat$geno, median)
```

         A/A      A/G      G/G 
    31.24847 25.06486 20.07363 

``` r
boxplot(exp ~ geno, data = dat,
        xlab = "Genotype at rs8067378",
        ylab = "ORMDL3 Expression",
        main = "ORMDL3 Expression by Genotype",
        col = c("pink", "gray", "blue"))
```

![](Class12pt2.markdown_strict_files/figure-markdown_strict/unnamed-chunk-6-1.png)

## Population Analysis
