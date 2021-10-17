# When are Deep Networks really better than Decision Forests at small sample sizes, and how?

[![arXiv](https://img.shields.io/badge/arXiv-2108.13637-red.svg?style=flat)](https://arxiv.org/abs/2108.13637)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![License](https://img.shields.io/badge/License-MIT-blue)](https://opensource.org/licenses/MIT)

**This is preliminary work. More details will be available.**

## Abstract

Deep networks and decision forests (such as random forests and gradient boosted trees) are the leading machine learning methods for structured and tabular data, respectively. Many papers have empirically compared large numbers of classifiers on one or two different domains (e.g., on 100 different tabular data settings). However, a careful conceptual and empirical comparison of these two strategies using the most contemporary best practices has yet to be performed. Conceptually, we illustrate that both can be profitably viewed as ''partition and vote'' schemes. Specifically, the representation space that they both learn is a *partitioning* of feature space into a union of convex polytopes. For inference, each decides on the basis of *votes* from the activated nodes. This formulation allows for a unified basic understanding of the relationship between these methods. Empirically, we compare these two strategies on hundreds of tabular data settings, as well as several vision and auditory settings. Our focus is on datasets with at most 10,000 samples, which represent a large fraction of scientific and biomedical datasets. In general, we found forests to excel at tabular and structured data (vision and audition) with small sample sizes, whereas deep nets performed better on structured data with larger sample sizes. This suggests that further gains in both scenarios may be realized via further combining aspects of forests and networks. We will continue revising this technical report in the coming months with updated results.

## Replicate

You can manually download the latest benchmark code by cloning the repository:

```
git clone https://github.com/neurodata/rf-dn-paper
cd rf-dn-paper
```

To replicate the benchmarks, you can install the required packages with specified versions:

```
pip install -r requirements.txt
```

For vision benchmarks, remember to specify the class number:

```
python cifar_10.py -m 3
```

For auditory benchmarks, remember to specify both the class number and the feature type:

```
python fsdd.py -m 3 -f spectrogram
```

In addition, the FSDD [dataset](https://github.com/Jakobovski/free-spoken-digit-dataset/releases/tag/v1.0.10) needs to be downloaded locally.
