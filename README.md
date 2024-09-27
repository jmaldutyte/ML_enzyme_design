# Machine Learning enzyme design assignment

I. The task.

readme_task.pdf explains the task in detail, including reference papers and data files available for using. In short, the given dataset contains 2854 single-point mutants of Ube2i SUMO conjugase, with measured fitness scores. This and biophysical features can be found in the features.csv file. The goal was to using only 96 samples, train/fit a model which can predict fitness of the rest of the data set, using all information availabls. This also includes amino acid encodings (not provided here due to large size), Ube2i multiple sequence alignment (ube2i_msa.a3m).

II. The solution, guide to navigating files:

1) The solution is provided in 4 Jupyter notebooks in Python. The first 3 look individually into the three data sources I used: biophysical features, MSA and amino acid representations. The last notebook integrates the three data sources into a final model. The work progresses from first to fourth notebooks.
2) Notebooks 2 and 3 generate files which are used in the notebooks that follow.

