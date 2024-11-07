# Python tutorial for Renewable Energy course

## Table of Contents

- [Python tutorial for Renewable Energy course](#python-tutorial-for-renewable-energy-course)
  - [Table of Contents](#table-of-contents)
  - [How to do modeling?](#how-to-do-modeling)
    - [What is the process of modeling](#what-is-the-process-of-modeling)
    - [Some Tips and Tricks](#some-tips-and-tricks)
  - [Setting up Your Environment](#setting-up-your-environment)
    - [Installing Python](#installing-python)
    - [Setting up the Editor](#setting-up-the-editor)
  - [Getting Familiar with Jupyter](#getting-familiar-with-jupyter)
    - [Why Jupyter?](#why-jupyter)
    - [Making a Notebook in VS Code](#making-a-notebook-in-vs-code)
    - [Moving Around in a Notebook](#moving-around-in-a-notebook)
  - [Getting Familiar with Python's Basic Syntax](#getting-familiar-with-pythons-basic-syntax)
    - [Variables - Basic Types](#variables---basic-types)
    - [Comments](#comments)
    - [Conditional Clauses](#conditional-clauses)
      - [`or` logical operator](#or-logical-operator)
      - [`and` logical operator](#and-logical-operator)
      - [`not` logical operator](#not-logical-operator)
      - [Combining logical operators](#combining-logical-operators)
      - [Conditional Clauses - Challenge 1](#conditional-clauses---challenge-1)
    - [Variables - Lists](#variables---lists)
      - [Lists Challenge 1](#lists-challenge-1)
      - [Lists Challenge 2](#lists-challenge-2)
      - [Lists Challenge 3](#lists-challenge-3)
    - [Variables - Dictionaries](#variables---dictionaries)
      - [Dictionaries Challenge 1](#dictionaries-challenge-1)
      - [Dictionaries Challenge 2](#dictionaries-challenge-2)
      - [Dictionaries Challenge 3](#dictionaries-challenge-3)
    - [Functions](#functions)
      - [Functions Basics](#functions-basics)
      - [Passing parameters to functions by name](#passing-parameters-to-functions-by-name)
      - [(Advanced) Functions `*` keyword for parameters](#advanced-functions--keyword-for-parameters)
      - [Functions Challenge 1](#functions-challenge-1)
      - [Functions Challenge 2](#functions-challenge-2)
  - [CheatSheet](#cheatsheet)
    - [Jupyter Notebook Keybindings](#jupyter-notebook-keybindings)
    - [Lists CheatSheet](#lists-cheatsheet)
      - [Length of the list](#length-of-the-list)
      - [Iterating items](#iterating-items)
      - [Adding new elements](#adding-new-elements)
      - [Removing elements](#removing-elements)
      - [Modifying Elements](#modifying-elements)
      - [Selecting elements](#selecting-elements)
      - [Checking if element exists in a list](#checking-if-element-exists-in-a-list)
    - [Dictionaries CheatSheet](#dictionaries-cheatsheet)
      - [Length of dictionary](#length-of-dictionary)
      - [Checking if key exists](#checking-if-key-exists)
      - [Iterating over dictionary](#iterating-over-dictionary)
      - [Removing an element](#removing-an-element)
      - [Merging Dictionaries (Python 3.9+)](#merging-dictionaries-python-39)
  - [To Dos](#to-dos)

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
  - Commonly used tool, but personally, I have no experience using it

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

### Conditional Clauses

In python we have 3 main conditional blocks:

- `if`
- `elif`
- `else`

An example of using these conditionals:

```python
name = "Mohammad"
if name == "Alireza":
  print("Hello AR!") # this will not print
elif name == "Hamed":
  print("Hello HD!") # this will not print
else:
  print("Hello MD!") # this will print
```

> [!NOTE]
> Notice how we are using `==` and not `=`. This is a `comparison operator`.
> `=` gives a certain variable certain value, but `==` means to check if values are the same.
> For example:
>
> ```python
> name = "Alireza"
> print(name == "Alireza") # True
> print(name == "Hamed") # False
> ```
>
> Other common comparison operators are:
>
> - `>`: greater
> - `<`: less
> - `>=`: greater or equal to
> - `<=`: less or equal to
> - `!=`: not equal to

Another important point:

> [!NOTE]
> Unlike other languages in python you can have two sided comparisons for a variable.
> For example
>
> ```python
> age = 23
> is_teen = 9 > age > 20
> print(is_teen) # False
> ```

#### `or` logical operator

```python
name = "Alireza" 
age = 23
is_working = False
if age >= 18 or is_working:
  print("good living on your own") # does not print
```

#### `and` logical operator

```python
name = "Alireza" 
age = 23
if name == "Alireza" and age < 18:
  print("child Alireza") # does not print
elif name == "Alireza" and age >= 18:
  print("adult Alireza") # prints
else:
  print("unknown person") # does not print
```

#### `not` logical operator

The not operators reverses the result:

```python
name = "Alireza" 
if not name == "Mohammad":
  print("Hello bot Mohammad") # prints
```

#### Combining logical operators

```python
name = "Mohammad"
mohammad_has_permission = True

if name == "Alireza" or (name == "Mohammad" and mohammad_has_permission):
  print("you are allowed")
```

#### Conditional Clauses - Challenge 1

Write a code that check if a person is eligible for voting or not checking the following variables:

```python
age = 20
is_citizen = True
```

and prints the following statements in the following scenarios:

- `person is citizen and older (greater equal) than 18`: "You can vote"
- `person is citizen and younger than 18`: "You are too young"
- `person is not citizen and older (greater equal) than 18`: "You not a citizen"
- `person is not citizen and younger than 18`: "What are you doing here?"

<details>
<summary>Answer</summary>

```python
age = 20
is_citizen = True
if age >= 18 and is_citizen:
  print("You can vote")
elif age < 18 and is_citizen:
  print("You are too young")
elif age >= 18 and not is_citizen:
  print("You are not a citizen")
else:
  print("What are you doing here?")
```

</details>

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

Consider having a list of numbers:

```python
my_list = [1, 4, 8, 12, 13, 3]
```

write a code that print elements only if they are *greater than 5*.

<details>
<summary>Answer</summary>

```python
my_list = [1, 4, 8, 12, 13, 3]
for item in list:
  if item > 5:
    print(item)
```

</details>

#### Lists Challenge 2

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

#### Lists Challenge 3

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

### Variables - Dictionaries

With dictionaries values are stored as key/value pairs. An example of a dictionary:

```python
##### Initializing a dictionary
user_ages = {
  "Alireza": 23,
  "Mohammad": 25,
  "Hamed": 18,
}

##### Getting a value from a dictionary
print(user_ages["Alireza"]) # 23

##### Setting a value in a dictionary
user_ages["Navid"] = 18 # setting a new value
user_ages["Mohammad"] = 24 # replacing a current value
print(user_ages["Mohammad"]) # 24
print(user_ages["Mohammad"]) # 18
```

Some important points on dictionaries:

- Unlike lists, the order of elements is not saved in the dictionaries
- They are useful when you want to get a value by a specific key (and not an index)

For more information on common functions on dictionaries, check out [Dictionaries CheatSheet](#dictionaries-cheatsheet)

#### Dictionaries Challenge 1

Consider we have the following variables:

```python
my_dict = {"Alireza": 23, "Mohammad": 11, "Hamed": 22}
```

Write a code that prints all the keys

```text
Alireza
Mohammad
Hamed
```

<details>
<summary>Answer</summary>

```python
my_dict = {"Alireza": 23, "Mohammad": 11, "Hamed": 22}
for key in my_dict.keys():
  print(key)
```

</details>

#### Dictionaries Challenge 2

Consider we have the following variables:

```python
my_list = [1, 1, 3, 2, 3, 3, 4, 5, 3]
frequencies = {}
```

Fill the dictionaries in a way that the key and values represent number of accurances
of a number in the list. For this example it would be:

```python
print(frequencies) # {1: 2, 2: 1, 3: 4, 4: 1, 5: 1}
```

You can see number `3` occurred `4` times in the list as a result `frequencies[3]` is `4`. 
Number `5` occurred only once and `frequncies[5]` is `1`.

<details>
<summary>Answer</summary>

```python
my_list = [1, 1, 3, 2, 3, 3, 4, 5, 3]
frequencies = {}
for item in my_list:
  if item in frequencies:
    frequencies[item] += 1
  else
    frequencies[item] = 1

print(frequencies)
```

</details>

#### Dictionaries Challenge 3

Consider we have the following variables:

```python
my_dict = {"Alireza": 18, "Mohammad": 18, "Hamed": 30, "Navid": 30, "Majid": 5}
ages_dict = {}
```

Write a code that reverses the keys and values and for each age (as a key) shows all the people who have that age (value as a list). For this example it would be:

```python
print(ages_dict) 
# { 
#   18: ["Alireza", "Mohammad"] ,
#   30: ["Hamed", "Navid"],
#   5: ["Majid"]
#}
```

Both `Alireza` and `Mohammad` have the age of `18` so they appeared in a list
with the key of `18`. `Majid` is the only person with the age of `5` so he appeared in
list with a single element with the key of `5`.

<details>
<summary>Answer</summary>

```python
my_dict = {"Alireza": 18, "Mohammad": 18, "Hamed": 30, "Navid": 30, "Majid": 5}
ages_dict = {}
for age, name in my_dict.items():
  if age in ages_dict:
    ages_dict[age].append(name)
  else
    ages_dict[age] = [name]

print(ages_dict)
```

</details>

### Functions

Functions are *inspired* by math functions. They get some values as input and return none,one or multiple outputs. One function that we used is `print` for writing texts to the console.

#### Functions Basics

Functions are defined with the following syntax:

```python
def add(num1, num2):
  return num1 + num2
```

The `return` keyword is for the output of the function. For example if you call this function it will return:

```python
num1 = 3
num2 = 2

res = add(num1, num2)
print(res) # 5
```

Returning things is not necessary and functions can return nothing for example:

```python
def my_print(text):
  print("my print")
  print(text)

my_print("salam") # my print, salam
```

#### Passing parameters to functions by name

In python, you can pass parameters to function both **by order** and **by name**. For example consider this function:

```python
def draw_dot(color, x, y, z): 
  print(f"drawing dot: x = {x}, y = {y}, z = {z}, color = {color}")
```

You can pass the parameters by order to the function:

```python
draw_dot('red', 10, 13, 11)
```

However, the problem is the code is not readable. If someone is not familiar with the function, he would have no idea which parameter is `x`, which is `y` and...

In order to resolve this issue, we used `named parameters`. We can call this function using this method:

```python
draw_dot(color='red', x=10, y=13, z=11)
draw_dot(color='blue', x=10, z=12, y=15)
```

This code is much more readable than the previous example, since we know which
input parameter has which value.

Also notice that in the second call the order of the parameters is not the same as the function definition and `z` comes before `y`.

*When calling functions using named parameters the order of parameters does not matter.*

> [!NOTE]
> Generally it is a good idea to use named parameters when you have
> more than 3 input parameters since they make your code much more
> readable.

#### (Advanced) Functions `*` keyword for parameters

Consider having the following function:

```python
def draw_dot(color, x, y, z): 
  print(f"drawing dot: x = {x}, y = {y}, z = {z}, color = {color}")
```

This function can be called both by named and ordered parameters. However, you can force the user *only use named parameters* by using the `*` keyword.

```python
def draw_dot(*, color, x, y, z): 
  print(f"drawing dot: x = {x}, y = {y}, z = {z}, color = {color}")
```

Now the user can not call the function without named parameters:

```python
# will not work
draw_dot('red', 10, 13, 11)

# will work
draw_dot(color='red', x=10, y=13, z=11)
```

You can also specify certain parameters to only be named parameters. For example:

```python
def draw_dot(color, *, x, y, z): 
  print(f"drawing dot: x = {x}, y = {y}, z = {z}, color = {color}")
```

In this example, `color` does not have to be a named parameter but `x`, `y` and `z` are. So this function can be called in this way:

```python
draw_dot('red', x=10, y=13, z=11)
```

> [!INFO]
> *Basically, all the parameters after the `*` are named parameters and all the parameters before that can be both called with their names and without*

#### Functions Challenge 1

Write a function that gets two parameters `num1` and `num2` and returns their multiplication product.

<details>
<summary>Answer</summary>

```python
def multiply(num1, num2):
  return num1 * num2
```

</details>

#### Functions Challenge 2

Write a function named `my_max` that gets a list of numbers as a parameter named `nums` and returns the max number in this list.

This would be the input and output example of this function:

```text
input: [12, 15, 18, 10, 11, 7]
output: 18
```

<details>
<summary>Answer</summary>

```python
def my_max(nums):
  curr_max = nums[0]
  for num in nums[1:]:
    if num > curr_max:
      curr_max = num
  return curr_max
```

</details>

## CheatSheet

### Jupyter Notebook Keybindings

- `Shift + Enter`: Run the cell and move to the next one.
- `Ctrl + Enter`: Run the cell but stay on the same cell.
- `Shift + M`: Merge the selected cell with the cell below.
- `Shift + Up/Down Arrow`: Extend cell selection above or below.
- `A`: Insert a new cell above the current cell.
- `B`: Insert a new cell below the current cell.
- `D`: Delete the selected cell.
- `Z`: Undo cell deletion.

### Lists CheatSheet

#### Length of the list

To check the length (size) of the lists use the `len` function:

```python
my_list = [1, 2, 3, 4]
print(len(list)) # 4
```

#### Iterating items

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

#### Adding new elements

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

#### Removing elements

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

#### Modifying Elements

Single elements can be modified with:

```python
my_list = ["Alireza", "Mohammad"]
my_list[1] = "Hamed"
print(my_list) # Alireza, Hamed
```

#### Selecting elements

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

#### Checking if element exists in a list

To check if an element is in the list:

```python
my_list = ["Alireza", "Mohammad", "Hamed"]
print("Alireza" in my_list) # True
print("Davood"in my_list) # False
```

### Dictionaries CheatSheet

#### Length of dictionary

Length of dictionary can be checked like a list:

```python
my_dict = {"Alireza": 12, "Mohammad": 23, "Hamed": 16}
print(len(my_dict)) # 3
```

#### Checking if key exists

Wether a key exists in a dict or not can be checked using the `in` operator:

```python
my_dict = {"Alireza": 12, "Mohammad": 23, "Hamed": 16}
if "Hamed" in my_dict:
  print(my_dict["Hamed"]) # prints 16
if "Navid" in my_dict:
  print(my_dict["Navid"]) # does not print
```

#### Iterating over dictionary

Iterating through keys of a dict:

```python
my_dict = {"Alireza": 12, "Mohammad": 23, "Hamed": 16}
for key in my_dict.keys():
  print(key) # Alireza, Mohammad, Hamed
```

Iterating through values of a dict:

```python
my_dict = {"Alireza": 12, "Mohammad": 23, "Hamed": 16}
for value in my_dict.values():
  print(value) # 12, 23, 16
```

Iterating through key/value pairs of a dict:

```python
my_dict = {"Alireza": 12, "Mohammad": 23, "Hamed": 16}
for key, value in my_dict.items():
  print(key, value) # Alireza, 12; Mohammad, 23; Hamed, 16
```

#### Removing an element

For removing an element use the `del` keyword:

```python
my_dict = {"Alireza": 12, "Mohammad": 23, "Hamed": 16}
del my_dict["Alireza"]
print(my_dict) # { "Mohammad": 23, "Hamed": 16 }
```

#### Merging Dictionaries (Python 3.9+)

For merging (combining) two dictionaries use the `|` operator:

```python
dict_1 = {"Alireza": 12, "Mohammad": 18}
dict_2 = {"Mohammad": 23, "Hamed": 16}
my_dict = dict_1 | dict_2
print(my_dict) # {"Alireza": 12, "Mohammad": 23, "Hamed": 16}
```

> [!NOTE]
> Notice how `Mohammad` exists in both dictionaries and is overrided by `dict_2` value. This
> is how mergin operator works. It overrides the values from from left-hand-side if a duplicate
> exists in the right-hand-side. If we did the reverse, (`dict_2 | dict_1`) then the value of
> `Mohammad` would be `18`.

## To Dos

- [ ] Strings Concatenation
- [ ] Strings Advanced
- [ ] Numpy Outline
- [ ] Numpy CheatSheet
- [ ] Pandas Outline
- [ ] Pandas CheatSheet
- [ ] Matplotlib + Seaborn Outline
- [ ] Matplotlib + Seaborn CheatSheet
