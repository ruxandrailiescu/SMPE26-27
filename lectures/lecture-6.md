lecture-6
================
Ruxandra Iliescu
2026-11-19

# Estimation - how to get information from samples

## The problem

- CSMA family (WiFi): typical random access protocol to a common channel
- async access to channel and sending messages
- every agent waits a random amount of time on an interval before
  sending the message (if a collision exists)
- increase the size of the interval if you encounter a collision (e.g.,
  double the size of the interval)
- how to choose the size of the interval?
- test the protocol on device to see it respects properties: uniform
  distrib, doubling of interval
- experiment: (add drawing)
- estimation + decision

## Estimation

- how could I_0 be estimated ? X_1, X_2 … X_n, … S_n/n = 1/n sum over i
  of X_i
- in the limit, S_n/n is converging to theta/2, for X in \[0, theta\]
- another option: get rid of outliers, take the max (second estimator).
  max over i of X_i
- how can we compare which is better?

## Stochastic model

- what could be said on probability law F from the observations {x_1, …
  , x_n}?
- parametric estimation: distribution is known (uniform) and unknown
  parameter theta
- nonparametric estimation: the shape of the law is unknown and some
  parameters are under study (expectation, variance, moments,
  distribution, …); we do not have a model
- cdf and pdf of max X_i
- biased estimator of theta; correction of bias by multiplying by
  (n+1)/n; unbiasing the estimator
- in real systems, decisions are made based on few measurements (so
  consistent estimators may not be sufficient)
- what is the risk of this estimator? it is the variance of the
  (estimator - theta): E\[T_n - theta\]^2
- it is the dispersion of the estimator around the real value; two
  parts: variance of the estimator and impact of bias
- we want the best concentration around the real value
- (n+1)/n max X_i -\> theta^2/n(n+2)
- (2/n) sum X_i -\> theta^2/3n
- the first estimator concentrates better around the distribution
- see more on concentration related to CLT and 1/sqrt(n) factor
- what about other estimators?
- here it was simple because we wanted to estimate a bound of the
  uniform distribution, but usually it is harder to construct estimators
  (e.g., correlation between variables)

## Regression and linear regression

- log of computing power (y) and years (x) - linear dependency (in
  log-scale?)
- big noise: find another variable that explains the noise
- Gauss-Markov theorem
- why would an arbitrary linear combination of the variables lead to a
  more difficult closed-form formula? don’t we derivate wrt beta, so
  it’s still linear and the x’s go in the matrix
- polynomial regression
- how to check homoscedastic errors in higher dimensions?
- residuals are white noise (if not, the model is not normal/Gaussian) -
  aren’t those the errors that should be centered around 0?
