---
layout: default
title: Installation
nav_order: 1
---
# Installation
Numbers and brightness is available on PyPi and can be installed as follows:

```shell
pip install numbers_and_brightness
```
Numbers and brightness requires an active [python installation](https://www.python.org/downloads/).

### Graphical user interface
The package contains a GUI that can be accessed as follows:
#### Python
```python
from numbers_and_brightness.gui import nb_gui
nb_gui()
```

#### Command line
```shell
C:\Users\User> numbers_and_brightness
C:\Users\User> python -m numbers_and_brightness.gui
```

### Desktop shortcut
Additionally, a desktop (and start menu) shortcut can be created using the following command:
```shell
C:\Users\User> numbers_and_brightness --shortcut
```