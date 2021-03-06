Untitled


Big data ain't all about the big 'amount' of data, but also the 'big' variety of their kinds. Today we deal with not only data handed to us in the spreadsheet, but also those in all forms such as texts, audio and images.


================
Miriam Chou
16 June 2018

Set up
------

``` r
library(png)
```

Load images
===========

``` r
img.a <- readPNG("lena.png")
img.b <- readPNG("lena_modified.png")
```

Data checking
=============

``` r
str(img.a) ; str(img.b) # Array 512*512*4
```

    ##  num [1:512, 1:512, 1:4] 0.635 0.635 0.635 0.635 0.635 ...

    ##  num [1:512, 1:512, 1:4] 0.635 0.635 0.635 0.635 0.635 ...

Difference extraction
=====================

``` r
diff.arr <- array(1L, dim = c(512, 512, 4))
diff.index <- which(img.a != img.b)
diff.arr[diff.index] <- img.b[diff.index]
```

Export image
============

``` r
writePNG(diff.arr, "difference.png")
```
