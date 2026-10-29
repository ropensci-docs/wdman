# Start phantomjs

Start phantomjs in webdriver mode

## Usage

``` r
phantomjs(
  port = 4567L,
  version = "2.1.1",
  check = TRUE,
  loglevel = c("INFO", "ERROR", "WARN", "DEBUG"),
  verbose = TRUE,
  retcommand = FALSE,
  ...
)
```

## Arguments

- port:

  Port to run on

- version:

  what version of phantomjs to run. Default = "2.2.1" which runs the
  most recent stable version. To see other version currently sourced run
  binman::list_versions("phantomjs")

- check:

  If TRUE check the versions of phantomjs available. If new versions are
  available they will be downloaded.

- loglevel:

  Set phantomjs log level \[values: fatal, error, warn, info, config,
  debug, trace\]

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
pjs <- phantomjs()
pjs$output()
pjs$stop()
} # }
```
