[![Build Status](https://github.com/gher-ulg/DIVAnd-singularity/workflows/Singularity%20Build/badge.svg)](https://github.com/gher-ulg/DIVAnd-singularity/actions?query=workflow%3A%22Singularity+Build%22) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7014264.svg)](https://doi.org/10.5281/zenodo.7014264) ![GitHub top language](https://img.shields.io/github/languages/top/gher-ulg/DIVAnd-singularity)


# DIVAnd-singularity
Singularity container for `DIVAnd`, the interpolation tool available at https://github.com/gher-ulg/DIVAnd.jl.

The container installs Julia, DIVAnd and the required Julia packages.

## Dependencies

* Install singularity: https://sylabs.io/docs/

## Building

After checking out the source, the singularity container can be build using:

```bash
rm -f DIVAnd.sif; sudo singularity build DIVAnd.sif Singularity
```
The first command is only needed if you already had the `.sif` file in your system.     
The _build_ operation lasts severall minutes due to the download and installation of languages and libraries.

## Download

There are two possibilities to get the container

#### 1. From the GitHub _actions_
- go to https://github.com/gher-ulg/DIVAnd-singularity/actions,
- choose the lastest commit,
- go to artefact,
- download and unzip the image file.              
            
#### 2. From the Sylabs reposity containers
```bash
singularity pull --arch amd64 library://gher-uliege/divand/divand-singularity:v0-1-0
```

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
(where `my_script.jl` has to be substitued by the correct file).


