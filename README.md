# Checked delivery with DataRaft

[![Checked delivery](https://github.com/dataraft-r/dataraft-example/actions/workflows/example.yaml/badge.svg)](https://github.com/dataraft-r/dataraft-example/actions/workflows/example.yaml)

A small, runnable example of a checked data delivery without DuckDB or Arrow.
It writes a versioned RDS delivery, an ODCS contract and an HTML quality report.

## Run

Requires R 4.2 or later. Install the two DataRaft components:

```r
install.packages("pak")
pak::pak(c("dataraft-r/dataraft.core", "dataraft-r/dataraft.adapters"), dependencies = NA)
```

Clone this repository, then run from its directory:

```sh
Rscript run.R
```

The script checks three orders whose amounts sum to 150. Set the environment
variable `DATARAFT_EXAMPLE_OUTPUT` to a directory to retain the output. Otherwise
the example uses a temporary directory. The printed version pins later reads
with `dr_source_rds()`.

The GitHub Actions workflow installs only hard package dependencies and checks
the example on every push and pull request.

See the [DataRaft documentation](https://dataraft-r.github.io/dataraft/) and
[guarantees](https://github.com/dataraft-r/dataraft/blob/main/vignettes/guarantees.Rmd).
DataRaft is experimental software; this example is not a production certification.
