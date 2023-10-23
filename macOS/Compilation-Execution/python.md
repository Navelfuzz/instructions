# Python 

## Prerequisites

Install: [`Python Downloads`](https://www.python.org/downloads/)

Read at leisure or need: [`Python Documentation`](https://docs.python.org/3/)

Install: [`VS Code Python extension`](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

### Install a Python interpreter

CLI: `brew install python3`

### Create a virtual environment

Use a project-specific `virtual environment`. Once you activate that environment, any packages you then install are isolated from other environments, including the global interpreter environment, reducing many complications that can arise from conflicting package versions. You can create non-global environments in VS Code using Venv or Anaconda with Python: Create Environment.

<kbd>⇧</kbd> + <kbd>⌘</kbd> + <kbd>P</kbd> to open the Command Palette 

`Python: Create Environment` and `Python: Select Interpreter` to ensure the new environment (using Venv or Conda is using the right Interpreter)

Use `Python: Start REPL` to run one line at a time

### Debugging

Initialize the debugger, press F5. Select Python File, then use the play button to `Debug Python File in Terminal`. 

*Note that launch.json is the standard name for a file containing debugging configurations*

### Install and Use Packages

*Example*

```py
# Don't use with Anaconda distributions because they include matplotlib already.

# macOS
python3 -m pip install numpy

# Windows (may require elevation)
py -m pip install numpy

# Linux (Debian)
apt-get install python3-tk
python3 -m pip install numpy
```
