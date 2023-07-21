# Methods to choose from
When coming up with your search process, you should have decided whether you were going to use a coordinate-based meta-analysis (CBMA) or an image-based meta-analysis (IBMA).
While in previous meta-analyses you may been constrained by the tool you were using to perform the meta-analysis, Neurosynth-Compose allows you to use a multitude of methods.

## CBMA

While sharing of statistical maps is becoming more common, it is still not the norm, and aggregation of statistical maps is still a difficult process.
Coordinates are much more commonly shared.

Coordinate-based meta-analysis (CBMA) is currently the most popular method for neuroimaging meta-analysis, given that the majority of fMRI papers currently report their findings as peaks of statistically significant clusters in standard space and do not release unthresholded statistical maps.
These peaks indicate where significant results were found in the brain, and thus do not reflect an effect size estimate for each hypothesis test (i.e., each voxel) as one would expect for a typical meta-analysis.
As such, standard methods for effect size-based meta-analysis cannot be applied.
Over the past two decades, a number of algorithms have been developed to determine whether peaks converge across experiments in order to identify locations of consistent or specific activation associated with a given hypothesis {cite:p}`Samartsidis2017-ej,Muller2018-mt`.

Kernel-based methods evaluate convergence of coordinates across studies by first convolving foci with a spatial kernel to produce study-specific modeled activation maps, then combining those modeled activation maps into a sample-wise map, which is compared to a null distribution to evaluate voxel-wise statistical significance.
Additionally, for each of the following approaches, except for SCALE, voxel- or cluster-level multiple comparisons correction may be performed using Monte Carlo simulations or false discovery rate (FDR) {cite:p}`Laird2005-qh` correction. Basic multiple-comparisons correction methods (e.g., Bonferroni correction) are also supported.

### CBMA kernels

CBMA kernels are available as {py:class}`~nimare.meta.kernel.KernelTransformer`s in the {py:mod}`nimare.meta.kernel` module.
There are three standard kernels that are currently available: {py:class}`~nimare.meta.kernel.MKDAKernel`, {py:class}`~nimare.meta.kernel.KDAKernel`, and {py:class}`~nimare.meta.kernel.ALEKernel`.
Each class may be configured with certain parameters when a new object is initialized.
For example, `MKDAKernel` accepts an `r` parameter, which determines the radius of the spheres that will be created around each peak coordinate.
`ALEKernel` automatically uses the sample size associated with each experiment in the `Dataset` to determine the appropriate full-width-at-half-maximum of its Gaussian distribution, as described in {cite:t}`EICKHOFF20122349`; however, users may provide a constant `sample_size` or `fwhm` parameter when sample size information is not available within the `Dataset` metadata.

### Multilevel kernel density analysis

**Multilevel kernel density analysis** (MKDA) {cite:p}`Wager2007-jc` is a kernel-based method that convolves each peak from each study with a binary sphere of a set radius.
These peak-specific binary maps are then combined into study-specific maps by taking the maximum value for each voxel.
Study-specific maps are then averaged across the meta-analytic sample.
This averaging is generally weighted by studies’ sample sizes, although other covariates may be included, such as weights based on the type of inference (random or fixed effects) employed in the study’s analysis.
An arbitrary threshold is generally employed to zero-out voxels with very low values, and then a Monte Carlo procedure is used to assess statistical significance, either at the voxel or cluster level.

In NiMARE, the MKDA meta-analyses can be performed with the {py:class}`~nimare.meta.cbma.mkda.MKDADensity` class.
This class, like most other CBMA classes in NiMARE, accepts a `null_method` parameter, which determines how voxel-wise (uncorrected) statistical significance is calculated.

```{admonition} On CBMA "null methods"
:class: tip
The `null_method` parameter allows two options: "approximate" or "montecarlo."
The "approximate" option builds a histogram-based null distribution of summary-statistic values, which can then be used to determine the associated p-value for _observed_ summary-statistic values (i.e., the values in the meta-analytic map).
The "montecarlo" option builds a null distribution of summary-statistic values by randomly shuffling the coordinates the `Dataset` many times, and computing the summary-statistic values for each permutation.
In general, the "montecarlo" method is slightly more accurate when there are enough permutations, while the "approximate" method is much faster.
```

```{warning}
Fitting the CBMA `Estimator` to a `Dataset` will produce p-value, z-statistic, and summary-statistic maps, but these are not corrected for multiple comparisons.

When performing a meta-analysis with the goal of statistical inference, you will want to perform multiple comparisons correction with NiMARE's `Corrector`
classes.
```



## IBMA

Image based meta-analysis is relatively new in the field of neuroimaging, although the methods have been around for a while since we can perform a more standard meta-analysis on the statistical maps where each voxel looked at for consensus whereas coordinates have to be transformed by some method to guess what the underlying statistical map looks like.

Image-based meta-analysis (IBMA) methods perform a meta-analysis directly on brain images (either whole-brain or partial) rather than on extracted peaks.
On paper, IBMA is superior to CBMA in virtually all respects, as the availability of analysis-level parameter and variance estimates at all analyzed voxels allows researchers to use the full complement of standard meta-analysis techniques, instead of having to resort to kernel-based or other methods that require additional spatial assumptions.
In principle, given a set of maps that contains no missing values (i.e., where there are _k_ valid pairs of parameter and variance estimates at each voxel), one can simply conduct a voxel-wise version of any standard meta-analysis or meta-regression method commonly used in other biomedical or social science fields.

In practice, the utility of IBMA methods has historically been quite limited, as unthresholded statistical maps have been unavailable for the vast majority of neuroimaging studies.
However, the introduction and rapid adoption of NeuroVault {cite:p}`Gorgolewski2015-sd`, a database for unthresholded statistical images, has made image-based meta-analysis increasingly viable.
Although coverage of the literature remains limited, and IBMAs of maps drawn from the NeuroVault database are likely to omit at least some (and in some cases most) relevant studies due to limited metadata,  we believe the time is ripe for researchers to start including both CBMAs and IBMAs in published meta-analyses, with the aspirational goal of eventually transitioning exclusively to the latter.
To this end, NiMARE supports a range of different IBMA methods, including a number of estimators of the gold standard mixed-effects meta-regression model, as well as several alternative estimators suitable for use when some of the traditional inputs are unavailable.

```{note}
NiMARE's IBMA `Estimator`s are light wrappers around classes from [PyMARE](https://pymare.readthedocs.io), a library for standard (i.e., non-neuroimaging) meta-analyses developed by the same team as NiMARE.
```


### Correctors

In NiMARE, multiple comparisons correction is separated from each CBMA and IBMA `Estimator`, so that any number of relevant correction methods can be applied after the `Estimator` has been fit to the `Dataset`.
Some correction options, such as the `montecarlo` option for FWE correction, are designed to work specifically with a given `Estimator` (and are indeed implemented within the `Estimator` class, and only called by the `Corrector`).

`Corrector`s are divided into two subclasses: `FWECorrector`s, which correct based on family-wise error rate, and `FDRCorrector`s, which correct based on false discovery rate.

All `Corrector`s are initialized with a number of parameters, including the correction method that will be used.
After that, you can use the `transform` method on a `MetaResult` object produced by a CBMA or IBMA `Estimator` to apply the correction method.
This will return an updated `MetaResult` object, with both the statistical maps from the original `MetaResult`, as well as new, corrected maps.
