[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# datascience-jupyter
Lightweight Docker-based Python environment for data science with Jupyter notebooks

This repository is designed so that you can customise the Python environment using the `requirements.txt` file - if you don't need that, just use the (standard Jupyter images)[https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html].

For a more heavy-weight solution with lots of useful extensions, look at (ML Workspace)[https://github.com/ml-tooling/ml-workspace].

## Installation and setup

Run using Docker Compose in detached mode (`-d`). From the repository root:

`docker-compose up -d`

This will create a Jupyter Notebook server that can be accessed via http://localhost:8888. When prompted for a password/token, enter `local_dev`. The repository root folder is mounted as `/working`.

## Customisation

You can customise the Jupyter Notebook Docker image that is used in the `Dockerfile`. The base image is the `datascience-notebook`, but a few other options include (in rough order of increasing complexity):
 - `minimal-notebook`
 - `scipy-notebook`
 - **`datascience-notebook`**
 - `tensorflow-notebook`
 - `pyspark-notebook`

If you change the image, you will need to rebuild the container before bringing it up:

    docker-compose build
    docker-compose up -d

More info on the different Jupyter images can be found here: (https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html)[https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html]

The Python environment can be customised by adding to the `requirements.txt`, or alternatively using a Conda `.yml` enivronment file - uncomment the relevant lines in the `Dockerfile`.



