# Toy Model for Ergo DVC POC

In order to test DVC a POC with a test data science usecase is created

## Getting Started

To set up your local development environment, please use a fresh virtual environment.

To create the environment run:

    conda env create --name DVC-POC-MODEL --file=environment-dev.yml

To activate the environment run:

    conda activate DVC-POC-MODEL

To update this environment with your production dependencies run:

    conda env update --file=environment.yml

You can now import functions and classes from the module with `import dvc_poc_model`.

### Testing

We use `pytest` as test framework. To execute the tests, please run

    python setup.py test

To run the tests with coverage information, please use

    python setup.py testcov

and have a look at the `htmlcov` folder, after the tests are done.

### Notebooks

To use your module code (`src/`) in Jupyter notebooks (`notebooks/`) without running into import errors, make sure to install the source locally

    pip install -e .

This way, you'll always use the latest version of your module code in your notebooks via `import dvc_poc_model`.

Assuming you already have Jupyter installed, you can make your virtual environment available as a separate kernel by running:

    conda install ipykernel
    python -m ipykernel install --user --name="DVC-POC-MODEL"

Note that we mainly use notebooks for experiments, visualizations and reports. Every piece of functionality that is meant to be reused should go into module code
and be imported into notebooks.

### Distribution Package

To build a distribution package (wheel), please use

    python setup.py dist

this will clean up the build folder and then run the `bdist_wheel` command.

### Contributions

Before contributing, please set up the pre-commit hooks to reduce errors and ensure consistency

    pip install -U pre-commit && pre-commit install

## Contact

Moritz Osterberger (moritz.osterberger@alexanderthamm.com)

## License

© Alexander Thamm GmbH
