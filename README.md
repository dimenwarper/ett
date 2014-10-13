gett
====

The genotype, expression, and trait toolkit

Main usage is through the gett.py script, e.g. as follows

python gett.py datasets/magnet/full_exp_cases.txt datasets/magnet/full_exp_controls.txt --correctcovariates datasets/magnet/all_sample_covariates.txt datasets/magnet/all_sample_covariates.txt --zscores --selectbyvariance 0.2 --clip --savesteps


The line above will take two trait matrices (rows are traits with first field being trait name e.g. gene names and gene expression values and columns are samples [with a header]) contained in full_exp_cases.txt and full_exp_controls.txt and will correct the values for the covariates using robust linear regression (default) included in all_sample_covariates.txt (in the same format as trait matrices) and will then take only the top 20% traits with most variance and then normalize trait-wise using z-scores. After that, the CLIP analysis will be run (with the --clip flag, you can run other analyses with e.g. --jgl, --pcor, --cor, etc.). The --savesteps flag will save intermediary files (e.g. one file for the covariance-corrected, then normalized, etc.).
