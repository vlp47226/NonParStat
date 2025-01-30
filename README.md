# Nonparametric Tests

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip) 
[![Build Status](https://travis-ci.com/GrzegorzMika/NonParStat.svg?branch=master)](https://travis-ci.com/GrzegorzMika/NonParStat)
[![codecov](https://codecov.io/gh/GrzegorzMika/NonParStat/branch/master/graph/badge.svg)](https://codecov.io/gh/GrzegorzMika/NonParStat)

<a href="https://www.buymeacoffee.com/grzegorzm" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

NonParStat is a python module containing various non parametric statistical tests. The name NonParStat is a shortcut from Non-Parametric Statistics. The aim of the package is to extend the functionalities provided in the `scipy` package in the scope of statistical testing. 

List of available tests:

1. Scale-location Cucconi test (two- and multisample version)
2. Scale-location Podgor-Gastwirth test

To generate the documentation run `pdoc3 --html --force  -o'docs' nonparstat/`.

Example Usage:
'''python
import numpy as np
from NonParStat.nonparstat import Cucconi
np.random.seed(987654321) # set random seed to get the same result
sample_a = sample_b = np.random.normal(loc=0, scale=1, size=100)
test_result = Cucconi.cucconi_test(sample_a, sample_b, replications=10000)
print(test_result) #-> CucconiResult(statistic=3.7763314663244195e-08, pvalue=1.0)

sample_a = np.random.normal(loc=0, scale=1, size=100)
sample_b = np.random.normal(loc=10, scale=10, size=100)
test_result = cucconi_test(sample_a, sample_b, method='permutation')
print(test_result) #-> CucconiResult(statistic=2.62372293956099, pvalue=0.000999000999000999)

sample_a = sample_b = np.random.normal(loc=0, scale=1, size=100)
test_result = podgor_gastwirth_test(sample_a, sample_b)
print(test_result) #->Podgor_GastwirthResult(statistic=-1.9596768652263527e-13, pvalue=1.0)
'''
