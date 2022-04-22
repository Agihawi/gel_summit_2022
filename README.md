# Genomics England Research Summit 4th May 2022

This repository will recreate the poster displayed at the Genomics England research summit 4th May 2022 and provide the associated information required for reproducibility.

# Poster Production

The [poster](gel_summit_2022.pdf) was created using the [posterdown](https://cran.r-project.org/web/packages/posterdown/index.html) package. To run, render the `Posterdown.Rmd` file. The output will be in html format. A PDF version is also provided in this repo.

# SEPATH Pipeline Parameters:

The [SEPATH](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-019-1819-8) pipeline is available as a singularity on [github](https://github.com/UEA-Cancer-Genetics-Lab/sepath_tool_UEA).

This pipeline was ran on all cancer whole genome sequences (v8 release) from the 100,000 Genomes Project with the following parameters (all others parameters were as default):

`krakendb` - All genomes in [NCBI Refseq](https://www.ncbi.nlm.nih.gov/refseq/) scaffold level and above (bacterial, viral, fungal, protozoal). Dustmasked to remove low complexity. See `names.dmp` and `nodes.dmp` on a [previous poster repository](https://github.com/Agihawi/Gel_Conference_Poster_1/tree/master/resources) for taxonomy information. `database.kdb` MD5:`1e5bbafdef19775b6a9a9055598fb709` 

`kraken_confidence` - 0.2 - 20% of assigned _k_-mers within a read must assign to a taxonomy before classification can be determined.

`min_clade_reads` - 0 - left unfiltered until analysis.

`bbduk_db` - Human reference [genome 38](https://www.ncbi.nlm.nih.gov/assembly/GCF_000001405.38/) (no decoys) with additional cancer sequences from the [COSMIC](https://cancer.sanger.ac.uk/cosmic/download) database

`minimum_quality` - 20 - in addition to quality control from Illumina

`minimum_length` -  35 - sufficient for _k_=31 runs with kraken. set low to preserve data


