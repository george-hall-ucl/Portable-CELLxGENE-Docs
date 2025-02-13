---
title: FAQs
layout: default
nav_order: 7
---

# Frequently asked questions

If you cannot find the answer to your problem here, please post it as an [issue](https://github.com/george-hall-ucl/portable-cellxgene/issues) on GitHub.

## How do I fix crashes?

### `Cellxgene Gateway - Process Error`

Crashed sessions often display the error `Cellxgene Gateway - Process Error`. These crashes can have different causes, which can be differentiated by the text next to "Stderr". Find the question most closely related to your Stderr text.

### Stderr contains: `Usage: cellgene launch <options> <path to data file> Error: Got unexpected extra arguments`

This error often means that there are spaces in the name of the `.h5ad` file or in one of the folders within which it is contained. Remove these spaces and see if this solves the problem.

### Stderr ends: `PrepareError: No valid layout data.`

This often means that there is no UMAP or PCA (or other valid) dimensionality reduction in your h5ad file. You must first compute one: Portable-CELLxGENE does not compute these itself, but simply displays existing ones.

### On Windows, Portable-CELLxGENE is prevented from launching

Windows requires a significant number of users before allowing software to run without a warning. Before this number is reached, it is likely to display a warning the first time it is run. See the Windows [installation instructions](installation.html#windows) for how to fix this.

### On Windows, Python is prevented from launching

The Windows firewall can prevent Python from running. You can allow its access from the pop-up. You may need to restart CELLxGENE for this to take effect.

## How can I cite Portable-CELLxGENE?

See [here](citation.html).
