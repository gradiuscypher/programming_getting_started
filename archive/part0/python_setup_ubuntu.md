# Setting up your Python Development Environment - Ubuntu Linux
## Introduction
Python is an interpreted programming language, which means any time we want to execute our Python scripts, we’ll be using the Python interpreter. Ubuntu comes with Python2.7 and Python3 installed by default. As of Ubuntu 16.04.3, Python2.7 is still the default interpreter. My suggestion would be to use Python3 for any new project moving forward. Many developers are writing code for Python3 which means you’ll likely find the most support with version 3 or higher.

## Python Virtual Environments
When working with other Python libraries, you’ll be installing those libraries on your system. Without proper organization your system will become a mess of libraries that you may or may not need any longer. That’s where virtual environments come into play. Virtual environments create a directory local to your project where you can maintain the most recent libraries required for your project without making your system Python libraries a mess.

### Setting Up python-virtualenv
```sh
sudo apt update
sudo apt install python-virtualenv
```

### Using python-virtualenv
These commands will be executed in your project folder

#### Creating and activating python-virtualenv
These commands will create a virtual environment based on the Python version provided with the `-p` flag. The secondary command tells your command shell to use the virtual environment as your default Python interpreter and your default pip tool. Running `python` or `pip` will execute the binaries from this virtual environment.

Creating a Python3 virtual environment:
```sh
virtualenv -p /usr/bin/python3 venv3
source venv3/bin/activate
```

Creating a Python2.7 virtual environment:
```sh
virtualenv -p /usr/bin/python2.7 venv2
source venv2/bin/activate
```

#### Installing Python packages with pip
Python virtual environments come with the Python package manager, pip, by default. To install a package with pip, just use pip and the package name. The example below will install the requests package.

```sh
pip install requests
```

#### Saving a list of required packages and installing from that list
This command will save the name of installed pip packages to a file to allow for easy setup later.

```sh
pip freeze > requirements.txt
```

This command will install the required packages that aren't currently installed.
```sh
pip install -r requirements.txt
```

#### Exiting the Python virtual environment
This will change your shell settings back to default and deactivates the Python virtual environment.
```sh
deactivate
```

## Python Editors
Code editors are always personal preference. I’ve found that having a feature-rich editor makes learning and interacting with a language much easier. Features like predictive editing and syntax highlighting, along with integration into things like debuggers and version control are a world of help.

Text editors with plugin systems will often have language support. I’m not familiar these systems as I’ve found that I really enjoy using the Python editor “Pycharm” from Jetbrains. They provide a community version for free, and it can be found [here](https://www.jetbrains.com/pycharm/download/#section=linux). You can also install Pycharm on Ubuntu Linux using the snap package manager with this command:

```sh
sudo snap install pycharm-community --classic
```

It’s best to find what works for you, and don’t be afraid of installing multiple editors to find what you like.
