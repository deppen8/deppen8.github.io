# `prospect`

[![docs_badge](https://img.shields.io/website-up-down-green-red/https/shields.io.svg?label=docs&logo=github)](https://deppen8.github.io/prospect/)
[![badge](https://img.shields.io/badge/GitHub-prospect-blue.svg?logo=github)](https://github.com/deppen8/prospect)

[![PyPI](https://img.shields.io/pypi/v/prospect)](https://pypi.org/project/prospect/)
![PyPI - Downloads](https://img.shields.io/pypi/dm/prospect)
[![Conda Version](https://img.shields.io/conda/vn/conda-forge/prospect.svg)](https://anaconda.org/conda-forge/prospect)
[![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/prospect.svg)](https://anaconda.org/conda-forge/prospect)

`prospect` is an open source Python package to build and run simulations of archaeological surveys. It is designed to be a flexible tool that can be run with some sensible defaults or highly customized, depending on the user’s needs.

Development was started as part of my Ph.D. research in the [Digital Archaeology Research Lab](https://www.digarlab.uw.edu/) at the University of Washington.

![prospect-logo](../assets/images/prospect-logo.png)

## Why `prospect`?

There are two use cases that motivated the development and design of `prospect`.

**As a planning tool for archaeological surveys**

Users can model different methodologies to see how they might impact artifact recovery rates or how they impact the discovery of specific features of interest. `prospect` can also provide estimates of the amount of time a particular survey will take and could be used to demonstrate compliance with heritage regulations, both of which are immediately useful for cultural resource management (CRM) companies.

**As a heuristic device for studying and evaluating survey methodologies**

Users can recreate the actual survey methodology used in the field and then vary different parameters to see what effects (or not) these might have had on the results. For example, one could repeat a simulation with a wide range of underlying artifact densities as a way to determine whether their methodology was robust enough to accurately estimate those densities.

This use case is also important as a way to address the impracticalities of producing reproducible field studies; controlled seeding experiments or re-surveying studies that have been used in the past are too limited in scale and scope. `prospect` can quickly generate thousands of surveys under wide ranges of parameters.

**Other uses**

While these two use cases were the main drivers in the development of `prospect`, it might also be useful in other areas. Some possibilities:

- As a tool for teaching students about survey methodologies
- As a gateway for teaching archaeology students to program in Python
- Outside of archaeology, it could be adapted for use in planning field research in disciplines like biology, ecology, paleontology, etc.
