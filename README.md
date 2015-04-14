# Plink

[![dockeri.co](http://dockeri.co/image/GELOG/plink)](https://registry.hub.docker.com/GELOG/plink)

[![stars](https://img.shields.io/github/stars/GELOG/plink.svg) 
![forks](https://img.shields.io/github/forks/GELOG/plink.svg) 
![issues](https://img.shields.io/github/issues/GELOG/plink.svg)
](https://github.com/GELOG/plink)


## Supported tags and respective `Dockerfile` links

- [`1.07-bin`, `latest` _(plink-1.07-bin/docker/Dockerfile)_](https://github.com/GELOG/plink/tree/v1.07/plink-1.07-bin/docker/Dockerfile)  based on [`Ubuntu:14.04.2`](https://registry.hub.docker.com/_/ubuntu/) image.


## What is Plink?

PLINK is a free, open-source whole genome association analysis toolset, designed to perform a range of basic, large-scale analyses in a computationally efficient manner.

The focus of PLINK is purely on analysis of genotype/phenotype data, so there is no support for steps prior to this (e.g. study design and planning, generating genotype or CNV calls from raw data).
Through integration with [gPLINK](http://pngu.mgh.harvard.edu/~purcell/plink/gplink.shtml) and [Haploview](http://www.broad.mit.edu/mpg/haploview), there is some support for the subsequent visualization, annotation and storage of results.

PLINK (one syllable) is being developed by Shaun Purcell at the Center for Human Genetic Research ([CHGR](http://chgr.mgh.harvard.edu/)), Massachusetts General Hospital ([MGH](http://www.mgh.harvard.edu/)), and the [Broad Institute](http://www.broad.mit.edu/) of Harvard & MIT, with the [support of others](http://pngu.mgh.harvard.edu/~purcell/plink/credits.shtml).  

### Why is there 2 plink versions?
- **Plink 1.07** is the latest version of plink released in 2009 by the Broad Institute.
- **Plink 2** is a complete rewrite of Plink v1, done by Christopher Chang (China). Currently in beta, the latest release is **v1.90**.

### Is this the official repository for Plink source code?

**NO**. This repository holds a copy of the latest stable release of Plink v1.07.

### Where can I find the official Plink?

- Plink v1:
  - [Project page](http://pngu.mgh.harvard.edu/~purcell/plink/)
  - [Source code (zip file)](http://pngu.mgh.harvard.edu/~purcell/plink/download.shtml#download)
- Plink v2:
  - [Project page](https://www.cog-genomics.org/plink2)
  - [Source code (Git repo)](https://github.com/chrchang/plink-ng)

### What is the directory structure of this project?

- `plink-1.07-bin/docker/`: Dockerfile for the _released_ version of Plink v1.
- `plink-1.07-src/`: A copy of Plink 1.07 source code
- `plink-2.0-bin/docker/`: Dockerfile for the _released_ version of Plink v2.


## What is Docker?
Docker is an open platform for developers and sysadmins to build, ship, and run distributed applications. 
Consisting of Docker Engine, a portable, lightweight runtime and packaging tool, and Docker Hub, a cloud service for sharing applications and automating workflows, Docker enables apps to be quickly assembled from components and eliminates the friction between development, QA, and production environments. 
As a result, IT can ship faster and run the same app, unchanged, on laptops, data center VMs, and any cloud.

https://www.docker.com/whatisdocker/

### What is a Docker Image?
Docker images are the basis of containers. 
Images are read-only, while containers are writeable. 
Only the containers can be executed by the operating system.

https://docs.docker.com/terms/image/

## How to use this image?

TODO
