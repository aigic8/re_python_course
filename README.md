# Python tutorial for Renewable Energy course

## Table of Contents

- Course Outline
  - [How to do modeling](#how-to-do-modeling)
    - [What is the process of modeling](#what-is-the-process-of-modeling)
    - [Some Tips and Tricks](#some-tips-and-tricks)
  - [Setting up Your Environment](#setting-up-your-environment)
    - [Installing Python](#installing-python)
    - [Setting up the Editor](#setting-up-the-editor)
  - [Getting Familiar with Jupyter](#getting-familiar-with-jupyter)
    - [Why Jupyter](#why-jupyter)
    - [Making A Notebook in VS Code](#making-a-notebook-in-vs-code)
    - [Moving around in Jupyter](#moving-around-in-a-notebook)
  - [Getting Familiar with Python's Basic Syntax](#getting-familiar-with-pythons-basic-syntax)
    - [Variables - Basic Types](#variables---basic-types)
    - [Comments](#comments)
    - Conditional Clauses
    - [Variables - Lists](#variables---lists)
      - [Lists Challenge 1](#lists-challenge-1)
      - [Lists Challenge 2](#lists-challenge-2)
    - Variables - Tuples
    - Variables - Dictionaries
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

1. `Finding`: Finding a reference paper/library
1. `Implementing`: Extract the model info from the paper
1. `Validating`: Write the model in python feed the input data in the reference paper and check if the outputs match
    - Ask your group to check if the data is valid
    - Use the paper formulas
    - Use a parallel model with the same input data (PVSyst for PV)
1. `Connecting the parts together`: After writing, and validating all the parts *separately*, all the parts should be connected to get final result

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
      - Setup format on save using `Ruff`. In VS Code settings json add the following snippet:

```json
"notebook.formatOnSave.enabled": true,
"[python]": {
    "editor.defaultFormatter": "charliermarsh.ruff",
    "editor.formatOnSave": true,
},
```

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
  - I widely used tool, but personally, I have no experience using it

## Getting Familiar with Jupyter

### Why Jupyter?

- Working with data is hard, there are a lot of edge cases
- Most of the code is only used for understanding the data and characteristics

### Making a Notebook in VS Code

- Press `Ctrl+Shift+P` (`Cmd+Shift+P` for mac)
- Type `New Jupyter Notebook` and choose the first option
- After the file is opened press `Ctrl+S` (`Cmd+S` for mac) to save the file

### Moving Around in a Notebook

- Jupyter has two modes `Command Mode` and `Edit Mode`
- `Command mode` is when a cell is selected and `Edit Mode` is when you are editing inside a cell
- To find out how to move faster while being in command mode, check out [Jupyter Notebook Keybindings](#jupyter-notebook-keybindings)

## Getting Familiar with Python's Basic Syntax

### Variables - Basic Types

In python, setting a variable is pretty simple:

```python
x = 5
y = 10
z = x + y
print(z) # 15
```

Basic data types:

- `string` (referred as `str` in python world)
- `float`
- `int`
- `bool`
- `None`

```python
age = 16 # int
grade = 18.34 # float
is_male = True # boolean
is_over_18 = False # boolean
work_place = None # none
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

### Variables - Lists

In python lists are a group of items. Important points about lists:

- Unlike C arrays, they do not have to have a predefined length

```python
my_list = []
print(len(my_arr)) # 0
my_list.append(1)
print(len(my_arr)) # 1
```

- They can consist of different types of data (but it is not recommended to store different types in one list)

```python
my_list = [1, "Alireza", True, 4.2]
```

For checking common functions in lists you can check [Lists CheatSheet](#lists-cheatsheet)

#### Lists Challenge 1

Consider having a lists of `int` variables like the following:

```python
my_list = [1, 2, 3, 4]
```

write a code to add the index to each number, for this example it would be:

```python
print(my_list) # 1, 3, 5, 7
```

<details>
<summary>Answer</summary>

```python
my_list = [1, 2, 3, 4]
for index, item in enumerate(list):
  my_list[index] = index + item
print(my_list)
```

</details>

#### Lists Challenge 2

Consider having the following variables:

```python
list_with_duplicates = [1, 2, 4, 1, 3, 2]
list_without_duplicates = []
```

write the code to add unique elements to the variable `lists_without_duplicates`. For this example, the expected result would be:

```python
print(list_without_duplicates) # 1, 2, 4, 3
```

<details>
<summary>Answer</summary>

```python
list_with_duplicates = [1, 2, 4, 1, 3, 2]
list_without_duplicates = []

for item in list_with_duplicates:
  if not item in list_without_duplicates:
    list_without_duplicates.append(item)

print(list_without_duplicates) # 1, 2, 4, 3
```

</details>

## CheatSheet

## Jupyter Notebook Keybindings

- `Shift + Enter`: Run the cell and move to the next one.
- `Ctrl + Enter`: Run the cell but stay on the same cell.
- `Shift + M`: Merge the selected cell with the cell below.
- `Shift + Up/Down Arrow`: Extend cell selection above or below.
- `A`: Insert a new cell above the current cell.
- `B`: Insert a new cell below the current cell.
- `D`: Delete the selected cell.
- `Z`: Undo cell deletion.

## Lists CheatSheet

### Length of the list

To check the length (size) of the lists use the `len` function:

```python
my_list = [1, 2, 3, 4]
print(len(list)) # 4
```

### Iterating items

Basic iterating through a list:

```python
my_list = ["Alireza", "Mohammad"]
for item in my_list:
  print(item) # Alireza, Mohammad
```

Iterating items with index:

```python
my_list = ["Alireza", "Mohammad"]
for index, item in enumerate(my_list):
  print(index, item) # 0 Alireza, 1 Mohammad
```

> [!NOTE]
> **What is index?**
> In lists, the order of elements matter and each element has a known index.
> The first element has index of `0` (and not `1`), the second element has `1` and ...

### Adding new elements

To add an element to the **end of the list**:

```python
my_list = ["Alireza", "Mohammad"]
print(my_list) # Alireza, Mohammad

my_list.append("Hamed")
print(my_list) # Alireza, Mohammad, Hamed
```

Adding element in an specific index:

```python
my_list = ["Alireza", "Mohammad"]
print(my_list) # Alireza, Mohammad

my_list.insert(1, "Hamed")
print(my_list) # Alireza, Hamed, Mohammad
```

### Removing elements

Removing by value:

```python
my_list = ["Alireza", "Mohammad"]
print(my_list) # Alireza, Mohammad

my_list.remove("Alireza")
print(my_list) # Mohammad
```

Removing by index:

```python
my_list = ["Alireza", "Mohammad"]
print(my_list) # Alireza, Mohammad

my_list.pop(1)
print(my_list) # Alireza
```

### Modifying Elements

Single elements can be modified with:

```python
my_list = ["Alireza", "Mohammad"]
my_list[1] = "Hamed"
print(my_list) # Alireza, Hamed
```

### Selecting elements

Selecting a single element in a list:

```python
my_list = ["Alireza", "Mohammad"]
el = my_list[0] # select where index == 0 => Alireza
print(el) # Alireza
```

Selecting a sublist of elements in a list:

```python
my_list = ["Alireza", "Mohammad", "Hamed"]
els = my_list[0:2] # select where index >= 0 and index < 2
print(els) # Alireza, Mohammad
```

> [!NOTE]
> Notice how the starting index (`0`) is inclusive (appears in the sublist)
> but the ending index (`2`) does not. (it is exclusive) This is how python work when selecting a subset

There can be variations of this syntax:

```python
my_list = ["Alireza", "Mohammad", "Hamed"]

### only stating the start
els_start = my_list[1:] # select where index >= 1
print(els_start) # Mohammad, Hamed

### only stating the end
els_end = my_list[:1] # select where index < 1
print(els_end) # Alireza

### negative indexes
els_neg = my_list[:-2] # select where from the end < 2
print(els_neg) # Alireza
```

### Checking if element exists in a list

To check if an element is in the list:

```python
my_list = ["Alireza", "Mohammad", "Hamed"]
print("Alireza" in my_list) # True
print("Davood"in my_list) # False
```
