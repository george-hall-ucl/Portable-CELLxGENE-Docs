---
title: Distributing your data
layout: default
nav_order: 2
---

# Distributing your data

To distribute your data using this app, simply create a folder containing
`.h5ad` files of the datasets of interest. Rendered notebooks can be made
accessible to the user by storing them in a folder named `rendered_notebooks`.
The recipient needs to download the Portable-CELLxGENE app and run it using the
above guide.

## Converting Seurat objects to `.h5ad` files

By default, the `.h5ad` files created by the standard Seurat to Anndata
conversion process (detailed
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

Remember that you must have calculated a umap reduction of your dataset to give
Portable-CELLxGENE something to plot!
