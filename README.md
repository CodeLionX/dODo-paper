# dODo Paper repository [![Build Status](https://travis-ci.com/CodeLionX/dODo-paper.svg?token=pqFUU2qudhkNenBcNwxf&branch=master)](https://travis-ci.com/CodeLionX/dODo-paper)
Paper about https://github.com/CodeLionX/dODo

**The PDF version of this paper is included in this repository. You can download it from [`dODo-paper.pdf`](https://github.com/CodeLionX/dODo-paper/raw/master/dODo-paper.pdf).**

## Abstract

When dealing with large amounts of data, finding hidden relationships in that data can help with maintaining and improving data quality and optimizing query performance.
ODs are among these kinds of hidden relationships.
A few solutions for the automatic detection of ODs have been proposed.
All of them are designed to run on a single system and have at least exponential runtime complexity.
In this work we introduce an OD discovery algorithm, called DODO, that distributes the detection of ODs across several machines in a cluster, thereby improving both speed and scalability.
DODO is built to be fault-tolerant and to work with a dynamically changing cluster size.
We evaluate DODO in respect to its performance, scalability and robustness.
We demonstrate that the single node setup of DODO is about twice as fast as the OCDDISCOVER algorithm by Consonni et al., which DODO is based on.
Running DODO distributed across multiple nodes achieves a significant speed-up compared to the single node setup.
This shows how distribution can be used to increase performance for OD discovery algorithms, which are limited by the power of the processors they are run on.

## Contents

The main file is called `paper.tex`.
It contains the preamble and document setup stuff.
Content of the paper is structured in the file `paper_toc.tex`.
Each `section` should live in its own file in the folder `sections`.

All kind of pictures should be saved in the folder `pictures`.

We use the LaTeX class for submission to _Lecture Notes in Informatics_ (LNI) from their
[Github repo](https://github.com/gi-ev/LNI).
The required files can be found in folder `lni-tex`.

The style files required for bibliography style _LNI_ are located in the root folder.
This is required like that by biblatex.
We use the _LNI_ style from [gi-ev/biblatex-lni](https://github.com/gi-ev/biblatex-lni).

## Build

This repository uses [Travis](https://travis-ci.com/) to build the resulting LaTeX PDF.
The PDF is built only for the branches `master`, `ci-*` and `ci/*` and pushed back to this repository via a commit by Travis.

Please be aware that every _push_ to the `master`-branch will trigger a build of the PDF and the corresponding commit by Travis.
This will force you to re-sync your local repository's master branch (`git pull`) before you can push again.

**If new LaTeX packages are added to the preamble of the document, the file `texlive/texlive-packages.txt` must be updated with the new package and all transitive dependencies.**


### Use Travis to generate a current snapshot PDF

You can instruct Travis CI to build the current version of the PDF and push it back to your branch via putting `[build pdf]` in your commit message.
This is independent from the branch-dependent build-rules and works in every branch.
