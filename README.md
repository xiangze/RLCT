## Reproducing generalizaiton experiments

Run sweep.py for all 32 taskids. Results are dumped to lastlayersims folder. 
To each taskid there are three files associated
+ taskid*_args.pt: contains all the arguments used in lastlayerbayesian.py
+ taskid*_results.pt: contains generalization error for each method and each sample size
+ taskid*.png: preliminary graphic, not publication pretty
Run visualize.py for all 32 taskids to produce pretty learning curves and latex tables summarizing learning coefficient and R2 fit.

The random seed was set to 43 in lastlayerbayesian.py.

### additional experiment
+ estimate_softmax_DNN.py
estimate LLC for softmax DNN with various alpha(nonlienar parameter)
+ llc_rlct_estimator_for_softmax_networks_via_power_posteriors_sgld.py
estimate_softmax_DNN using SGLD or NUTS HMC


## Committing Jupyter notebooks

To commit notebooks, first execute the following to strip all notebooks of output.

python3 -m nbconvert --ClearOutputPreprocessor.enabled=True --inplace *.ipynb **/*.ipynb

## Equation numbering in Juypter

# install
pip install jupyter_contrib_nbextensions

# enable
jupyter contrib nbextension install --user
jupyter nbextension enable equation-numbering/main

# activate
MathJax.Hub.Config({
    TeX: { equationNumbers: { autoNumber: "AMS" } }
});
