---
title: "Part I: Introduction"
author: "Laurent Gatto"
---

## References

- [Advanced R](http://adv-r.had.co.nz/), Hadley Wickham.
- [The R Inferno](http://www.burns-stat.com/documents/books/the-r-inferno/), Patrick Burns.
- [An Introduction to the Interactive Debugging Tools in R](http://www.biostat.jhsph.edu/~rpeng/docs/R-debug-tools.pdf), Roger D. Peng.
- [R Programming for Bioinformatics](http://master.bioconductor.org/help/publications/books/r-programming-for-bioinformatics/), Robert Gentleman.

## Coding style(s)

Why?

> Good coding style is like using correct punctuation. You can manage
> without it, but it sure makes things easier to read.
-- Hadley Wickham

for **consistency** and **readability**.

## Which one?

- [Bioconductor](http://master.bioconductor.org/developers/how-to/coding-style/)
- [Hadley Wickham](http://r-pkgs.had.co.nz/style.html)
- [Google](http://google.github.io/styleguide/Rguide.xml)
- ...

## Examples

- Place spaces around all infix operators (`=`, `+`, `-`, `<-`, etc., but *not* `:`)
  and after a comma (`x[i, j]`).
- Spaces before `(` and after `)`.
- Use `<-` rather than `=`.
- Limit your code to 80 characters per line
- Indentation: do not use tabs, use 2 (HW)/4 (Bioc) spaces
- Function names: use verbs
- Variable names: camelCaps (Bioc)/ `_` (HW) (but not a `.`)
- Prefix non-exported functions with a ‘.’ (Bioc).
- Class names: start with a capital
- Comments: `# ` or `## ` (from emacs)

## [`formatR`](https://cran.rstudio.com/web/packages/formatR/index.html)


```r
library("formatR")
tidy_eval(text = c("a=1+1;a  # print the value", "matrix ( rnorm(10),5)"),
          arrow = TRUE)
```

```
## a <- 1 + 1
## a  # print the value
## ## [1] 2
## 
## matrix(rnorm(10), 5)
## ##            [,1]         [,2]
## ## [1,] -1.4667074  0.109601352
## ## [2,]  2.3879977 -0.001741281
## ## [3,]  0.3004284  1.078886704
## ## [4,] -1.0106071 -0.473581455
## ## [5,] -1.5194370 -0.592679401
```

## [`BiocCheck`](http://bioconductor.org/packages/devel/bioc/html/BiocCheck.html)

```
* Checking function lengths................
  The longest function is 677 lines long
  The longest 5 functions are:
* Checking formatting of DESCRIPTION, NAMESPACE, man pages, R source,
  and vignette source...
    * CONSIDER: Shortening lines; 616 lines (11%) are > 80 characters
      long.
    * CONSIDER: Replacing tabs with 4 spaces; 3295 lines (60%) contain
      tabs.
    * CONSIDER: Indenting lines with a multiple of 4 spaces; 162 lines
      (2%) are not.
```

## Interactive use vs programming: `drop`

```
head(cars)
head(cars[, 1])
head(cars[, 1, drop = FALSE])
```

## Interactive use vs programming: `sapply/lapply`

```
df1 <- data.frame(x = 1:3, y = LETTERS[1:3])
sapply(df1, class)
df2 <- data.frame(x = 1:3, y = Sys.time() + 1:3)
sapply(df2, class)
```
## Interactive use vs programming

Moving from using R to programming R is *abstraction*, *automation*,
*generalisation*.

## Environments

## Semantincs

- pass-by-ref: environments, S4 Reference Classes
- pass-by-value (copy-on-modify)

## Computing on the language

## Tidy data

(interactive use)
- tidy data
- pipe operator
