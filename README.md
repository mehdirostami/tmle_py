# tmle_py
Running the tmle procedure to estimate the causal parameter 

We import R codes to python and run tmle.
tmle uses a super learner (an ensemble of machine learning methods) to estimate counterfactuals, and propensity score
and estimate the causal parameter. The initial estimate is biased. So through a series of adjustments, the method tries
to reduce the biasedness in the estimate while controlling for the variance of the estimator. 

This is known to be doubly robust as the final results are valid even if one (not both) of the models are wrong:
1) The modeling of the outcome (which gives the counterfactuals) 
2) The modeling of the exposure or treatment.

This method is is often successful since it's likely that we specify one of the above models correctly.

In the tmle_r2py.md attached, we simulate data and set the treatment effect to be -1 and we hope that tmle can recover this
parameter. The last line of the code shows the miracle of this method.
