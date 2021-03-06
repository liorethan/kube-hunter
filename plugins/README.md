# Plugins

This folder contains modules that will load before any parsing of arguments by kube-hunter main module.

An example for using a plugin to add an argument:
```python
# example.py
from kube_hunter.conf import config

config.parser.add_argument('--exampleflag', action="store_true", help="enables active hunting")
```
What we did here was just add a file to the `plugins/` folder, import the parser, and adding an argument.

All plugins in this folder gets imported right after the main arguments are added, and right before they are getting parsed, so you can add an argument that will later be used in your [hunting/discovery module](../kube_hunter/README.md).
