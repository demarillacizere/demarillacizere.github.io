## Hey there

This repository contains a Quarto website documenting my experiences in the MDS program so far. It also includes computational blog posts in R and Python that explore real-world datasets through reproducible code, tables, and visualizations.

## Software Requirements

Before building the website, install the following software. These are the versions used to build this project:

* **Quarto:** `1.10.18` — Install from the [Quarto installation page](https://quarto.org/docs/get-started/).
* **R:** `4.6.1` — Install from [CRAN](https://cran.r-project.org/).
* **uv:** `0.12.9` — Install using the [official uv installation guide](https://docs.astral.sh/uv/getting-started/installation/).

The R dependencies are managed with `renv`. You do not need to install `renv` separately because it bootstraps itself when the project is restored.

After installation, verify the versions from the terminal:

```bash
quarto --version
R --version
uv --version
```

## Build the Site

### 1. Clone the repository

Run in a terminal:

```bash
git clone https://github.com/demarillacizere/demarillacizere.github.io
cd demarillacizere
```

All remaining commands should be run from the root of the repository.

### 2. Install the Python dependencies

Run in the terminal:

```bash
uv sync
```

This creates the Python environment using the dependencies recorded in the repository.

### 3. Restore the R environment

Start R from the repository root:

```bash
R
```

Then, inside the R console, run:

```r
renv::restore()
```

When it finishes, exit R:

```r
q()
```

### 4. Build the website

Back in the terminal, run:

```bash
uv run quarto render
```

The rendered website will be created in:

```text
docs/
```

### 5. View the website locally

To start a local preview server, run:

```bash
uv run quarto preview
```

Quarto will print the local address in the terminal. Open that address in a web browser to view the site.

## Data

The R post uses the **Gapminder** dataset provided through the `gapminder` R package.

The Python post uses the **Palmer Penguins** dataset provided through the `palmerpenguins` Python package.

Because these datasets are supplied by installed packages, the site does not need to download the datasets from their original sources while rendering. However, an internet connection may be required during the initial environment setup to install the R and Python dependencies.

