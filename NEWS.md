# msaenet 3.0 (2018-12-14)

## New Features

- Added a new argument `penalty.factor.init` to support customized penalty factor applied to each coefficient in the initial estimation step. This is useful for incorporating prior information about variable weights, for example, emphasizing specific clinical variables. We thank Xin Wang from University of Michigan for this feedback [[#4](https://github.com/road2stat/msaenet/issues/4)].

# msaenet 2.9 (2018-05-13)

## Improvements

- New URL for the documentation website: https://nanx.me/msaenet/.

# msaenet 2.8 (2018-01-05)

## New Features

- Added a Cleveland dot plot option `type = "dotplot"` in `plot.msaenet()`. This plot offers a direct visualization of the model coefficients at the optimal step.

# msaenet 2.7 (2017-09-24)

## Bug Fixes

- Fixed the missing arguments issue when `init = "ridge"`.

# msaenet 2.6 (2017-04-23)

## Improvements

- Added two arguments `lower.limits` and `upper.limits` to support coefficient constraints in `aenet()` and `msaenet()` [[#1](https://github.com/road2stat/msaenet/issues/1)].

# msaenet 2.5 (2017-03-24)

## Improvements

- Better code indentation style.
- Update gallery images in `README.md`.

# msaenet 2.4 (2017-02-17)

## Improvements

- Improved graphical details for coefficient path plots, following the general graphic style in the ESL (*The Elements of Statistical Learning*) book.
- More options available in `plot.msaenet()` for extra flexibility: it is now possible to set important properties of the label appearance such as position, offset, font size, and axis titles via the new arguments `label.pos`, `label.offset`, `label.cex`, `xlab`, and `ylab`.

# msaenet 2.3 (2017-02-09)

## Improvements

- Reduced model saturation cases and improved speed at the initialization step for MCP-net and SCAD-net based models when `init = "ridge"`, by using the ridge estimation implementation from `glmnet`. As a benefit, we now have a more aligned baseline for the comparison between elastic-net based models and MCP-net/SCAD-net based models when `init = "ridge"`.
- Style improvements in code and examples: reduced whitespace with a new formatting scheme.

# msaenet 2.2 (2017-02-02)

## New Features

- Added BIC, EBIC, and AIC in addition to k-fold cross-validation for model selection.
- Added new arguments `tune` and `tune.nsteps` to controls this for selecting the optimal model for each step, and the optimal model among all steps (i.e. the optimal step).
- Added arguments `ebic.gamma` and `ebic.gamma.nsteps` to control the EBIC tuning parameter, if `ebic` is specified by `tune` or `tune.nsteps`.
- Redesigned plot function: now supports two types of plots (coefficient path, screeplot of the optimal step selection criterion), optimal step highlighting, variable labeling, and color palette customization. See `?plot.msaenet` for details.

## Improvements

- Renamed previous argument `gamma` (scaling factor for adaptive weights) to `scale` to avoid possible confusion.
- Reset the default values of candidate concavity parameter `gammas` to be 3.7 for SCAD-net and 3 for MCP-net.
- Unified the supported model `family` in all model types to be `"gaussian"`, `"binomial"`, `"poisson"`, and `"cox"`.

# msaenet 2.1 (2017-01-15)

## New Features

- Added functions `msaenet.sim.binomial()`, `msaenet.sim.poisson()`, `msaenet.sim.cox()` to generate simulation data for logistic, Poisson, and Cox regression models.
- Added function `msaenet.fn()` for computing the number of false negative selections in msaenet models.
- Added function `msaenet.mse()` for computing mean squared error (MSE).

## Improvements

- Speed improvements in `msaenet.sim.gaussian()` by more vectorization when generating correlation matrices.
- Added parameters `max.iter` and `epsilon` for MCP-net and SCAD-net related functions to have finer control over convergence criterion. By default, `max.iter = 10000` and `epsilon = 1e-4`.

# msaenet 2.0 (2017-01-05)

## New Features

- Added support for adaptive MCP-net. See `?amnet` for details.
- Added support for adaptive SCAD-net. See `?asnet` for details.
- Added support for multi-step adaptive MCP-net (MSAMNet). See `?msamnet` for details.
- Added support for multi-step adaptive SCAD-net (MSASNet). See `?msasnet` for details.
- Added `msaenet.nzv.all()` for displaying the indices of non-zero variables in all adaptive estimation steps.

## Improvements

- More flexible `predict.msaenet` method allowing users to specify prediction type.

# msaenet 1.1 (2016-12-28)

## New Features

- Added method `coef` for extracting model coefficients.
  See `?coef.msaenet` for details.

## Improvements

- New documentation website generated by pkgdown,
  with a full set of function documentation and vignettes available.
- Added Windows continuous integration support using AppVeyor.

# msaenet 1.0 (2016-09-20)

## New Features

- Initial version of the msaenet package
