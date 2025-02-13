---
title: Loading data
layout: default
nav_order: 2
---

# Loading data

To view a dataset in Portable-CELLxGENE, simply create a folder containing the
`.h5ad` files of interest and select this folder when prompted by the software.
Rendered notebooks can be made accessible to the user by storing them within
this folder in a subfolder named `rendered_notebooks`.

## Creating an `h5ad` file from your data

If you want to distribute your own dataset for others to view in Portable-CELLxGENE, you first need to save it as an `h5ad` file. This is the native format of the scanpy package in Python. If your dataset is called `cells`, then it can be saved in this format with:

```python
cells.write_h5ad("my_dataset.h5ad")
```

### Converting Seurat objects to `.h5ad` files

If you are instead analysing your dataset in Seurat, then you can save your
data as an `h5ad`  using the `SeuratDisk` package. By default, the `.h5ad`
files created by the standard Seurat to Anndata conversion process (detailed
[here](https://mojaveazure.github.io/seurat-disk/articles/convert-anndata.html))
contain only the highly variable genes, and therefore other genes cannot be
annotated in `CELLxGENE`. This can be fixed by removing the `scale.data` slot
of the Seurat object (along with the count data, for memory reasons) with the
`DietSeurat` function.  This object can then be converted to a `.h5ad` file
using the process detailed in the link above. Putting this together:

```r
# For each Seurat object you want to include in Portable-CELLxGENE:
# Assume Seurat object is called "cells"
library(Seurat)
library(SeuratDisk)
# Remove everything except data slot and UMAP reduction
cells <- DietSeurat(cells, scale.data = FALSE, counts = FALSE,
                        dimreducs = "umap")
SaveH5Seurat(object = cells, filename = "cells.h5Seurat")
Convert(source = "cells.h5Seurat", dest = "h5ad")
```

If you experience problems with the above process, an alternative approach is to use the [zellkonverter](https://github.com/theislab/zellkonverter) package. If you still cannot save your data in this format, submit an [issue](https://github.com/george-hall-ucl/portable-cellxgene/issues) on GitHub.

## Analysing public data

The `h5ad` format is often used to distribute single-cell transcriptomic datasets. All datasets in the [CELLxGENE Discover](https://cellxgene.cziscience.com/datasets) database can be downloaded in this format by clicking "Download" and then selecting `.h5ad` under "Data format". The downloaded files can be loaded in Portable-CELLxGENE as detailed at the top of this page.
