
<!-- README.md is generated from README.Rmd. Please edit that file -->
<!-- badges: start -->

[![R-CMD-check](https://github.com/illinois-r/uiucdata/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/illinois-r/uiucdata/actions/workflows/R-CMD-check.yaml)
<!-- badges: end -->

# uiucdata: An R Data Package for UIUC Data

The goal of `uiucdata` is to provide data sets available at the
[University of Illinois at Urbana-Champaign
(UIUC)](http://illinois.edu/) to a diverse group of individuals with a
low barrier for entry.

## Installation

You can install `uiucdata` from github with:

``` r
# install.packages("remotes")
remotes::install_github("coatless-rpkg/uiucdata")
```

## Example

There are two ways to access the data contained within this package.

The first is to load the package itself and type the name of a data set.
This approach takes advantage of *R*’s lazy loading mechansim, which
avoids loading the data until it is used in *R* session. For details on
how lazy loading works, please see [Section 1.17: Lazy
Loading](https://cran.r-project.org/doc/manuals/r-release/R-ints.html#Lazy-loading)
of the [R
Internals](https://cran.r-project.org/doc/manuals/r-release/R-ints.html)
manual.

``` r
# Load the `uiucdata` package
library("uiucdata")

# See the first 10 observations of the `fall_enrolled_ranking` dataset
head(fall_enrolled_ranking)

# View the help documentation for `fall_enrolled_ranking`
?fall_enrolled_ranking
```

The second approach is to use the `data()` command to load data on the
fly without and type the name of a data set.

``` r
# Loading `fall_enrolled_ranking` without a `library(ucidata)` call
data("fall_enrolled_ranking", package = "uiucdata")

# See the first 10 observations of the `fall_enrolled_ranking` dataset
head(fall_enrolled_ranking)

# View the help documentation for `fall_enrolled_ranking`
?fall_enrolled_ranking
```

## Included Data Sets

The following data sets are included in the `ucidata` package:

- [Division of Management Information](http://www.dmi.illinois.edu/)
  - [Student Enrollment by Curriculum and Class
    Level](http://www.dmi.illinois.edu/stuenr/#class)
- [Freedom of Information Data
  Sets](https://www.uillinois.edu/cms/One.aspx?portalId=1324&pageId=171041)
  - Grade Distribution Data
- [Center for Innovation in Teaching and Learning
  (CITL)](http://citl.illinois.edu/)
  - Teachers Ranked as Excellent (Data courtesy of Wade-Fagen, see the
    [project repo for more
    details](https://github.com/wadefagen/Teachers-Ranked-As-Excellent-UIUC))

## Build Scripts

Want to see how each data set was imported? Check out the
[`data-raw`](https://github.com/coatless-rpkg/uiucdata/tree/master/data-raw)
folder!

## Submodules

This repository uses submodules as a way to store data. This allows for
us to have the repositories contents as the final data product. As a
result, we avoid increase the size of the repository since the raw data
is now tracked in a separate repository. For more details, please see
GitHub’s [Working with
Submodules](https://github.com/blog/2104-working-with-submodules) post.

### Example submodule inclusion statement

``` bash
# Add Excellent Teacher Data in data-raw
git submodule add https://github.com/wadefagen/Teachers-Ranked-As-Excellent-UIUC data-raw/excellent-teachers
```

**NB** This repository is made by an employee of the University of
Illinois at Urbana-Champaign who is not the author of this data package.

------------------------------------------------------------------------

Raw grade data

``` bash
git submodule add https://github.com/coatless-rpkg/uiucgradedata data-raw/grade-dist
```
