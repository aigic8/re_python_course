# Python tutorial for Renewable Energy course

## Table of Contents

- Course Outline
  - [How to do modeling](#how-to-do-modeling)
    - [What is the process of modeling](#what-is-the-process-of-modeling)
    - [Some Tips and Tricks](#some-tips-and-tricks)
  - [Setting up Your Environment](#setting-up-your-environment)
    - [Installing Python](#installing-python)
    - [Setting up the Editor](#setting-up-the-editor)
    - TODO Getting Familiar with Jupyter
  - [Getting Familiar with Python's Basic Syntax](#getting-familiar-with-pythons-basic-syntax)
    - [Variables - Basic Types](#variables---basic-types)
    - [Comments](#comments)
    - Variables - Arrays
    - Variables - Tuples
    - Variables - Dictionaries
    - If clauses
    - Loops
    - Functions
- CheatSheet
  - Jupyter keybindings
  - Python
    - String
    - Array
    - Dictionary
  - Numpy
    - TODO
  - Pandas
    - TODO
  - Matplotlib + Seaborn
    - TODO

## How to do modeling?

### What is the process of modeling

1. `Finding`: Finding a reference paper
1. `Implementing`: Extract the model info from the paper
1. `Validating`: Write the model in python feed the input data in the reference paper and check if the outputs match

### Some Tips and Tricks

- Start with simple models and make them more complex as you go deeper in the process
- Use reference papers with extensive input and output so you can validate your models
- Break your process to smaller parts and validate each part separately
  - For a PV model, develop a model in PVSyst in parallel and compare the results with them
- For some model which are essentially complex (PV modelling for example) it might be a better option to use a library

## Setting up Your Environment

### Installing Python

- **Downloading and Installing**
  - Python can be downloaded from [the official website](https://www.python.org/downloads/)
  - **MAKE SURE TO CHECK THE ADD TO PATH OPTION WHILE INSTALLING ON WINDOWS**
- **Python version**
  - Python is *mostly backward compatible*, which means if you have a newer version of python it can run older's versions code, but if you have older version it may have some problems running newer codes.
  - The latest and the recommended version is `3.13`
  - The best bet is for all the team to have the same version installed
  - If python is already installed, check if the version is **AT LEAST** `>3.10`. You can check your current version with the following command:

```bash
python --version
```

> [!NOTE]
> Depending on your configuration, the above command may be `python --version` or `python3 --version`.
> For simplicity, we will use the `python` command in this course,
> but if it is not the case for you, replace every instance of the word `python` with `python3` throughout the course

### Setting up the Editor

4 options for setting up the environment:

- **VS Code + Python Extensions**
  - Visual Studio Code can  be downloaded from the [Official Website](https://code.visualstudio.com/download)
  - The method used through this course
  - Install and use the following extensions
    - [Official python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
    - [Official Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
    - [Ruff](https://marketplace.visualstudio.com/items?itemName=charliermarsh.ruff) (Optional - For code formatting)
- **Pycharm Community Edition**
  - Better initial typing and autocomplete support than VS Code
  - Can be downloaded from [The official website](https://www.jetbrains.com/pycharm/download/)
  - In the free version, notebook view is not available, but you download the cracked Pro edition and **Become a Pirate**
- **Google Colab (remote)**
  - Can be visited from [The official website](https://colab.research.google.com/)
  - There is no need to install any software, only requires a google account
  - There is no need to transfer code between teammates since everything is online
  - If you have a data file, the file must be uploaded to the Colab
  - The resources in the free edition is probably enough for your projects
- **Jupyter notebook**
  - I have no experience using this tool

## Getting Familiar with Python's Basic Syntax

### Variables - Basic Types

In python, setting a variable is pretty simple:

```python
x = 5
y = 10
z = x + y
print(z) # 15
```

Basic data types are `string` (referred as `str` in python world), `float`, `int`, `bool`.

```python
age = 16 # int
grade = 18.34 # float
is_male = True # boolean
is_over_18 = False # boolean
name = "Alireza" # string
```

> [!NOTE]
> Notice the same convention in the variable names. In python *naming variables*
> is in `snake_case`. Which means all the letters are lower case and the words
> are connected with underlines.
>
> Though it is **only a convention**, using other naming methods like `isMale` will not through an error.

### Comments

In python the syntax for comments in `#` character and then the comment

```python
# This is a comment
# That is multiline.
# For each line there is a separate '#' character

name = "Alireza" # comments can also start from the middle of the lines
```
