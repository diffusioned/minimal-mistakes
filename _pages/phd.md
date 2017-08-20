---
permalink: /phd/
---

## PhD Thesis ##

### History ###

My first task as a new PhD student was to investigate why a particular Monte Carlo simulation was having problems.  The simulation involved fitting artificial noisy signals with a biexponential model using a nonlinear regression algorithm in MATLAB.  This work turned out to form the basis of my PhD thesis/dissertation that I completed four years later in 2016.  The title of this thesis is **Reliability and Uncertainty in Diffusion MRI Modelling**.  My thesis is freely available on the University of Sydney online repository [here](http://hdl.handle.net/2123/16060).

### Abstract ###

Current Diffusion MRI studies often utilise more complex models beyond the single exponential decay model used in clinical standards. As this thesis shows, however, two of these models, biexponential and kurtosis, experience mathematical, ill-conditioning issues that can arise when used with regression algorithms, causing extreme bias and/or variance in the parameter estimates. Using simulated noisy data measurements from known truth, the magnitude of the bias and variance was shown to vary based on signal parameters as well as SNR, and increasing the SNR did not reduce this uncertainty for all data. Parameter estimate reliability could not be assessed from a single regression fit in all cases unless bootstrap resampling was performed, in which case measurements with high parameter estimate uncertainty were successfully identified. Prior to data analysis, current studies may use information criteria or cross-validation model selection methods to establish the best model to assess a specific tissue condition. While the best selection method to use is currently unclear in the literature, when testing simulated data in this thesis, no model selection method performed more reliably than the others and these methods were merely biased toward either simpler or more complex models. When a specific model was used to generate simulated noisy data, no model selection method selected this true model for all signals, and the ability of these methods to select the true model also varied depending on the true signal parameters. The results from these simulated data analyses were applied to ex vivo data from excised prostate tissue, and both information criteria measures and bootstrap sample distributions were able to identify image voxels whose parameter estimates had likely reliability issues. Removing these voxels from analysis improved sample variance of the parameter estimates.

### Code ###

The code that created almost all of the figures in my thesis is available on my GitHub repository [here](https://github.com/diffusioned/MATLAB-Thesis-Code).  

### Acknowledgements ###

Funding for my PhD research was largely provided by winning an [Australian Postgraduate Award](https://www.education.gov.au/australian-postgraduate-awards), which provided me with 3 and a half years of funding for full-time postgraduate study.
