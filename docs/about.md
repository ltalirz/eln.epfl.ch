---
layout: page
title: About
permalink: /about/
---

## Philosophy

> We aim to store any kind of information correctly, reliably and in a perennial and reusable way. FAIR data is not an afterthought.

### FAIR, "machine-learning-ready" data

The ELN takes care of converting all files into [FAIR](https://www.go-fair.org/fair-principles/) , standardized, and open formats. In this way, the information will be accessible tens from year of now---and not only until the manufacturer stops supporting the format.

With all synthesis or characterization data, we also store rich metadata.

The idea is shown in the figure below. In the ideal case, the data is directly captured from the instruments, converted into a FAIR format and then stored as attachment in a [CouchDB database](https://en.wikipedia.org/wiki/Apache_CouchDB). In case this is not possible, the data can always be uploaded via drag-and-drop. A barcode system ensures that you can build a chemical library and that nothing is lost.

<img style="width: 30em" src="../assets/img/importation.png">

### Reusable

If you use eln.epfl.ch you can create data archives that can be reused by collaborators or readers of your paper. The archives are structured such that they can be understood by machines (following ideas of the [semantic web](https://en.wikipedia.org/wiki/Semantic_Web)) and accompanied by a link that can be used to visualize the data.

### Aigle development: Ready for any kind of information

The ELN is developed in a modular fashion that makes it possible to quickly adapted to new requirements or to implement new tools or data formats. The formats that are currently supported are documented in the [database schema](https://cheminfo.github.io/data_schema/).

### Built by chemists for chemists

The way data is entered into the ELN is similar to how you would use your paper based lab notebook. You can have a reaction diagram, a reagent table, and a description of the synthesis.
The only difference is that everything is coupled, the reagent table automatically retrieves data from large chemical databases, and computes the stochiometry for you.
For the most common characterization techniques in chemistry and materials science we built specific tools. You can predict and assign NMR spectra, analyze mass spectra by matching fragment or predict PXRD patterns for your crystal structures---all in the browser!

<img style="width: 30em" src="../assets/img/pxrd_overview.png">

## The cheminfo ecosystem

We did not only build the ELN, but more than 150 other libraries which are part of the following GitHub organizations

- [mljs](https://github.com/mljs): Libraries for linear algebra, optimization
- [image-js](https://github.com/image-js): Image analysis
- [cheminfo](https://github.com/cheminfo): Cheminformatics tools, like parsers for all kinds of characterization techniques
- [cheminfo-js](https://github.com/cheminfo-js): Cheminformatics tools
- [cheminfo-py](https://github.com/cheminfo-py): Webservices, e.g., for PXRD pattern predictiion or topology analysis


{% include youtube.html id="SHN07asZaGc" %}