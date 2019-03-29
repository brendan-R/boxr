
<!-- README.md is generated from README.Rmd. Please edit that file -->

[![Build
Status](https://travis-ci.org/r-box/boxr.svg)](https://travis-ci.org/r-box/boxr)
[![Win Build
Status](https://ci.appveyor.com/api/projects/status/github/r-box/boxr?branch=master&svg=true)](https://ci.appveyor.com/project/r-box/boxr)
[![Project Status: Active - The project has reached a stable, usable
state and is being actively
developed.](https://img.shields.io/badge/repo%20status-active-brightgreen.svg)](https://www.repostatus.org/#active)
[![cran
version](https://www.r-pkg.org/badges/version/boxr)](https://cran.rstudio.com/web/packages/boxr)
![monthly\_downloads](https://cranlogs.r-pkg.org/badges/boxr)

# boxr

A lightweight, high-level R interface to the box.com API, standing on
the shoulders of [`httr`](https://github.com/hadley/httr).

[Box](https://www.box.com) is a cloud content-management and
file-sharing service. The goal of the **boxr** package is to make it
easier for you to conduct data analyses that interact with your Box
account.

## Installation

You can download boxr from
[CRAN](https://CRAN.R-project.org/package=boxr), with:

``` r
install.packages("boxr")
```

If you’d like to download the development version from GitHub, use:

``` r
# install.packages("devtools")
devtools::install_github("r-box/boxr")
```

### Documentation

The packge-documentation website is created and maintained using
[pkgdown](https://pkgdown.r-lib.org). Upon the CRAN release for version
0.3.5, the documentation website will consist of:

  - a [CRAN-version site](https://r-box.github.io/boxr/)
  - a [development-version site](https://r-box.github.io/boxr/dev)

Until the CRAN release for version 3.5, the most-current version of the
site will be the [development-version
site](https://r-box.github.io/boxr/dev).

## Usage

We have a [Get-started
article](https://r-box.github.io/boxr/articles/boxr.html) that goes into
more detail on interacting with your Box account using R.

### Authorization

This can be the a little tricky to set up, but once it works, going
forward, it should *just work*. As detailed in the
[article](https://r-box.github.io/boxr/articles/boxr.html#authorization),
there are two use-cases:

  - authorizing from R your local computer
  - authorizing from R on a remote server

Once you have made the configuration, you can use `box_auth()` to renew
your authorization for your R session.

### Basic operations

  - [Accessing Box
    directories](https://r-box.github.io/boxr/articles/boxr.html#accessing-box-directories-folders):
    `box_setwd()`, `box_getwd()`, `box_dir_create()`, `box_ls()`,
    `box_push()`, `box_fetch()`
  - [Accessing Box
    files](https://r-box.github.io/boxr/articles/boxr.html#accessing-box-files):
    `box_ul()`, `box_dl()`, `box_previous_versions()`,
    `box_add_description()`
  - [Searching
    Box](https://r-box.github.io/boxr/articles/boxr.html#searching-box):
    `box_search()`

### Advanced operations

  - [Using Box
    trash](https://r-box.github.io/boxr/articles/boxr.html#using-box-trash):
    `box_delete_file()`, `box_delete_folder()`, `box_restore_file()`,
    `box_restore_folder()`
  - [Interacting with your R
    session](https://r-box.github.io/boxr/articles/boxr.html#interacting-with-your-r-session):
    `box_read()`, `box_write()`, `box_source()`, `box_save()`,
    `box_load()`

## Alternatives

Other ways to interact with a Box account include:

  - The [Box desktop apps](https://www.box.com/resources/downloads)
  - The *other* boxr, [written in
    Ruby](https://github.com/cburnette/boxr). Its motivations are rather
    different, and it covers 100% of the box.com API (e.g account
    administration, etc.)
  - Box themselves provide a [wide range of
    SDKs](https://github.com/box), including [one for
    Python](https://github.com/box/box-python-sdk)

## Contributing

Always very welcome\! If you’d like to submit a pull request for a new
feature, ideally it would be documented, come with an addtion to
[NEWS.md](https://r-box.github.io/boxr/news/index.html), and have a test
or two. This project has a standard [Code of
Conduct](https://r-box.github.io/boxr/CONDUCT.html).

## License

The MIT License (MIT)

Copyright (c) 2015-2019 boxr contributors

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
“Software”), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
