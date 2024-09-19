# 99bottles

The purpose of this repository is to follow along with the book [*99 Bottles of OOP*](https://sandimetz.com/99bottles) by Sandi Metz.

## Setting Up Your Dev Environment

After cloning the repository, set up a virtual environment using Python 3.12 or later:

`python -m virtualenv -p <path to your Python3.12> venv`

Activate the virtual environment and then install the developer requirements:

`python -m pip install -r dev-requirements.txt`

We are using [pip-tools](https://github.com/jazzband/pip-tools) to manage dependencies. To add a new requirement, add it in the `dependencies` array in the `pyproject.toml` file. To add a developer dependency, add it in the `dev` array of the `project.optional-dependecies` table. `pip-tools` offers several useful commands:

* To create the pinned requirements.txt file: `pip-compile -o requirements.txt pyproject.toml`
* To update dependencies in the requirements.txt file: `pip-compile --upgrade`
* To create the pinned requirements file for dev: `pip-compile --extra dev -o dev-requirements.txt pyproject.toml`
* To remove any installs besides those necessary: `pip-sync requirements.txt dev-requirements.txt`
