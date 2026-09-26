# A checked delivery with DataRaft

**Run one data delivery, check it, and keep a version you can revisit.**

This example starts with three orders. It checks the columns and amounts, writes an RDS release, and creates a contract file and an HTML quality report. Start with the [DataRaft overview](https://github.com/dataraft-r/dataraft) if you want to understand the whole package family first.

## Run the example

Requires R 4.2 or later and Git. Clone the repository, install its two DataRaft packages, and run the script:

```sh
git clone https://github.com/dataraft-r/dataraft-example.git
cd dataraft-example
Rscript -e 'install.packages("pak"); pak::pak(c("dataraft-r/dataraft.core", "dataraft-r/dataraft.adapters"), dependencies = NA)'
Rscript run.R
```

The script prints a release version. It checks that the saved order amounts add up to 150. By default it uses a temporary directory; set `DATARAFT_EXAMPLE_OUTPUT` to a directory to keep the RDS release, ODCS contract and HTML report.

The [source script](run.R) shows the complete flow. Read the [getting-started guide](https://dataraft-r.github.io/dataraft/articles/get-started.html) for the concepts or the [adapters documentation](https://dataraft-r.github.io/dataraft/components/dataraft.adapters/reference/index.html) for RDS targets. The [GitHub Actions workflow](.github/workflows/example.yaml) runs the script on every change.

DataRaft is under development. This example demonstrates one checked delivery, not a production certification.
