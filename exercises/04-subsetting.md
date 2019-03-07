Foundations: Subsetting
================

## 4.2 Selecting multiple elements

1.  Fix each of the following common data frame subsetting errors:

<!-- end list -->

``` r
mtcars[mtcars$cyl = 4, ]
mtcars[-1:4, ]
mtcars[mtcars$cyl <= 5]
mtcars[mtcars$cyl == 4 | 6, ]
```

2.  Why does the following code yield five missing values? (Hint: why is
    it different from x\[NA\_real\_\]?)

<!-- end list -->

``` r
x <- 1:5
x[NA]
```

3.  What does upper.tri() return? How does subsetting a matrix with it
    work? Do we need any additional subsetting rules to describe its
    behaviour?

<!-- end list -->

``` r
x <- outer(1:5, 1:5, FUN = "*")
x[upper.tri(x)]
```

4.  Why does mtcars\[1:20\] return an error? How does it differ from the
    similar mtcars\[1:20, \]?

> t does not know if 1:20 are the rows or columns.

5.Implement your own function that extracts the diagonal entries from a
matrix (it should behave like diag(x) where x is a matrix).

> 

6.  What does df\[is.na(df)\] \<- 0 do? How does it work?

> Replaces all NAs with 0s

## 4.3 Selecting a single element

1.  Brainstorm as many ways as possible to extract the third value from
    the cyl variable in the mtcars dataset.

> 

2.  Given a linear model, e.g., mod \<- lm(mpg \~ wt, data = mtcars),
    extract the residual degrees of freedom. Then extract the R squared
    from the model summary (summary(mod)).

> 

## 4.5 Applications

1.  Positive integers select elements at specific positions, negative
    integers drop elements; logical vectors keep elements at positions
    corresponding to TRUE; character vectors select elements with
    matching names.

> 

2.  \[ selects sub-lists: it always returns a list. If you use it with a
    single positive integer, it returns a list of length one. \[\[
    selects an element within a list. $ is a convenient shorthand: x$y
    is equivalent to x\[\[“y”\]\].

> 

3.  Use drop = FALSE if you are subsetting a matrix, array, or data
    frame and you want to preserve the original dimensions. You should
    almost always use it when subsetting inside a function.

> 

4.  If x is a matrix, x\[\] \<- 0 will replace every element with 0,
    keeping the same number of rows and columns. In contrast, x \<- 0
    completely replaces the matrix with the value 0.

> 

5.  A named character vector can act as a simple lookup table: c(x = 1,
    y = 2, z = 3)\[c(“y”, “z”, “x”)\]

>