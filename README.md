# Hyperpyper:

Hypermodern Python project structure (circa 2020-09) with a focus on simplicity and minimalism.

## Source:

https://cjolowicz.github.io/posts/hypermodern-python-01-setup/

## Installation

You need a recent Linux, Unix, or Mac system with bash, curl and git for this tutorial.

### Install additional packages:

```sh
sudo apt update &&\
sudo apt install -y \
  make \
  build-essential \
  libssl-dev \
  zlib1g-dev \
  libbz2-dev \
  libreadline-dev \
  libsqlite3-dev \
  wget \
  curl \
  llvm \
  libncurses5-dev \
  libncursesw5-dev \
  xz-utils \
  tk-dev \
  libffi-dev \
  liblzma-dev \
  python-openssl \
  git
```

Clone the repository to your machine, and cd into it:

```sh
git clone https://github.com/School-Of-Gabri/hyperpyper
cd hyperpyper
```

### Install pyenv

```sh
curl https://pyenv.run | bash
```

Add the following lines to your ~/.bashrc:

```sh
export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

Open a new shell, or source ~/.bashrc in your current shell:

```sh
source ~/.bashrc
```

Install the Python build dependencies for your platform, using one of the commands listed in the official instructions. For example, on a recent Ubuntu this would be:

```sh
sudo apt update && sudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \
libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl git
```

### Install python

You’re ready to install the latest Python releases. This may take a while:

```sh
pyenv install 3.8.2
pyenv install 3.7.7
```

Make your fresh Pythons available inside the repository:

```sh
pyenv local 3.8.2 3.7.7
```

Congratulations! You have access to the latest and greatest of Python:

```
$ python --version
Python 3.8.2

$ python3.7 --version
Python 3.7.7
```

Python 3.8.2 is the default version and can be invoked as python, but both versions are accessible as python3.7 and python3.8, respectively.

### Install Poetry

Install Poetry:

```sh
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python
```

Open a new login shell or source ~/.poetry/env in your current shell:

```sh
source ~/.poetry/env
```

Initialize your Python project:

```sh
poetry init --no-interaction
```

This command will create a pyproject.toml file
This is the new Python package configuration file specified in PEP 517 and 518.

```toml
# pyproject.toml
[tool.poetry]
name = "hypermodern-python"
version = "0.1.0"
description = ""
authors = ["Your Name <you@example.com>"]

[tool.poetry.dependencies]
python = "^3.8"

[tool.poetry.dev-dependencies]

[build-system]
requires = ["poetry>=0.12"]
build-backend = "poetry.masonry.api"
```

There you go: One declarative file in TOML syntax, containing the entire package configuration. Let’s add some metadata to the package:

```toml
# pyproject.toml
[tool.poetry]
...
description = "The hypermodern Python project"
license = "MIT"
readme = "README.md"
homepage = "https://github.com/<your-username>/hypermodern-python"
repository = "https://github.com/<your-username>/hypermodern-python"
keywords = ["hypermodern"]
```

Poetry added a dependency on Python 3.8, because this is the Python version you ran it in. Support the previous release as well by changing this to Python 3.7:

```toml
[tool.poetry.dependencies]
python = "^3.7"
```
