# Meta-Analyses in Python

```{tableofcontents}
```

## What is meta-analysis?

Meta-analysis is the re-use, and often aggregation, of previously computed statistical results. Analyzing previously computed results, often across several published studies, in this way is used to find consensus and/or parse differences across studies of a similar topic or paradigm. 

Meta-analysis leans on relatively light-weight data representations (e.g., published tabular data) and, thus, does not require the original source of data. This allows wide reuse without the privacy concerns or computational resources necessary for re-analysis of primary datasets. Further, published results are often more accessible than original data sources, making it possible to synthesize many independent sources of information.


## Why would you want to do a meta-analysis?

In the face of replication crises–such as those plaguing neuroimaging,  psychology, and cancer research–being able to aggregate results in this way is particularly valuable. Researchers can use meta-analysis to identify consistency across studies and papers. Neuroimaging meta-analyses, specifically, can allow researchers to find consistency across relatively homogeneous or related groups of studies, regardless of individual study sample sizes, pipeline differences, and intrinsic differences in functional neuroanatomy between study samples (i.e., {cite}`pintos_lobo_neural_2022`). On the other hand, meta-analysis can help identify a common effect across related, but distinct, studies {cite}`bartley_meta-analytic_2018`.

Further, neuroimaging meta-analyses can be used to generate hypotheses for future primary data analysis, as well. Meta-analytically generated brain networks or regions of interest (ROIs) that are significantly activated across a cognitive or behavioral paradigm can be used in subsequent analyses (e.g., for limited field-of-view, functional connectivity, or psychophysiological interaction studies). Data-driven classification of a larger set of studies into distinct categories based on similarity of brain activations can be used to investigate or propose underlying cognitive/neurobiological models of complex processing {cite}`bottenhorn_cooperating_2018, flannery_meta-analytic_2020, laird_neural_2015, riedel_dissociable_2018`. Further, meta-analyses can be useful in identifying common neural phenomena shared by multiple, seemingly distinct psychiatric diagnoses {cite}`dugre_meta-analytical_2022, janiri_shared_2020, opel_cross-disorder_2020`.

## How is meta-analysis in neuroimaging different from your standard, effect-size meta-analysis?

A standard meta-analysis aggregates results across a single measure. Neuroimaging meta-analyses are a special case because:
- data from a single statistical analysis of neuroimaging often include more than one effect size (e.g., multiple significant voxels, represented by stereotaxic coordinates)
- stereotaxic coordinates include spatial information, in addition to effect sizes and significance, and thus require additional processing

There are two over-arching categories of neuroimaging meta-analyses, differentiated by the input data source. *Coordinate-based* meta-analyses are run on stereotaxic x-, y-, z-coordinate data, such as those published in neuroimaging papers, while *image-based* meta-analyses run on 3D statistical image data, such as those shared on various online repositories (e.g., NeuroVault, the Open Science Framework). There are several algorithms for both categories, but they are both distinguished from standard meta-analyses by both the volume of data per study/case (i.e., coordinates, voxels), the spatial information that is inherent to that data, and the assumptions of independence that those two features violate.

```{bibliography}
:filter: docname in docnames
```