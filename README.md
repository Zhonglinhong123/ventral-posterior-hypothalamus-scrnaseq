# Mickelsen et al 2020 scRNA-seq of the Ventroposterior Hypothalamus

## Sample descriptions

Ventral posterior hypothalamus microdissections were harvested from four (4)
batches of three (3) mice.  Two batches were harvested at a time, one male
batch and one female batch:

| LibraryID | Batch | Strain | Age | Sex | Harvest | Time of Harvest | Chemistry Version |
|---|---|---|---|---|---|---|---|
| AJ18003 | 1 | C57BL/6 | P30-35 | Male | 1 | March 2018 | v2 |
| AJ18004 | 2 | C57BL/6 | P30-35 | Female | 1 | March 2018 | v2 |
| AJ19001 | 3 | C57BL/6 | P30-35 | Female | 2 | March 2019 | v3 |
| AJ19002 | 4 | C57BL/6 | P30-35 | Male | 2 | March 2019 | v3 |

## Combined data

You can interactively analyze the resulting aggregated data using the [10X
Loupe Browser][loupe-link] by downloading `.cloupe` files we've prepared using
our datasets, [available for download here][ftp-loupe-link].

We have provided 3 Loupe files for the aggregated global clustering, neuronal
sub-clustering, and non-neuronal subclustering.

When using the Loupe files, note the following:
-   As of March 2020, all Loupe files will contain *****default t-SNE and UMAP
    embeddings as well as default K-means and Graph-based clustering*** that was
    generated by 10X's cellranger tool.  It is currently impossible to remove
    these entries from the Loupe file.  

-   To circumvent these, we have added our UMAP embedding under the name
    "CustomUMAP" and our clustering under the name "Custom Clustering".  Please
    refer to these when trying to correlate the Loupe file with results
    presented in the manuscript.


## Overview of the analysis

## Reproducing manuscript figures

The manuscript figures were generated as individual panels which were then
combined in Adobe Illustrator.  However, the individual panels showing scRNA-seq
can be regenerated using notebooks in `notebooks/` and associated utility
scripts.  You can view those directly here:

-   [Main figures][main-notebook]
-   [SI figures][si-notebook]
-   [Extra figures][extra-notebook]

### Requirements

Full requirements are listed in the `environment.yaml` file, but for the most
part, the following Python 3.6+ packages are needed.

```bash
scanpy
numpy
pandas
scikit-learn
matplotlib
seaborn
cmocean
```

### Downloading data

Some of the data is too large to host on GitHub.  Download the data directly
via your [web browser][ftp-link] or use the command line:

```bash
git clone git@github.com:TheJacksonLaboratory/ventroposterior-hypothalamus-scrna-seq.git
cd ventroposterior-hypothalamus-scrna-seq/data
wget ftp://ftp.jax.org/flynnb/mickelsen-vph-2020/h5ad.zip
unzip h5ad.zip
```

### Running the notebooks

```bash
jupyter notebook notebooks/main_figures.ipynb
jupyter notebook notebooks/si_figures.ipynb
jupyter notebook notebooks/extra_figures.ipynb
```


[loupe-link]: https://support.10xgenomics.com/spatial-gene-expression/software/downloads/latest
[ftp-link]: ftp://ftp.jax.org/flynnb/mickelsen-vph-2020/
[ftp-loupe-link]: ftp://ftp.jax.org/flynnb/mickelsen-vph-2020/loupe.zip
[main-notebook]: https://github.com/TheJacksonLaboratory/ventroposterior-hypothalamus-scrna-seq/blob/master/notebooks/main_figures.ipynb
[si-notebook]: https://github.com/TheJacksonLaboratory/ventroposterior-hypothalamus-scrna-seq/blob/master/notebooks/si_figures.ipynb
[extra-notebook]: https://github.com/TheJacksonLaboratory/ventroposterior-hypothalamus-scrna-seq/blob/master/notebooks/extra_figures.ipynb
