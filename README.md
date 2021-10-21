# NorESM User Workshop 2021

Tutorial on "Running NorESM in a container" at the annual NorESM user workshop 2021

## Usage

### Building the book

If you'd like to develop and/or build the NorESM User Workshop 2021 book, you should:

1. Clone this repository
2. Run `pip install -r requirements.txt` (it is recommended you do this within a virtual environment)
3. (Optional) Edit the books source files located in the `noresm_user_workshop_2021/` directory
4. Run `jupyter-book clean content/` to remove any existing builds
5. Run `jupyter-book build content/`

A fully-rendered HTML version of the book will be built in `content/_build/html/`. The rendered HTML version is automatically generated to `gh-pages` every time you push changes to this repository.

## Contributors

We welcome and recognize all contributions. You can see a list of current contributors in the [contributors tab](https://github.com/NordicESMHub/NorESM_user_workshop_2021/graphs/contributors).

## Credits

This project is created using the excellent open source [Jupyter Book project](https://jupyterbook.org/) and the [executablebooks/cookiecutter-jupyter-book template](https://github.com/executablebooks/cookiecutter-jupyter-book).
