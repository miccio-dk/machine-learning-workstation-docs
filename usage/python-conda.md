# Python/Conda

A lot of libraries for machine learning \(keras, pytorch, tensorflow, sk-learn\), numerical computing \(numpy, scipy\), and data visualization \(matplotlib, pandas, seaborn\) are available in the form of python packages.

While its builtin package manager `pip` let's you easily install new packages, it doesn't fully account for their dependencies which may result in malfunctionings or unreplicable results. Therefore, it is recommended to use `conda` instead; conda is a package and environment manager, meaning that it allows you to create and maintain multiple development environments at the same time, each one with its own package versions, while keeping track of dependencies and avoiding conflicts. This also means that you can have the same development setup on the workstation as well as on your local machine: just install conda \(and set up an environment\) in there too!

Please note: it is also recommended to use Python 3.6 or 3.7 rather than 2.7, which will soon be discontinued.

For more information about conda, please refer to its excellent [user manual](https://conda.io/projects/conda/en/latest/user-guide/index.html) or [cheatsheet](https://conda.io/projects/conda/en/latest/user-guide/cheatsheet.html).

## Install miniconda

The following commands have to be executed from a terminal connected to the workstation.

Download the miniconda installer:

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

Run it:

```bash
bash Miniconda3-latest-Linux-x86_64.sh
```

Go ahead and keep the default settings, then restart the connection to verify the installation. Type:

```bash
conda list
```

If the installation was successful, a list of installed packages should appear.

## Setup environment

In order to create a new environment called `<ENV_NAME>`, you have to type:

```bash
conda create --name <ENV_NAME>
```

You can then activate the environment by running:

```bash
conda activate <ENV_NAME>
```

You will know that the environment is active because its name will appear between parentheses at the beginning of the command prompt. Once an environment is active, you can access all the python packages installed within. You can also use the command above to switch between existing environments.

In order to install the custom package `<PACKAGE_NAME>` within the environment, make sure the environment is active then type:

```bash
conda install <PACKAGE_NAME>
```

You can search for python packages on [this repository](https://anaconda.org/), which also contains detailed instruction on how to install most packages.

Some packages may simply not exist in conda; as a last resort, you can install pip inside your environment and then use pip from within the conda environment:

```bash
conda install pip
pip install <PACKAGE_NAME>
```

## Other commands

* Update conda:

  ```bash
  conda update conda
  ```

* Update a package in the environment:

  ```bash
  conda update <PACKAGE_NAME>
  ```

* Remove a package from the environment:

  ```bash
  conda remove <PACKAGE_NAME>
  ```

* List environments:

  ```bash
  conda info --envs
  ```

* Delete environment:

  ```bash
  conda env remove --name <ENV_NAME>
  ```

The following commands can be used to share environments.

* Export environment into `.yml` file:

  ```bash
  conda env export > environment.yml
  ```

* Create environment from `.yml` file:

  ```bash
  conda env create -f environment.yml
  ```

For more commands, refer to [this page](https://conda.io/projects/conda/en/latest/user-guide/tasks/index.html).

