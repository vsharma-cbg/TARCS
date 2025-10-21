# TARCS: Titratable Acidic Residue Conformation Suggestion
version 1.0.0, University of Helsinki

## Description
TARCS is a conformer suggestion script for titratable acidic residues in cryo-EM structures.
The purpose of this script is to generate conformers of aspartic and glutamic acid residue side chains, and based on your pKa preferences, select the ones that meet your criteria for your experiments or simulations.

TARCS follows a linear workflow, as illustrated below:

Data input &rarr; Conformer generation (MODELLER) &rarr; Dihedral and pKa calculations (VMD and PROPKA, respectively) &rarr; Filters &rarr; Clustering (DBSCAN) &rarr; Selection of conformers

## Features

* Generation of user-specified conformers of specific ASP or GLU side chains of interest
* Calculation of pKa values of proteins of interest
* Identification of pKa-dihedral clusters of ASP or GLU side chain orientation
* Conformer selection of ASP or GLU side chain based on pKa preferences

## Known issues / Future improvements
- [ ] Inclusion of dihedral preferences
- [ ] Conversion to python for better interoperability
- [ ] Use of flag system for setting up preferences
- [ ] Extension of quality control for data input
- [ ] Inclusion of .cif file format for data extraction
- [ ] Analyses of multiple residues at once (either separately or as a group)

## Download and installation
Currently, TARCS is available only for Linux systems. TARCS needs only to be downloaded to be used.
There are, however, certain dependencies that need to be met in order to function properly. Please see the **Dependencies** section for more information.

## Usage instructions
To use TARCS, execute the perl script like in this example: `$ perl tarcs.pl 7O71.pdb`

1. Move the experimental structure of interest to the **tarcs/** directory:	`$ mv 7O71.pdb {path\_to\_tarcs}/tarcs/`
2. Grant execution permissions to tarcs.pl:				`$ chmod +x tarcs.pl`
3. Execute tarcs.pl using the structure of interest:			`$ perl {path\_to\_tarcs}/tarcs/tarcs.pl {experimental\_structure\_code}.pdb`

After analysis, you should receive a list of conformers like so:
```
#	Conformer
1	1-7O71.pdb
2	56-7O71.pdb
3	24-7O71.pdb

[END MESSAGE]
Done. We hope these conformers aid you in your research. Cheerio! :)
```

## Supported systems and Dependencies

TARCS has been tested on Linux systems Ubuntu 24.04 LTS, Cubbli 24, LinuxMint 22.2 Cinnamon and Fedora Workstation 42.
Version 1.0.0 uses perl v5.40.3, tcl/tk v9.0.2, python v3.13.7 and bash v5.2.37(1)-release.

For TARCS to work, you need MODELLER and PROPKA installed, as well as VMD 1.9.3.
You can find instructions on MODELLER installation here: https://salilab.org/modeller/download\_installation.html .
You can find instructions on PROPKA installation here: https://github.com/jensengroup/propka .

Please make sure to have the following packages installed:

* numpy
* scikit-learn
* mdanalysis
* fasteners
* GridDataFormats
* joblib
* matplotlib
* mda-xdrlib
* mmtf-python
* packaging
* scipy
* threadpoolctl
* tqdm

## Authors and contact information
If you have questions regarding the code, please send an email to Georgios Kolypetris at georgios.kolypetris@helsinki.fi. If you'd like to discuss about or participate in the project, please contact Vivek Sharma at vivek.sharma@helsinki.fi.
