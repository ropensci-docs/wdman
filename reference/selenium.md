# Start Selenium Server

Start Selenium Server

## Usage

``` r
selenium(
  port = 4567L,
  version = "latest",
  chromever = "latest",
  geckover = "latest",
  iedrver = NULL,
  phantomver = "2.1.1",
  check = TRUE,
  verbose = TRUE,
  retcommand = FALSE,
  ...
)
```

## Arguments

- port:

  Port to run on

- version:

  what version of Selenium Server to run. Default = "latest" which runs
  the most recent version. To see other version currently sourced run
  binman::list_versions("seleniumserver")

- chromever:

  what version of Chrome driver to run. Default = "latest" which runs
  the most recent version. To see other version currently sourced run
  binman::list_versions("chromedriver"), A value of NULL excludes adding
  the chrome browser to Selenium Server.

- geckover:

  what version of Gecko driver to run. Default = "latest" which runs the
  most recent version. To see other version currently sourced run
  binman::list_versions("geckodriver"), A value of NULL excludes adding
  the firefox browser to Selenium Server.

- iedrver:

  what version of IEDriverServer to run. Default = "latest" which runs
  the most recent version. To see other version currently sourced run
  binman::list_versions("iedriverserver"), A value of NULL excludes
  adding the internet explorer browser to Selenium Server. NOTE this
  functionality is Windows OS only.

- phantomver:

  what version of PhantomJS to run. Default = "2.2.1" which runs the
  most recent stable version. To see other version currently sourced run
  binman::list_versions("phantomjs"), A value of NULL excludes adding
  the PhantomJS headless browser to Selenium Server.

- check:

  If TRUE check the versions of selenium available and the versions of
  associated drivers (chromever, geckover, phantomver, iedrver). If new
  versions are available they will be downloaded.

- verbose:

  If TRUE, include status messages (if any)

- retcommand:

  If TRUE return only the command that would be passed to
  [`process`](http://processx.r-lib.org/reference/process.md)

- ...:

  pass additional options to the driver

## Value

Returns a list with named elements `process`, `output`, `error`, `stop`,
and `log`. `process` is the object from calling
[`process`](http://processx.r-lib.org/reference/process.md). `output`
and `error` are the functions reading the latest messages from "stdout"
and "stderr" since the last call whereas `log` is the function that
reads all messages. Lastly, `stop` call the `kill` method in
[`process`](http://processx.r-lib.org/reference/process.md) to the kill
the `process`.

## Examples

``` r
if (FALSE) { # \dontrun{
selServ <- selenium()
selServ$output()
selServ$stop()
} # }
```
