<h1 align="center"> widgetastic.patternfly5 </h1>

<p align="center">
    <a href="https://pypi.org/project/widgetastic.patternfly5/">
    <img alt="Python Versions" src="https://img.shields.io/pypi/pyversions/widgetastic.patternfly5.svg?style=flat">
    </a>
    <a href="https://pypi.org/project/widgetastic.patternfly5/#history">
    <img alt="PyPI version" src="https://badge.fury.io/py/widgetastic.patternfly5.svg">
    </a>
    <a href="https://codecov.io/github/RedHatQE/widgetastic.patternfly5">
      <img src="https://codecov.io/github/RedHatQE/widgetastic.patternfly5/graph/badge.svg?token=cWuTXniIPm"/>
    </a>
    <a href="https://github.com/RedHatQE/widgetastic.patternfly5/actions/workflows/tests.yaml">
    <img alt="github actions" src="https://github.com/RedHatQE/widgetastic.patternfly5/actions/workflows/tests.yaml/badge.svg">
    </a>
    <a href="https://github.com/RedHatQE/widgetastic.patternfly5/blob/main/LICENSE">
    <img alt="License: GPLv3" src="https://img.shields.io/github/license/RedHatQE/widgetastic.patternfly5">
    </a>
    <a href="https://pypi.org/project/black">
    <img alt="Code style: black" src="https://img.shields.io/badge/code%20style-black-000000.svg">
    </a>
</p>

This library offers Widgetastic Widgets for [PatternFly v5](https://www.patternfly.org/), serving as an extended
itteration of [widgetastic.patternfly4](https://github.com/RedHatQE/widgetastic.patternfly4).


### Components:
- [alert](https://www.patternfly.org/components/alert)
- [breadcrumb](https://www.patternfly.org/components/breadcrumb)
- [title](https://www.patternfly.org/components/title)

### Charts:
- [bullet-chart](https://www.patternfly.org/charts/bullet-chart)


### Contribution guide

```bash
# clone the repo
git clone https://github.com/RedHatQE/widgetastic.patternfly5.git
cd widgetastic.patternfly5

# create a virtual environment
python3 -m venv .venv_pfy5
source .venv_pfy5/bin/activate

# update pip and its friends
pip install -U pip setuptools wheel

# install the package in editable mode
pip install -e .[dev]
pre-commit install
```

### Testing

The library has selenium tests that are performed against [Patternfly React docs](https://patternfly-react-main.surge.sh).
It's also configured to run the tests every time when a new version of that page is released.

Tests spawn a container from official selenium image - [selenium/standalone-{chrome/firefox}](https://hub.docker.com/u/selenium).
We can check local runs via vnc `http://localhost:7900`

**Note:** Tests use `podman` to manage containers. Please install it before running.

It's possible to run tests in parallel to speed up the execution. Make sure that you have **xdist** python plugin installed.

Use `-n` key to specify a number
of workers:

```bash
BROWSER=firefox pytest -v testing -n 4
```