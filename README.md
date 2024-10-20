# **HLADR4Pred2.0**
A computational approach to predict HLA-DRB1-04:01 binders using the sequence information of the peptides.
## Introduction
HLADR4Pred2.0 is an update of HLADR4Pred published by our group in 2004. It is developed to predict, scan, and, design the binders of HLA-Class II allele HLA-DRB1-04:01 using sequence information only. In the standalone version, extra-tree classifier based model is implemented alongwith the BLAST search, named it as hybrid approach.
HLADR4Pred2.0 is also available as web-server at https://webs.iiitd.edu.in/raghava/hladr4pred2. Please read/cite the content about the HLADR4Pred2.0 for complete information including algorithm behind the approach.
## Reference:
<li> Patiyal S, Dhall A, Kumar N, Raghava GPS (2024) HLA-DR4Pred2: an improved method for predicting HLA-DRB104:01 binders. <a href="https://doi.org/10.1016/j.ymeth.2024.10.007"><font color=blue>Methods, doi.org/10.1016/j.ymeth.2024.10.007.</font></a> </li>
<li> Bhasin M, Raghava GPS (2004) SVM based method for predicting HLA-DRB1 binding peptides in an antigen sequence. <A href="http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=pubmed&dopt=Abstract&list_uids=14960470&query_hl=1&itool=pubmed_docsum"><font color=blue>Bioinformatics 20(3): 421-3</font><a></li>
 
## PIP Installation
PIP version is also available for easy installation and usage of this tool. The following command is required to install the package 
```
pip install hladr4pred2
```
To know about the available option for the pip package, type the following command:
```
hladr4pred2 -h
```
## Standalone
The Standalone version of transfacpred is written in python3 and following libraries are necessary for the successful run:
- scikit-learn
- Pandas
- Numpy
- blastp

## Minimum USAGE
To know about the available option for the stanadlone, type the following command:
```
python hladr4pred2.py -h
```
To run the example, type the following command:
```
python3 hladr4pred2.py -i example_input.fa
```
This will predict if the submitted sequences are Binders or Non-binder. It will use other parameters by default. It will save the output in "outfile.csv" in CSV (comma seperated variables).

## Full Usage
```
usage: hladr4pred2.py [-h] 
                       [-i INPUT 
                       [-o OUTPUT]
		       [-j {1,2,3}]
		       [-t THRESHOLD]
                       [-w {9,10,11,12,13,14,15,16,17,18,19,20}]
		       [-d {1,2}]
```
```
Please provide following arguments for successful run

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Input: protein or peptide sequence(s) in FASTA format
                        or single sequence per line in single letter code
  -o OUTPUT, --output OUTPUT
                        Output: File for saving results by default outfile.csv
  -j {1,2,3}, --job {1,2,3}
                        Job Type: 1:Predict, 2: Design, 3:Scan, by default 1
  -t THRESHOLD, --threshold THRESHOLD
                        Threshold: Value between 0 to 1 by default 0.16
  -w {9,10,11,12,13,14,15,16,17,18,19,20}, --winleng {9,10,11,12,13,14,15,16,17,18,19,20}
                        Window Length: 9 to 20 (scan mode only), by default 9
  -d {1,2}, --display {1,2}
                        Display: 1:Binders only, 2: All peptides, by default 1
```

**Input File:** It allow users to provide input in the FASTA format.

**Output File:** Program will save the results in the CSV format, in case user do not provide output file name, it will be stored in "outfile.csv".

**Threshold:** User should provide threshold between 0 and 1, by default its 0.16.

**Job:** User is allowed to choose between three different modules, such as, 1 for prediction, 2 for Designing and 3 for scanning, by default its 1.

**Window length**: User can choose any pattern length between 9 and 20 in long sequences. This option is available for only scanning module.

**Display type:** This option allow users to fetch either only HLA-DRB1-04:01 binding peptides by choosing option 1 or prediction against all peptides by choosing option 2.

HLADR4Pred2.0 Package Files
=======================
It contantain following files, brief descript of these files given below

INSTALLATION                    : Installations instructions

LICENSE                         : License information

README.md                       : This file provide information about this package

model.zip                       : This zipped file contains the compressed version of model

envfile                         : This file compeises of paths for the database and blastp executable

hladr4pred2.py                  : Main python program

example_input.fa                : Example file contain peptide sequenaces in FASTA format

example_predict_output.csv      : Example output file for predict module

example_scan_output.csv         : Example output file for scan module

example_design_output.csv       : Example output file for design module
