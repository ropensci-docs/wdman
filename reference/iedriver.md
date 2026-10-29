# Start IE driver server

Start IE driver server

## Usage

``` r
iedriver(
  port = 4567L,
  version = "latest",
  check = TRUE,
  loglevel = c("FATAL", "TRACE", "DEBUG", "INFO", "WARN", "ERROR"),
  verbose = TRUE,
  retcommand = FALSE,
  ...
)
```

## Arguments

- port:

  Port to run on

- version:

  what version of IE driver server to run. Default = "latest" which runs
  the most recent version. To see other version currently sourced run
  binman::list_versions("iedriverserver")

- check:

  If TRUE check the versions of IE driver available. If new versions are
  available they will be downloaded.

- loglevel:

  Specifies the log level used by the server. Valid values are: TRACE,
  DEBUG, INFO, WARN, ERROR, and FATAL. Defaults to FATAL if not
  specified.

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
ieDrv <- iedriver()
ieDrv$output()
ieDrv$stop()
} # }
```
