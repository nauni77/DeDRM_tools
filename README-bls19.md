# decrypt e-books with DRM

This project will add a poetry to this project.
To install easily the needed dependencies and add with pipX the commands for execution to the system path.

## installation process

Precondition. Install all necessary components:

- a supported python version
- poetry
- pipX

Now you just need to execute two commands.
First build the release to your local dist directory.

```bash
poetry build
```

Now you can install with pipX the command to your system.

```bash
pipx install dist/dedrm_tools_git-10.0.9.dev12-py3-none-any.whl 
  installed package dedrm-tools-git 10.0.9.dev12, installed using Python 3.13.3
  These apps are now globally available
    - decryptEPUB
    - decryptPDF
done! ✨ 🌟 ✨
```

That's all.
Now you can call `decryptEPUB` and `decryptPDF` from the terminal.

## solved problems from original project

### import handling

One answer has an excellent example of how to use classes from modules:
https://stackoverflow.com/questions/16981921/relative-imports-in-python-3

At the code the import of classes from the same directory will not work.
The solution is to remove the `.` in front of the file name.

```python
from .utilities import SafeUnbuffered
from .argv_utils import unicode_argv
```

Or to import a Class from the same directory use this.

```python
from . import Database  
```

The `.` (dot) means from within the same directory as this `__init__.py` module grab.

### make the script files executable

To call the script `ineptpdf.py` or `ineptepub.py` you need to make the scripts executable.
For example, use:

```bash
chmod 755 DeDRM_plugin/ineptepub.py
chmod 755 DeDRM_plugin/ineptpdf.py
```

## future TODO/ enhancements

- If more people will need this it's very useful to create a property file to define the default options
  (`--output-direcectory` and `--userkey-file`).
  