### Text-mining neurosynth text corpus using Deep Boltzmann Machines
#
# 
# 
#

Subdirectories/files are as follows:
 - Code: contains all code.
 - Data: will contain preprocessed data (note this is not included due to storage constraints)
 - Data/Raw: folder to store all collected abstracts (kept empty to due to storage contraints)
 - Weights: contains fitted RBM/DBM models (only final DBM model stored here atm)

 In order to reproce results or train DBM on neurosynth abstract corpus run the following scripts:
 	1. collectPaperText.py: collect abstract text, cleans text and stores in incidence matrix
 	2. PretrainLayer.py: selects architecture of each layer by comparing log-likelihood on validation dataset. Pretrains RBMs for each layer
 	3. FineTuneDBM.py: applies DBM training algorithm to pretrained layers

Note that step 1 can be skipped (cleaned data is provided in data folder).
The final DBM employed is also saved in the Weights folder ("DBM_50_50_Full.p")

The following (non-standard) libraries are required:
 - biopython.org - used to collect abstracts from PUBMED API
 - textmining (http://www.christianpeccei.com/textmining/) - used to build term incidence matrix
 - nltk (http://www.nltk.org/) - used for stopwords 
Note that these library are only required for the text collection and cleaning (collectPaperText.py) and can be ignored if this step is skipped