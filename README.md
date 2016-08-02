# Necrobiome data and code

These materials are supplementary to the paper _A Computational Framework for Using the Postmortem Skin Microbiome to Estimate the Postmortem Interval_ by Hunter Johnson, Donovan Trinidad, Stephania Guzman, Zenab Khan, James Parziale, Jennifer DeBruyn, and Nathan Lents.  That paper provides detailed information about the project from which these data and code originate.  

Very briefly, this code performs regression analysis on data which relate to changes in the necrobiome human cadavers, with the aim of determining the post-mortem interval of a cadaver from the necrobiome found in the nose and ear.

Included in this repository are the following directories:

1. `raw_data`
2. `processed_data`
3. `code`

The `raw_data` directory contains files for absolute abundance of several types of microbiota sampled from decomposing cadavers, as well as corresponding measurements of accumulated degree days (ADD) to which the cadavers were exposed.  The microbiome data is contained in files of the form _t\_Level\_Aggregate\_Counts.csv_, where _t_ denotes a taxon in the following list: kingdom, phylum, class, order, genus, species.  These data are linked, via the ``sample number'' to a file _legend.csv_, where the associated ADD and other information can be found. The data is divided into two directories depending on whether it is from the ear or the nose.

The `processed_data` directory contains most of the same information contained in the `raw_data` directory, but in a form that is more easily readable by machine.  There are two types of files in this directory:  files with names beginning with _X_ and files with names beginning with _y_.  The files of the _X_ type are based on the aggregate counts from the `raw_data` directory, whereas the _y_ type files are based on the legend file.  

The form of the _X_ files is: `X_(taxon)_(curated/noncurated)_(ear/nose/joint)`. The "joint" files are roughly a concatenation of both ear and nose data.  For each choice of ear, nose, or joint there is an associated _y_ type file.  The rows of the _X_ file and an associated _y_ file are for the same sample.  Thus, if file A is, say, for the ear, then the ith row of A is a necrobiome sample from a cadaver taken at an ADD corresponding to the ith row of `y_EAR`.   

The `code` directory contains the salient part of the code written for this project, namely the code that performs the regression.  The file `DataRegressor.ipynb` is a Python notebook file, in particular a Jupyter notebook file.  Information on configuring a Jupyter IDE can be found [here](https://jupyter.org/).  The code requires the machine learning library [scikit-learn](http://scikit-learn.org/stable/) version 0.17.  

Please see the file `LICENSE.md` for usage rights.  
Please send correspondence to hujohnson@jjay.cuny.edu or nlents@jjay.cuny.edu.  
For any use of this data the authors would appreciate a citation of the associated paper.
