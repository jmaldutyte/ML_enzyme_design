# Machine Learning enzyme design assignment

I. The task.

In short, the given dataset contains 2854 single-point mutants of Ube2i SUMO conjugase, with measured fitness scores. Additionally, 20 biophysical features were provided for each mutant. The goal was to using only 96 samples, train/fit a model which can predict fitness of the rest of the data set, using all information available. This also includes amino acid encodings and a Ube2i multiple sequence alignment (MSA). Model performance needs to be evaluated using Spearman's correlation.

II. The solution, guide to navigating files.

1) The solution is provided in 4 Jupyter notebooks in Python. The first 3 look individually into the three data sources I used: biophysical features, MSA and amino acid representations. The last notebook integrates the three data sources into a final model. The work progresses from first to fourth notebooks.
2) Notebooks 2 and 3 generate files which are used in the notebooks that follow.
3) Detailed assignment write-up can be found in the "Assignment_write-up_JM.pdf"

Choice of model:

According to Biswas et al. (2021), if aa representations are indeed semantically-rich, fairly simple models, such as linear regression variations, could be used to predict protein function. I therefore focused on using ridge regression (RR) and random forest regression (RFR) (for potentially better capturing non-linear relationships) from scikit-learn library.  Even though a preliminary convolutional neural network (CNN) and support vector machine (SVM) were tested, these approaches was not further pursued due to poor initial performance and the low sample restraint (n=96) which doesnot suit deep learning approaches.

III. Conclusions.

The best performing model when all the given data was used in combination was Ridge Regression. The model achieved Spearman's correlation of 0.508. A large limitation for the model's performance is likely the fitness readout for the mutant proteins. As opposed to cell lethality, it would be more useful to narrow this readout down to Ube2i interaction with a single or a set of protein interactors, i.e. to focus on enhancing a specific function.

Other things to try could be: 
- More complex types of models for handling non-linearity, e.g. bettertuned SVM
- Ensemble of models: use a variety of different models and average them
- Larger size of training data increases model accuracy. E.g. using 50% of the given data, the model reaches R2=0.358 and ρ=0.65. Further sampling optimization.
- Use a different Protein Language Model (PLM) to encode amino acids, such as MSA Transformer or UniRep (it was not provided in the task how aa encoding was done). Alternatively, PLM used to encode aas could be trained/tailored on a collection of enzymes in the ubiquitin/SUMO and similar pathways, in order to focus its learning on enzyme functionality in the context of interacting proteins.
