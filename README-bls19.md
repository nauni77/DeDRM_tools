# decrypt DRM

## import problems

At the code the import of classes from the same directory will not work. A solution is to remove the `.` in front of the file name.

### import handling within same directory

How to handle imports from the same directory:
https://stackoverflow.com/questions/60593604/importerror-attempted-relative-import-with-no-known-parent-package

Since you are using Python 3.8 version, the imports work a little differently, but I think this should work:

Use either:

```python
from database import Database
#Database is the class
```

or try:

```python
import database.Database
```

lastly, this one is very secure and best practice possibly:

```python
from . import Database  
```

The '.' (dot) means from within the same directory as this __init__.py module grab

### import handling

One answer has an excellent example of how to use classes from modules:
https://stackoverflow.com/questions/16981921/relative-imports-in-python-3

## usage

To call the script `ineptpdf.py` or `ineptepub.py` you need to make the scripts executable.
For example, use:

```bash
chmod 755 DeDRM_plugin/ineptepub.py
```

## future TODOs

I think it would be a nice idear to create a class at the root which imports the package classes and which can be called directly.
