# robstat
Stata module to estimate robust univariate statistics

`robstat` estimates various classic and robust measures of location, scale,
skewness, and kurtosis, and, optionally, performs robust tests for normality.

To install `robstat` from the SSC Archive, type

    . ssc install robstat, replace

in Stata. Stata version 11 or newer is required. Furthermore, `moremata` is
required. To install `moremata` from the SSC Archive, type

    . ssc install moremata, replace

---

Installation from GitHub:

    . net install robstat, replace from(https://raw.githubusercontent.com/benjann/robstat/main/)
    . net install moremata, replace from(https://raw.githubusercontent.com/benjann/moremata/master/)

---

Main changes:

    15mar2025 (version 1.0.5)
    - standard errors were wrong if option over() was specified since the influence
      functions were not rescaled in relation to subgroup size; this is fixed

    20dec2020 (version 1.0.4)
    - refined computations of influence functions such that they have a mean exactly
      equal to zero for all statistics (apart from roundoff error); results for
      standard errors and confidence intervals are now slightly different for some
      of the statistics due to these changes
    - Huber, biweight, and S now computed using mm_mloc() and mm_mscale() from
      moremata
    - pairwise HL, Qn, and [L/R]MC now computed using mm_hl(), mm_qn(), and mm_mc()
      from moremata
    - results for alpha-trimmed mean could be unstable in case of weights; this is fixed
    - skewness and kurtosis did not allow iweights; this is fixed
    
    10aug2020 (version 1.0.3)
    - now using mm_density() from moremata instead of -kdens-
    - option -adaptive(0)- now allowed
    
    21feb2019 (version 1.0.1)
    - new option -cilog- to use log-transformed CIs for scale statistics
    - influence function (and standard error) of M-estimate of scale was valid 
      only for symmetric distributions; this is fixed
    
    24aug2018 (version 1.0.0)
    - published on SCC
