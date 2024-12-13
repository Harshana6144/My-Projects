1) Prerequisites

You need to install python 3.12.0. For installation, you can visit the following link:
https://www.python.org/downloads/release/python-3120/

If you are using macOS, you can install python using pyenv:
```bash
pyenv install 3.12.0
```

Once you have installed python, you can create a virtual environment. Feel free to use any tool you like. I will be using pipenv for this tutorial.

```bash
pipenv --python 3.12.0
pipenv shell
```

2) Install dependencies

With pipenv:
```bash
pipenv install
```

For convenience, we have included a requirements.txt file. You can install the dependencies using pip:
```bash
pip install -r requirements.txt
```

3) Zipping files

```bash
pip install --platform=manylinux_2_17_x86_64 --only-binary=:all: --target ./python -r requirements.txt
cd python/
zip -r ../my_deployment_package.zip .
cd ../
zip -r my_deployment_package.zip app/
```