# <img src="images/icon.jpg" alt="Icon" width="20" height="20" /> HySort: Hydrogenase subtype classifier

HySort is used to identify the potential hydrogenases in a genome followed by subtype classification. It's built upon hidden markov model search for potential hydrogenases and probability calculation based on Gaussian mixture models with the new embeddings from constrative learning of the protein language model ESM-C.

# Installation
## Requirements before installation
Python3 is required for the installation. Becasue `hmmscan` and `seqkit` are called by HySort, please make sure to have them installed beforehand and make them accessible system-wide.

## Install HySort with `pip`
Installation of HySort is straightforward and trivial.
Step1: clone the github repo:
```
git clone
cd
```
Step2: create a new python environment for installation of required packages:
```
pip -n
pip install -r requirements.txt
```

# Usage
You can check the help page with:
```
./hysort -h
```
HySort accepts the input as a single protein file, (e.g. coding sequences from a genome) or a folder containing multiple protein files:
```
# single file
./hysort --input_file tests/test.fa
# multiple files
./hysort --protein_dir tests --file_extension fa
```
You can also use GPU for accelaration:
```
./hysort --input_file tests/test.fa --device cuda
./hysort --input_file tests/test.fa --device cuda:0
```
