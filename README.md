<p align="center">
  <img width=600 src="https://github.com/user-attachments/assets/a77313b6-1a42-46c1-8230-708af3c50a50">
</p>
<p align="center">
  <b>A mini tool to better handle your Conda environment and Python package</b>
</p>
<p align="center">
  <a href="https://github.com/pabroux/Conda-piptools/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/pabroux/Conda-piptools.svg" alt="License Badge">
  </a>
</p>


## About
Conda-piptools makes your Conda environment and Python package management easier:
- It allows you to specify easily the exact Python version as well as other things you want (e.g. CUDA and CUDNN versions) for a Conda environment;
- It allows you to better handle the dependencies and the compatibilities of your Python packages. More precisely, it requires you to only specify minimal constraints (e.g. `torch >= 1.7` and `numpy`) and Conda-piptools will then figure out exact and mutually compatible versions (e.g. `torch==1.7.1` and `numpy==1.19.5`).
`

> [!NOTE]
> As its name implies, Conda-piptools uses [Conda](https://anaconda.org/anaconda/conda) and [pip-tools](https://github.com/jazzband/pip-tools) in the background.

## Requirements
You need to have [Conda](https://anaconda.org/anaconda/conda) installed.

## Usage
Follow these steps:

1. Specify your Python version as well as the versions of other things (e.g. CUDA and CUDNN versions) you want for a conda environment in the `environment.yml` file;
2. Use the `setEnvName.sh` script to set the name of the new or existing conda environment:
```
./setEnvName.sh "yourEnvironmentName"
```
3. Specify your Python package requirements for the development and the production respectively in `requirements/dev.in` and `requirements/prod.in`;
4. Use the `make` command to create and/or update all your Python packages (use `make force` if you want to force it):
```
make
```

## Multiple Conda installed
If you have multiple Conda installed, use Conda-piptools inside the _base_ Conda environment of the targeted Conda.
