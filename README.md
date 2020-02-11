# Molecular Dynamics Structural Bioinformatics

## Introduction

Molecular dynamics simulation is the most used theoretical technique to analyze macromolecular flexibility and dynamics. Present state of the methodology is good enough to give biological insight in processes involving conformational changes in macromolecules, binding of ligands or other macromolecules, and for the generation of thermodynamically valid ensembles.

Molecular dynamics simulation codes have been optimized to be able to run efficiently even in normal computer (although supercomputers, and accelerated computers, are heavily used for larger projects). There is however a critical step: the setup of the system prior simulation. Proper setup is key to obtains biologically meaningful results. An incorrect setup may cause the simulation simply to crash, or even worse, to give apparently correct results that are completely biased.

We will prepare a simple protein for simulation to review the main steps of the process.

## Method

To ease the process, we will use a helper library (BioBB) that performs all the necessary steps automatically, while allowing to follow the details. 

There are several simulation codes available. We will use GROMACS (http://www,gromacs.org). GROMACS is free software and one of the most widely used MD simulations codes. 

## Software

Helper software: BioBB: http://mmb.irbbarcelona.org/biobb
Python environment: Conda (either anaconda or miniconda (recommended))

Simulation: GROMACS.
- From http://www.gromacs.org (version 2020)
- From bioconda Biobb packages (preferred)

Visualization: Pymol, VMD
Scripting: python, Biobb, GromacsWrapper python module, …

## Installation procedure

- Install conda software (https://docs.conda.io/en/latest/miniconda.html) if not available.
- Create a working directory ex. …/SBIO2020.
- Create a working directory for structure checking /SBIO2020/check and MD setup /SBIO2020/setup.
- Install software. Structure check.

  $ cd SBIO2020/check
  
  $ git clone --branch devel http://mmb.irbbarcelona.org/gitlab/BioExcel/structureChecking.git biobb_structure_checking
  
  $ git clone --branch devel http://mmb.irbbarcelona.org/gitlab/BioExcel/structure_manager.git biobb_structure_manager
  
  $ conda create -n biobb_check
  
  $ conda activate biobb_check
  
  $ conda install python=3.6
  
  $ conda install biopython
  
  $ conda install psutil
  
  $ conda install -c salilab modeller
  
  $ export PYTHONPATH=biobb_structure_checking:biobb_structure_manager
  
  Run check structure program as:

  $ biobb_structure_checking/bin/check_structure
 
A guide for available commands can be obtained with biobb_structure_checking/bin/check_structure commands.

Modeller software requires registration (free) to get the appropriate license key. Modeller is required to build missing backbone residues.


