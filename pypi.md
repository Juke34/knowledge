# This is how you create the PyPI package and upload to the PyPI repo

* Prerequisite: 

    * Create an account
    * Install required packages:

```bash
pip install tqdm
pip install  twine
pip install setuptools wheel
```

* Step 1, build the source distribution

```bash
python setup.py sdist
```
* Step 2, build distribution  

```bash
python setup.py bdist_wheel --universal
```

* Step 3, upload  
```bash
python -m twine upload dist/* 
```

## Tips

Everytime you want to upload a new version you have to increment the version number within the setup.py file.
