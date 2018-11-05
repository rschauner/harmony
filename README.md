# Harmony

Check out the latest preprint of Harmony on [bioRxiv](https://www.biorxiv.org/content/early/2018/11/04/461954)

![ ](Figure1.jpg)

# Installation

To run Harmony, open R and install directly from github using the following commands: 

```
library(devtools)
install_github("immunogenomics/harmony")
```

# Getting Started

Try out Harmony on your single cell dataset! If you already have PCA embeddings for your cells and a vector that defines some batch you want to integrate over, Harmony will do the rest: 

```
library(harmony)
my_harmony_embeddings <- HarmonyMatrix(my_pca_embeddings, my_batch_vector)
```

Now your cell embeddings will be less dependent on your batch variable. Do you want to align the data even more? Consider increasing the alignment parameter: 

```
my_harmony_embeddings <- HarmonyMatrix(my_pca_embeddings, my_batch_vector, theta = 4)
```

## Harmony in a Seurat workflow

If you already have a Seurat workflow for analyzing your single cell data, check out the tutorial below. To run Harmony, use the `RunHarmony` function. To then use Harmony in RunTSNE, specify `reduction.use = "harmony"`. To use it in FindClusters, specify `reduction.type = "harmony"`. 

We created a wrapper function `RunHarmony` to seamless integrate into your existing Seurat workflow. Check out this vignette to see how it works: 

[Aligning 10X PBMCs](https://github.com/immunogenomics/harmony/blob/master/vignettes/Seurat.ipynb)

This vignette is based on the original in Seurat: 

[Suerat Vignette](https://satijalab.org/seurat/pbmc3k_tutorial.html)

## Harmony with two or more covariates

Coming soon!

This section will show you how to align cells from donors and tissues at the same time. 





