# Python tutorial for Renewable Energy course

## Table of Contents

- Course Outline
  - [How to do modeling](#how-to-do-modeling)
    - [What is the process of modeling](#what-is-the-process-of-modeling)
    - [Some Tips and Tricks](#some-tips-and-tricks)
  - [Setting up Your Environment](#setting-up-your-environment)
    - [Installing Python](#installing-python)

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

- Python can be downloaded from [the official website](https://www.python.org/downloads/)
- If python is already installed, check if the version is `>3.10`. You can check your current version with the following command:

```bash
python --version
```

> [!NOTE]
> Depending on your configuration the above command may be `python --version` or `python3 --version`.
> For simplicity, we will use the `python` command in this course,
> but if it is not the case for you, replace every instance of the word `python` with `python3`

3 options for setting up the environment:

- VS Code + Python Extensions
-
