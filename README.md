
<!-- README.md is generated from README.Rmd. Please edit that file -->

[![Build
Status](https://travis-ci.org/r-box/boxr.svg?branch=master)](https://travis-ci.org/r-box/boxr)
[![Win Build
Status](https://ci.appveyor.com/api/projects/status/github/r-box/boxr?branch=master&svg=true)](https://ci.appveyor.com/project/r-box/boxr)
[![Project Status: Active - The project has reached a stable, usable
state and is being actively
developed.](https://img.shields.io/badge/repo%20status-active-brightgreen.svg)](https://www.repostatus.org/#active)
[![cran
version](https://www.r-pkg.org/badges/version/boxr)](https://cran.rstudio.com/web/packages/boxr)
![monthly\_downloads](https://cranlogs.r-pkg.org/badges/boxr)

# boxr <img src="man/figures/logo.png" align="right" alt="" width="120" />

A lightweight, *opinionated*, high-level R interface to the box.com API,
standing on the shoulders of **[httr](https://github.com/r-lib/httr)**.

[Box](https://www.box.com) is a cloud content-management and
file-sharing service. The goal of the **boxr** package is to make it
easier for you to conduct data analyses that interact with your Box
account.

## New in boxr 0.3.5

It has been a while since the last CRAN release of boxr; we are pleased
to to announce:

  - the package-documentation has been fortified, including a [pkgdown
    site](https://r-box.github.io/boxr/).

  - a new authentication method: `box_auth_service()`, described in this
    [article](https://r-box.github.io/boxr/articles/boxr-app-service.html).

  - new maintainers: the creator of boxr, Brendan Rocks, is now
    maintainer-emeritus. The day-to-day maintenance is handled by Nathan
    Day and Ian Lyttle.

Other changes are detailed in the
[NEWS](https://r-box.github.io/boxr/news/index.html).

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

The package-documentation website is created and maintained using
[pkgdown](https://pkgdown.r-lib.org). Upon the CRAN release for version
0.3.5, the documentation website consists of:

  - a [CRAN-version site](https://r-box.github.io/boxr/).
  - a [development-version site](https://r-box.github.io/boxr/dev).

## Usage

We have a [Get-started
article](https://r-box.github.io/boxr/articles/boxr.html) that goes into
more detail on interacting with your Box account using R.

### Authentication

Any time you interact with the Box API, you will be using a Box
application, i.e. a Box-app. If you’ve already used boxr to authenticate
with Box, you’ve already used a Box app.

#### tl;dr

If you have access to `client_id` and `client_secret` for a Box-app, you
can use `box_auth()` to authenticate:

``` r
box_auth(client_id = "your_client_id", client_secret = "your_client_secret")
```

This will kick off a process that, all being well, will keep you
authenticated for the rest of the R session. By saving this information
to your `.Renviron` file, at your next R session you can use, without
arguments:

``` r
box_auth()
```

If you don’t have access to `client_id` and `client_secret` for a
Box-app, read on.

#### Details

You can think of a Box-app as the door through which boxr functions can
access Box. For the most part, boxr functions keep this “out-of-mind”.
During authentication, Box-apps come to the fore.

Getting the authentication to work the first time is most difficult part
of using this package. Once you get it working, it should *just work*.

How you deal with Box-apps may depend on your situation:

  - **“I use a personal Box account”**:
    
    You will have to set up a Box-app, then authenticate to it.

  - **“I use a Box account that an institution manages”**:
    
    Your institution may have set up an app already; you may be able to
    authenticate to it. If not, maybe you can create a Box-app or ask
    your Box-admin team to create one.

The type of Box-app you use may also depend your situation:

  - **“I want to use boxr interactively, from my local computer”**:
    
    We recommend you use a Box interactive-app, then authenticate using
    `box_auth()`. You can read more in this [interactive-app
    article](https://r-box.github.io/boxr/articles/boxr-app-interactive.html).

  - **“I want to run an unattended scheduled process, e.g. a report,
    from a remote machine using boxr”**:
    
    We recommend you use a Box service-app, then authenticate using
    `box_auth_service()`. You can read more in this [service-app
    article](https://r-box.github.io/boxr/articles/boxr-app-service.html).

  - **“I want to use boxr interactively using a remote machine, perhaps
    using RStudio Cloud or RStudio Server.”**:
    
    You could go either way; this situation is covered in both the
    [interactive-app
    article](https://r-box.github.io/boxr/articles/boxr-app-interactive.html#transfer)
    and the [service-app
    article](https://r-box.github.io/boxr/articles/boxr-app-service.html#transfer).

The differences between the two types of apps are discussed in this
[overview article](https://r-box.github.io/boxr/articles/boxr-apps.html)
on Box-apps.

### Basic operations

  - [Accessing Box
    directories](https://r-box.github.io/boxr/articles/boxr.html#accessing-box-directories-folders):
    `box_setwd()`, `box_getwd()`, `box_dir_create()`, `box_ls()`,
    `box_push()`, `box_fetch()`.
  - [Accessing Box
    files](https://r-box.github.io/boxr/articles/boxr.html#accessing-box-files):
    `box_ul()`, `box_dl()`, `box_previous_versions()`,
    `box_add_description()`.
  - [Searching
    Box](https://r-box.github.io/boxr/articles/boxr.html#searching-box):
    `box_search()`.

### Advanced operations

  - [Using Box
    trash](https://r-box.github.io/boxr/articles/boxr.html#using-box-trash):
    `box_delete_file()`, `box_delete_folder()`, `box_restore_file()`,
    `box_restore_folder()`.
  - [Interacting with your R
    session](https://r-box.github.io/boxr/articles/boxr.html#interacting-with-your-r-session):
    `box_read()`, `box_write()`, `box_source()`, `box_save()`,
    `box_load()`.

## Alternatives

Other ways to interact with a Box account include:

  - The [Box desktop apps](https://www.box.com/resources/downloads).
  - The *other* boxr, [written in
    Ruby](https://github.com/cburnette/boxr). Its motivations are rather
    different, and it covers 100% of the box.com API (e.g account
    administration, etc.).
  - Box themselves provide a [wide range of
    SDKs](https://github.com/box), including [one for
    Python](https://github.com/box/box-python-sdk).

## Contributing

Always very welcome\! If you’d like to submit a pull request for a new
feature, ideally it would be documented, come with an addition to
[NEWS.md](https://r-box.github.io/boxr/news/index.html), and have a test
or two. This project has a standard [Code of
Conduct](https://r-box.github.io/boxr/CONDUCT.html).

## License

The MIT License (MIT)

Copyright (c) 2015-2020 boxr contributors

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
