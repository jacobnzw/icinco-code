### Bayes-Hermite Kalman Filters/Smoothers
This repo contains accompanying `Python 2` source code used for generating tables and a figure in the paper
> J. Prüher and M. Šimandl, *Bayesian Quadrature in Nonlinear Filtering,*
Informatics in Control, Automation and Robotics (ICINCO), 2015 12th International Conference on, 2015

All the Gaussian nonlinear sigma-point filters use some sort of numerical integration procedure to approximate moments of a Gaussian random variable undergoing nonlinear transformation. All the well-known sigma-point filters such as, UKF, CKF and GHKF, rely on a classical numerical quadrature formulas which are able to approximate the integral with zero error only if the nonlienearity is a polynomial. This is however rarely the case in practical situations, thus any quadrature ends up making errors which should be accounted for in the filering algorithm. The filters based on classical quadratures simply sweep this fact under the rug and pretend it does not exist.

In the paper, we design a Bayes-Hermite Kalman Filter (BHKF) which is based on alternative approach to numerical integration called Bayesian quadrature (BQ). BQ views numerical integration as statistical inference problem, where the integral is seen as a random variable. Variance of the integral then serves as a model of the integration error which can be used to inform the filtering algorithm about integration errors.

The experiment in the paper compares the root mean square error (RMSE) and non-credibility index (NCI) performance of the BHKF and the prominent sigma-point filters, such as CKF, UKF and GHKF. BHKF is shown to outperform all classical quadrature-based sigma-point filters in terms of both RMSE and NCI.

The script `icinco_demo.py` contains two main functions:
  * `rmse_nci_tables()`: generates the RMSE and NCI tables comparing BHKF filter performance with classical sigma-point filters.
  * `hypers_demo()`: generates figure showing dependece of filter RMSE and NCI performance on the lengthscale kernel hyper-parameters.

Launching the script by
```
python icinco_demo.py
```
will run both functions, print the tables in terminal and plot the figure.
