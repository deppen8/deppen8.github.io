---
title: "`leiap` Python package"
excerpt: "Code written for the LEIA Project dataset<br/><img src='/images/leiap_logo_original.png'><br/>"
collection: portfolio
date: 2018-11-02
---

[![badge](https://img.shields.io/badge/GitHub-leiap-blue.svg?logo=github)](https://github.com/deppen8/leiap)
[![docs_badge](https://img.shields.io/website-up-down-green-red/https/shields.io.svg?label=leiap_docs&logo=github)](https://deppen8.github.io/leiap/)

<img align="right" src="/images/leiap_logo_small.png">The `leiap` Python package was created as a way to streamline analysis of the [LEIA Project](http://leiap.weebly.com/) dataset. I had written a great deal of code across a number of Jupyter Notebooks that I found myself re-using regularly. The code that read, cleaned, and transformed data from the project's SQLServer database was especially important to have in a handy reusable form.

Because the package is designed to be a catch-all for anything the LEIA Project needs, it covers a lot of ground: I/O, calculations, spatial data, visualizations, and more. There is even a chore scheduler for the field team. As much as possible, these different categories are separated into their own modules.

The package is not available on PyPI simply because it is only intended for use by project members.

Full code documentation for `leiap` is built with Sphinx and available on a [GitHub Pages site](https://deppen8.github.io/leiap/).
