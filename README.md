skill-ml
=========

**Open Skills Project - Machine Learning**

This is the library for the methods usable by the Open Skills API, including processing algorithms and utilities for computing our jobs and skills taxonomy.


New to Skills-ML? Check out the [Skills-ML Tour](https://workforce-data-initiative.github.io/skills-ml/skills_ml_tour)! It will get you started with the concepts. You can also check out the [notebook version of the tour](https://github.com/workforce-data-initiative/skills-ml/blob/master/Skills-ML%20Tour.ipynb) which you can run on your own.

Documentation
-----------
[Hosted on Github Pages](https://workforce-data-initiative.github.io/skills-ml/)


Quick Start
-----------
### 1. Virtualenv
**skills-ml** depends on python3.8, so create a virtual environment using a python3.6 executable.

```bash
virtualenv venv -p /usr/bin/python3.8
```
Activate your virtualenv

```bash
source venv/bin/activate
```

### 2. Installation

#### Prerequisites

* Postgres client

```bash
brew install postgresql
```

#### Installation command

```bash
pip install skills-ml
```

### 3. Import skills_ml
```python
import skills_ml
```

- There are a couple of examples of specific uses of components to perform specific tasks in [examples](examples/).
- Check out the descriptions of different algorithm types in [algorithms/](skills_ml/algorithms/) and look at any individual directories that match what you'd like to do (e.g. skill extraction, job title normalization)
- [skills-airflow](https://github.com/workforce-data-initiative/skills-airflow) is the open-source production system that uses skills-ml algorithms in an Airflow pipeline to generate open datasets


Building the Documentation
----------

skills-ml uses a forked version of pydocmd, and a custom script to keep the pydocmd config file up to date. Here's how to keep the docs updated before you push:

$ cd docs
$ PYTHONPATH="../" python update_docs.py # this will update docs/pydocmd.yml with the package/module structure and export the Skills-ML Tour notebook to the documentation directory
$ pydocmd serve # will serve local documentation that you can check in your browser
$ pydocmd gh-deploy # will update the gh-pages branch


Structure
----------
- [algorithms/](skills_ml/algorithms/) - Core algorithmic module. Each submodule is meant to contain a different type of component, such as a job title normalizer or a skill tagger, with a common interface so different pipelines can try out different versions of the components.
- [datasets/](skills_ml/datasets/) - Wrappers for interfacing with different datasets, such as ONET, Urbanized Area.
- [evaluation/](skills_ml/evaluation/) - Code for testing different components against each other.


Contributors
----------
- Kwame Porter Robinson - [Github](https://github.com/robinsonkwame)
- Eddie Lin - [Github](https://github.com/tweddielin)
- Tristan Crockett - [Github](https://github.com/thcrock)
- Zoo Chai - [Github](https://github.com/zoochai)


License
-------
This project is licensed under the MIT License - see the `LICENSE.md` file for details.
