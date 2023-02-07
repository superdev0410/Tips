# How to fix ssl certificate verify failed while install python packages using pip

## One time fix
Using below command we can install python packages one time.

```shell
pip install --trusted-host pypi.python.org --trusted-host pypi.org --trusted-host files.pythonhosted.org <package name>
```

## Permanant fix
To fix this error permanantly, follow these steps.

1. Make a "pip.ini" file in "C:/ProgramData/pip".
2. Write below text in "pip.ini"
```text
[global]
trusted-host = pypi.python.org
               pypi.org
               files.pythonhosted.org
```