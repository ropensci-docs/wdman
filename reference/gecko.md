# Start gecko driver

Start gecko driver

## Usage

``` r
gecko(
  port = 4567L,
  version = "latest",
  check = TRUE,
  loglevel = c("info", "fatal", "error", "warn", "config", "debug", "trace"),
  verbose = TRUE,
  retcommand = FALSE,
  ...
)
```

## Arguments

- port:

  Port to run on

- version:

  what version of geckodriver to run. Default = "latest" which runs the
  most recent version. To see other version currently sourced run
  binman::list_versions("geckodriver")

- check:

  If TRUE check the versions of geckodriver available. If new versions
  are available they will be downloaded.

- loglevel:

  Set Gecko log level \[values: fatal, error, warn, info, config, debug,
  trace\]

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
gDrv <- gecko()
gDrv$output()
gDrv$stop()
} # }
```
