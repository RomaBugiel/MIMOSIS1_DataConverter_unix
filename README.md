# How to run 

## General desciption 
__MIMOSIS1_DataConverter__

The software is dedicated for converting the data file .bin from MIMOSIS1 DAQ to ROOT Tree format (.root). Using ROOT TTree the data might be loaded into __MIMOSIS1_PhysicsAnalysis__ to plot S-Curves and performe basic noise analysis. 

For that moment the software is working with __FIRED DAQ__ data type, so the data format containing 2-DIM array with multiplicity of fired pixels per N frames. This format is futher called __integrated frame__ .

## GitHub
Repository can be cloned from:

__https://github.com/RomaBugiel/MIMOSIS1_DataConverter_unix.git__

## Software
* C++14, ROOT 

### Needed packages 
The software was tested on:

* ROOT 6.22/00 
* Unix: Ubuntu 20
* Doxygen: 1.8.17
* g++: 9.3.0 

## Compilation and run

### Software
> __make__ <br/>
> ./mimosis1reader

#### Configuration file

For configuration parameters list on HTLM documentation please go: Releated Pages --> config_file.cfg

#### Output
> In general the path for saving the root trees is provided via config_file.cfg.
> If not changed, one can find the outputs in: ./outputData

### Documentation

> * in main directory run: __make docs__ 
> 	* for Latex go to /doc/latex: __make__ and open __refman.pdf__
> 	* for HTLM: go to /doc/html and open __index.html__

## Scirpits

The bash script __convert_multiple_files.sh__ is provided for running data conversion of serveral files. 
The bash script is generating only config_file.cfg which is loaded in runtime, so after changes in configuration file do not need complitation.

There are four analysis parameters for which script is able to call automatic conversion (simply execute program for multiple files for which the value of parameter is changed). These analysis parameters are: run, VPULSE, VTHRESHOLD and VBACKBIAS. One can also use script for running only one file. In such a case only one number (without {}) should be placed in for-loops inside bashscript. 

## Essentail steps for running the software
* after cloning the repository --> __make__
* check if outputData directory is created in software dir. 
* edit __convert_multiple_files.sh__ . Most of the parameters might stay unchanged. One should edit (check): 
	* ranges of for-loops
	* _run
	* _row_start
	* _row_end
	* _column_start
	* _column_end
	* _in_file_path 
	* _out_tree_file_path 
	
Definitions in doc. 
