# Quickstart Guide

### 🪛 Develop

First install workstation

```shell
pyenv install -s 3.8.12
pyenv local 3.8.12
poetry lock
nox -s pre-commit -- install
nox -s pre-commit -- install --hook-type commit-msg
```
