# Workstation

![Tests](https://github.com/militu/workstation-cli/actions/workflows/tests.yml/badge.svg)
![Release](https://github.com/militu/workstation-cli/actions/workflows/release.yml/badge.svg)
![Python Version](https://img.shields.io/pypi/pyversions/workstation-cli)

### 🕮 Documentation

For detailed documentation (todo), please see [here](https://militu.github.io/workstation-cli/)

```shell
pip install workstation --user
```

### 🪛 Develop

First install workstation

```shell
pyenv install -s 3.8.12
pyenv local 3.8.12
poetry lock
nox -s pre-commit -- install
nox -s pre-commit -- install --hook-type commit-msg
```

Release

```shell
git switch --create release main
nox -s release -- --patch
git push origin release
```
