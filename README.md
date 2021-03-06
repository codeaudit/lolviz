# lolviz

A simple Python data-structure visualization tool for **L**ists **O**f **L**ists, lists, dictionaries, and linked lists; primarily for use in Jupyter notebooks / presentations. It seems that I'm always trying to describe how data is laid out in memory to students. There are really great data structure visualization tools but I wanted something I could use directly via Python in Jupyter notebooks. The look and idea was inspired by the awesome [Python tutor](http://www.pythontutor.com).

There are currently four functions of interest that return `graphviz.files.Source` objects:

* `dictviz()`: A dictionary visualization<br><img src=images/dict.png width=50>
* `listviz()`: Horizontal list visualization<br><img src=images/list2.png width=300>
* `lolviz()`: List of lists visualization with the first list vertical and the nested lists horizontal.<br><img src=images/lol2.png width=400>
* `llistviz()`: Linked list visualization with horizontal orientation<br><img src=images/llist2.png width=140>

## Installation

```bash
$ pip install lolviz
```

## Usage

From within generic Python, you can get a window to pop up using the `render()` method:

```python
from lolviz import *
g = listviz(['hi','mom',{3,4},{"parrt":"user"}])
g.render(view=True) # render graphviz.files.Source object
```

<img src="images/list.png" width=200>

From within Jupyter notebooks you can avoid the `render()` call because Jupyter knows how to display `graphviz.files.Source` objects:

<img src=images/jupyter.png width=600>

You can look at a list of tuples as a list of list too:

<img src=images/lol3.png width=230>

Here's how to describe a hashtable with 3 elements in 2 different buckets:

<img src=images/hashtable.png width=350>

If you want the graphviz/dot source, use `source` field of returned `graphviz.files.Source` object.

For 1.1, I added linked lists. Figuring out that layout was annoying. You're welcome. ;)

<img src="images/llist.png" width=500>

Here's an example of specifying lambda functions to extract values from nodes:

<img src="images/tuplellist.png" width=450>
