[![PyPI version](https://badge.fury.io/py/tslearn.svg)](https://badge.fury.io/py/tslearn)
[![Documentation Status](https://readthedocs.org/projects/tslearn/badge/?version=latest)](http://tslearn.readthedocs.io/en/latest/?badge=latest)
[![Build Status](https://travis-ci.org/rtavenar/tslearn.svg?branch=master)](https://travis-ci.org/rtavenar/tslearn)
[![Code Climate](https://codeclimate.com/github/rtavenar/tslearn/badges/gpa.svg)](https://codeclimate.com/github/rtavenar/tslearn)
[![Test Coverage](https://codeclimate.com/github/rtavenar/tslearn/badges/coverage.svg)](https://codeclimate.com/github/rtavenar/tslearn/coverage)

`tslearn` is a Python package that provides machine learning tools for the analysis of time series.
This package builds on `scikit-learn`, `numpy` and `scipy` libraries.

If you would like to contribute to `tslearn`, please have a look at [our contribution guidelines](CONTRIBUTING.md).

# Dependencies

```
Cython
numpy
scipy
scikit-learn
```

If you plan to use the `shapelets` module, `keras` should also be installed.

# Installation

## Using PyPI

The easiest way to install `tslearn` is probably via `pip`:
```bash
pip install tslearn
```

## Using latest github-hosted version

If you want to get `tslearn`'s latest version, you can `git clone` the repository hosted at github:
```bash
git clone https://github.com/rtavenar/tslearn.git
```

Then, you should run the following command for Cython code to compile:
```bash
python setup.py build_ext --inplace
```

Also, for the whole package to run properly, its base directory should be appended to your Python path.

# Documentation and API reference

The documentation, including a gallery of examples, is hosted at [readthedocs](http://tslearn.readthedocs.io/en/latest/index.html).

# Already available

* A `generators` module provides Random Walks generators
* A `datasets` module provides access to the famous UCR/UEA datasets through the `UCR_UEA_datasets` class 
* A `preprocessing` module provides standard time series scalers
* A `metrics` module provides:
  * Dynamic Time Warping (DTW) (with Sakoe-Chiba band and Itakura parallelogram variants)
  * LB_Keogh
  * Global Alignment Kernel
  * Soft-DTW from Cuturi and Blondel
* A `neighbors` module includes nearest neighbor algorithms to be used with time series
* A `clustering` module includes the following time series clustering algorithms:
  * Standard Euclidean k-means (with adequate array reshaping done for you)
    * Based on `tslearn.barycenters`
  * DBA k-means from Petitjean _et al._
    * Based on `tslearn.barycenters` that offers DBA facility that could be used for other applications than just 
    k-means
  * Global Alignment kernel k-means
  * KShape clustering from Paparizzos and Gravano
  * Soft-DTW k-means from Cuturi and Blondel
    * Based on `tslearn.barycenters` that offers Soft-DTW barycenter computation
* A `shapelets` module includes an efficient implementation of the Learning Time-Series method from Grabocka _et al._
  * **Warning:** to use the shapelets module, an extra dependency is required: `keras`
* A `piecewise` module includes standard time series transformations, as well as the corresponding distances:
  * Piecewise Aggregate Approximation (PAA)
  * Symbolic Aggregate approXimation (SAX)
  * 1d-Symbolic Aggregate approXimation (1d-SAX)

# TODO list

Have a look [there](https://github.com/rtavenar/tslearn/issues?utf8=✓&q=is%3Aissue%20is%3Aopen%20label%3A%22new%20feature%22%20) for a list of suggested features.
**If you want other ML methods for time series to be added to this TODO list, do not hesitate to open an issue!** See [our contribution guidelines](CONTRIBUTING.md) for more information about how to proceed.

# Acknowledgments

Author would like to thank Mathieu Blondel for providing code for 
[Kernel k-means](https://gist.github.com/mblondel/6230787) and [Soft-DTW](https://github.com/mblondel/soft-dtw) (both 
distributed under BSD license) that is used in the clustering module of this library.
