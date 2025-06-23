[![Build Status](https://github.com/gher-uliege/DIVAnd-singularity/workflows/Singularity%20Build/badge.svg)](https://github.com/gher-uliege/DIVAnd-singularity/actions?query=workflow%3A%22Singularity+Build%22) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7014264.svg)](https://doi.org/10.5281/zenodo.7014264) ![GitHub top language](https://img.shields.io/github/languages/top/gher-uliege/DIVAnd-singularity)      
![GitHub issues](https://img.shields.io/github/issues/gher-uliege/DIVAnd-singularity) ![GitHub all releases](https://img.shields.io/github/downloads/gher-uliege/DIVAnd-singularity/total) ![GitHub contributors](https://img.shields.io/github/contributors/gher-uliege/DIVAnd-singularity) ![GitHub last commit](https://img.shields.io/github/last-commit/gher-uliege/DIVAnd-singularity)      
[![Static Badge](https://img.shields.io/badge/Project-PHIDIAS-blue)](https://www.phidias-hpc.eu/)


# DIVAnd-singularity
Singularity container for `DIVAnd`, the interpolation tool (https://github.com/gher-uliege/DIVAnd.jl).

The container installs the last stable release of [`Julia`](https://julialang.org/), `DIVAnd` and other required Julia packages.

## Dependencies

* Install singularity: https://sylabs.io/docs/

## Building

After checking out the source, the singularity container is build using:

```bash
rm -f DIVAnd.sif; sudo singularity build DIVAnd.sif Singularity
```
The first command is only needed if you already had the `.sif` file in your system.     
The _build_ operation lasts severall minutes due to the download and installation of languages and libraries.

## Download

### From the GitHub _actions_
- go to https://github.com/gher-uliege/DIVAnd-singularity/actions,
- choose the lastest commit,
- go to artefact,
- download and unzip the image file.   
- ![singularity_artefact](https://user-images.githubusercontent.com/11868914/189079405-b156f584-1992-46ce-9ac5-0d60f57c7d42.png)

## Running the container

There are two ways to run the container:

#### 1. Without specifying a Julia script
```bash
singularity run DIVAnd.sif
``` 
This gives access to a Julia terminal, where commands and scripts can be executed.
#### 2. By specifying the script to be run
```bash
singularity run DIVAnd.sif my_script.jl
``` 
(where `my_script.jl` has to be substitued by the correct file name).

## Acknowledgements

The development of this container has been made possible thanks to [PHIDIAS](https://www.phidias-hpc.eu/) project (2019-2022).

The PHIDIAS project has received funding from the European Union's Connecting Europe Facility under grant agreement n° INEA/CEF/ICT/A2018/1810854. 


