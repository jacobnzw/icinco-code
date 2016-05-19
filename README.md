### Bayes-Hermite Kalman Filters/Smoothers
This repo contains accompanying `Python 2` source code used for generating tables and a figure in the paper
> J. Prüher and M. Šimandl, *Bayesian Quadrature in Nonlinear Filtering,* 
Informatics in Control, Automation and Robotics (ICINCO), 2015 12th International Conference on, 2015

All the Gaussian nonlinear sigma-point filters use some sort of numerical integration procedure to approximate moments of a Gaussian random variable undergoing nonlinear transformation.
In the paper, we propose utilization of the integral variance, which arises from imperfect approximations of the moment integrals by numerical quadrature rules. Bayesian quadrature (BQ) is an exciting alternative view of numerical integration that enables us to explicitly acknowledge the fact that our moment integral quadrature approximations are not perfect. Classical quadratures simply sweep this fact under the rug and pretend it does not exist.

The experiment in the paper compares the root mean square error (RMSE) and non-credibility index (NCI) performance of the BHKF, which is nonliear sigma-point filter based on BQ, and the prominent sigma-point filters (CKF, UKF, GHKF) based on classical quadratures. BHKF is shown to outperform all classical quadrature-based sigma-point filters in terms of all criteria.

The script `icinco_demo.py` contains two main functions:
  * `rmse_nci_tables()`: generates the RMSE and NCI tables comparing BHKF filter performance with classical sigma-point filters.
  * `hypers_demo()`: generates figure showing dependece of filter RMSE and NCI performance on the lengthscale kernel hyper-parameters.

Launching the script by 
```
python icinco_demo.py
```
will run both functions, prints the tables in terminal and plots the figure.
