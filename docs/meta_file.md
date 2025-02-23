# Meta file

This pipeline was developed to download data from SRA and process it in parallel. The meta file and all of the data assume that you are wanting to download the data for process. If you want to use your own data, you will need to manipulate the meta file and directory structure so that you skip `fasterq-dump` and proceed to read trimming.

The meta file is a `.tsv` file that has at least two columns named `srx` and `srr`. The biological replicate is considered the `srx` ID and the technical replicate is considered the `srr` ID. If you have more than one `srr` ID per `srx` ID the technical replicates will be merged into a single `srx` based output. The code will use the `srr` ID to download the `.fastq` files that are to be processed. Right now you must provide all the `srr` ID values for a `srx` ID on your own.

Example meta file:

```tsv
srr	srx
SRR5427886	SRX2717911
SRR5427887	SRX2717912
```