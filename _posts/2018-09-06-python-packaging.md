---
title: 'Turn Python code into a package'
date: 2018-09-06
permalink: /posts/2018/09/python-packaging/
tags:
  - Python
  - packaging
  - PyPI
  - LEIA Project
  - Jupyter Notebook
---

The title of this post is meant in every sense. It is both a command and an indicator of what will follow.

For the last few years, I have been writing small Python functions and scripts to help in the analysis of data from the LEIA Project. This includes [my metadata analyses](https://deppen8.github.io/portfolio/1-leia_project_metadata/) as well as a number of scripts that synthesize and visualize data for the annual report submitted to the Consell Insular de Mallorca, the government body that issues archaeological permits. All of this code was stored in various Jupyter Notebooks. However, [Jupyter Notebooks are *not* a perfect place to do reproducible research](https://docs.google.com/presentation/d/1n2RlMdmv1p25Xy5thJUhkKGvjtV-dkAIsUXP-AL4ffI/edit?usp=sharing). Here is the workflow I was using:
1. Download the latest data from the database as `.csv` using our online portal's simple export utilities.
2. Read the `.csv` file into a `pandas` DataFrame. In doing this, I also had to specify a number of options so that `pandas` would assign the types to different columns correctly.
3. Filter the data in various ways. For example, removing artifacts that were marked as "discarded" in the database.
4. Finally, do the actual analysis that I wanted to do.

While that isn't a terrible way to go about things and *can* be done in Jupyter Notebooks if one is careful, steps 1-3 get repeated in slightly different ways in almost every notebook. [Ideally](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself), I want to avoid that repetition. I also wanted something that I could share easily with my colleagues and other researchers.

So I decided to start building a `leiap` package. That way, all I'd have to do was `import leiap` and I'd have access to all of the code I'd written before.

My first task was to separate my code into roughly-coherent modules in order to keep things organized. So far I have `io.py`, `checks.py`, `fieldschool.py`, `mapping.py`, `progress.py`, `report.py`, `spatial.py`, and `time.py`, all of which contain a series of functions that do the tasks which used to be housed in Jupyter Notebooks. The `io.py` module is especially important because its functions allow me to pull data from the database directly with ODBC connections, thus avoiding the `.csv` downloads.

After I had everything more or less organized, I didn't really know what to do next. I found this [Packaging Python Projects](https://packaging.python.org/tutorials/packaging-projects/) tutorial and the companion [sampleproject GitHub repo](https://github.com/pypa/sampleproject) very helpful for figuring out what `__init__.py` and `setup.py` files are and how they should be structured. The `setup.py` file in the `sampleproject` repo is especially well-commented and clear about what needs to be included and what is optional. I discovered both of those links as a result of this PyCon talk from Dustin Ingram.

[![Dustin Ingram at PyCon2018](http://img.youtube.com/vi/AQsZsgJ30AE/0.jpg)](http://www.youtube.com/watch?v=AQsZsgJ30AE "Dustin Ingram at PyCon2018")

Putting it all together, I now have a directory that looks like this:

```
leiap/
    leiap/
        __init__.py
        checks.py
        fieldschool.py
        io.py
        mapping.py
        progress.py
        report.py
        setup.py
        spatial.py
        time.py
```

Additionally, by structuring my `__init__.py` file like this:

```python
from .checks import *
from .io import *
from .spatial import *
from .time import *
from .report import *
from .fieldschool import *
from .progress import *
from .mapping import *
```

I can use the generic import statement to get access to all of the functions I wrote. For example, I can use the very clean
```python
import leiap
leiap.fields_summary_table()
```
instead of less clean alternatives like
```python
from leiap.report import fields_summary_table
fields_summary_table()
```
or 
```python
import leiap
leiap.report.fields_summary_table()
```

The final destination for most Python packages is probably the [Python Package Index (PyPI)](https://pypi.org/). Once it is there, it can be installed easily by anyone with `pip` commands. To put it on PyPI, you need to generate distribution archives, which are the actual files that install the package.

```bash
$ python3 setup.py sdist bdist_wheel
```

However, because the `leiap` package allows access to the database, I do not want it to be public on PyPI, but I *do* want to share the package with my collaborators. So, to make it easily installable for them, I went ahead and created the distribution files anyway. They can then [install the package from the distribution files saved locally on their machine](https://packaging.python.org/tutorials/installing-packages/#installing-from-local-archives).

```bash
$ pip install ./downloads/leiap-0.1.1.tar.gz
```

From there, the package should work exactly as any other package you are used to like `pandas` or `numpy`. Common IDE features like help and tab-completion should work as expected.

![help_in_jupyter](/images/blog/package_help.png)

So there you have it. Some hacked-together code that crudely imported `.csv` files and was scattered across various Jupyter Notebooks now exists as its very own Python package, ready to be shared and installed wherever it's needed.