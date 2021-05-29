# Poetry Template Repository

This repository contains my goto template for Python projects using [Poetry][poetry].

It makes use of:

* [pyenv][pyenv]
* [Poetry][poetry]
  * Project structure that works well -- at least for me
* GitHub Workflows to run some QA tools
  * pytest
  * flake8
  * mypy
  * black
* Template config for [git-conventional-commits][gcc]

## Getting started

### 0. Download and prepare the template

```
$> curl -LO https://github.com/ErikThorsell/poetry_project_template/archive/refs/heads/main.zip
$> unzip main.zip
$> mv poetry_project_template-main <name of your project>
```

Create a new repository on e.g. [GitHub][github] and follow the instructions
for creating a new repository on the command line.

### 1. Make sure [pyenv][pyenv] is installed

Specify your Python interpreter of choice by first installing it and then
specifying the interpreter as your local interpreter for your project.

```
$> pyenv install 3.9.4
$> pyenv local 3.9.4
```

This will create a `.python-version` file.
I prefer to keep this file in the repository as I consider it an important
aspect of the project.
Others choose to ignore the file using `.gitignore`.

### 2. Create a virtual environment

```
$> python -m venv .venv
$> source .venv/bin/activate
```

### 3. Install your dependencies 

```
$> poetry install
```

### 4. Run your application

Your application should be available on your path, in accordance to what you specified in `pyproject.toml`.

```
[tool.poetry.scripts]
project_cli = "project_name.main:main"
```

Will create a CLI Script which you can execute using: `project_cli`.

<!-- REFERENCES -->
[pyenv]: https://github.com/pyenv/pyenv
[poetry]: https://python-poetry.org/
[gcc]: https://github.com/qoomon/git-conventional-commits
[github]: https://github.com