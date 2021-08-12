# `pandas-vet`

[![badge](https://img.shields.io/badge/GitHub-pandas--vet-blue.svg?logo=github)](https://github.com/deppen8/pandas-vet)
[![GitHub stars](https://img.shields.io/github/stars/deppen8/pandas-vet?style=social)](https://github.com/deppen8/pandas-vet)

[![PyPI](https://img.shields.io/pypi/v/pandas-vet.svg)](https://pypi.org/project/pandas-vet/)
[![PyPI - Downloads](https://img.shields.io/pypi/dm/pandas-vet.svg)](https://pypi.org/project/pandas-vet/)
[![Conda Version](https://img.shields.io/conda/vn/conda-forge/pandas-vet.svg)](https://anaconda.org/conda-forge/pandas-vet)
[![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/pandas-vet.svg)](https://anaconda.org/conda-forge/pandas-vet)

```{image} ../assets/images/pandas-vet-logo.png
:alt: pandas-vet-logo
:width: 150px
:align: right
```

`pandas-vet` is a plugin for `flake8` that provides opinionated linting for `pandas` code.

It began as a project during the PyCascades 2019 sprints and development continued at the PyCascades 2020 sprints.

## Motivation

Starting with `pandas` can be daunting. The usual internet help sites are littered with different ways to do the same thing and some features that the `pandas` docs themselves discourage live on in the API. `pandas-vet` is (hopefully) a way to help make `pandas` a little more friendly for newcomers by taking some opinionated stances about `pandas` best practices. It is designed to help users reduce the `pandas` universe.

The idea to create a linter was sparked by [Ania Kapuścińska](https://twitter.com/lambdanis)'s talk at PyCascades 2019, ["Lint your code responsibly!"](https://youtu.be/hAnCiTpxXPg?t=21814).

Many of the opinions stem from [Ted Petrou's](https://twitter.com/TedPetrou) excellent [Minimally Sufficient Pandas](https://medium.com/dunder-data/minimally-sufficient-pandas-a8e67f2a2428). Other ideas are drawn from `pandas` docs or elsewhere. The [Pandas in Black and White](https://deppen8.github.io/pandas-bw/) flashcards have a lot of the same opinions too.
