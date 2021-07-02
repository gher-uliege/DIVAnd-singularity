[![Build Status](https://github.com/gher-ulg/DIVAnd-singularity/workflows/Singularity%20Build/badge.svg)](https://github.com/gher-ulg/DIVAnd-singularity/actions?query=workflow%3A%22Singularity+Build%22)

# DIVAnd-singularity
Singularity container for DIVAnd


# Dependencies

* Install singularity: https://sylabs.io/docs/

# Building

After checking out the source, the singularity container can be build using:

```
rm -f DIVAnd.sif; sudo singularity build DIVAnd.sif Singularity
```
The first command is only needed if you already had the `.sif` file in your system.     
The _build_ operation lasts severall minutes due to the download and installation of languages and libraries.

# Download

Container images are build using GitHub actions.
Go to https://github.com/gher-ulg/DIVAnd-singularity/actions choose the lastest commit and go to artefact.
Download and unzip the image file and run with:

```bash
singularity run DIVAnd.sif
```
