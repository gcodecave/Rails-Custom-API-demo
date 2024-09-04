![Python package](https://github.com/gitpython-developers/GitPython/workflows/Python%20package/badge.svg)
[![Documentation Status](https://readthedocs.org/projects/gitpython/badge/?version=stable)](https://readthedocs.org/projects/gitpython/?badge=stable)
[![Packaging status](https://repology.org/badge/tiny-repos/python:gitpython.svg)](https://repology.org/metapackage/python:gitpython/versions)

Aspects
Routing: Defines how incoming requests are matched to specific functions or handlers.
Serialization/Deserialization: Converts data between different formats, such as JSON or XML.
Validation: Ensures that incoming data meets specified criteria before processing.
Authentication & Authorization: Manages user identities and permissions.
Error Handling: Provides mechanisms to handle and respond to errors gracefully.
Documentation: Generates documentation for the API to help users understand how to interact with it.
Testing: Offers tools and methodologies for testing API endpoints.
Popular API Frameworks
For JavaScript/Node.js
Express.js: Minimalist framework that provides robust features for web and mobile applications.
Koa.js: Developed by the creators of Express, focusing on modern JavaScript and async/await.
NestJS: A progressive framework for building scalable server-side applications, leveraging TypeScript and Angular-inspired architecture.
For Python
Django REST Framework (DRF): A powerful and flexible toolkit for building Web APIs on top of Django.
FastAPI: A modern, fast (high-performance), web framework for building APIs with Python 3.7+ based on standard Python type hints.
Flask: A micro-framework that can be extended with libraries to handle APIs, often used with Flask-RESTful.
Ensure testing libraries are installed. This is taken care of already if you installed with:


DEVELOPMENT STATUS
This project is in maintenance mode, which means that

…there will be no feature development, unless these are contributed
…there will be no bug fixes, unless they are relevant to the safety of users, or contributed
…issues will be responded to with waiting times of up to a month


REQUIREMENTS
GitPython needs the git executable to be installed on the system and available in your PATH for most operations. If it is not in your PATH, you can help GitPython find it by setting the GIT_PYTHON_GIT_EXECUTABLE=<path/to/git> environment variable.

Git (1.7.x or newer)
Python >= 3.7
The list of dependencies are listed in ./requirements.txt and ./test-requirements.txt. The installer takes care of installing them for you.

INSTALL
GitPython and its required package dependencies can be installed in any of the following ways, all of which should typically be done in a virtual environment.

From PyPI
To obtain and install a copy from PyPI, run:

contact for full Ver.
gcodecave@gmail.com

```sh
pip install -e ".[test]"
```

If you had installed with a command like `pip install -e .` instead, you can still run
the above command to add the testing dependencies.

#### Test commands

To test, run:

```sh
pytest
```

To lint, and apply some linting fixes as well as automatic code formatting, run:

```sh
pre-commit run --all-files
```

This includes the linting and autoformatting done by Ruff, as well as some other checks.

To typecheck, run:

```sh
mypy
```

#### CI (and tox)

Style and formatting checks, and running tests on all the different supported Python versions, will be performed:

- Upon submitting a pull request.
- On each push, *if* you have a fork with GitHub Actions enabled.
- Locally, if you run [`tox`](https://tox.wiki/) (this skips any Python versions you don't have installed).

#### Configuration files

Specific tools are all configured in the `./pyproject.toml` file:

- `pytest` (test runner)
- `coverage.py` (code coverage)
- `ruff` (linter and formatter)
- `mypy` (type checker)

Orchestration tools:

- Configuration for `pre-commit` is in the `./.pre-commit-config.yaml` file.
- Configuration for `tox` is in `./tox.ini`.
- Configuration for GitHub Actions (CI) is in files inside `./.github/workflows/`.

### Contributions

Please have a look at the [contributions file][contributing].

### INFRASTRUCTURE

- [User Documentation](http://gitpython.readthedocs.org)
- [Questions and Answers](http://stackexchange.com/filters/167317/gitpython)
- Please post on Stack Overflow and use the `gitpython` tag
- [Issue Tracker](https://github.com/gitpython-developers/GitPython/issues)
  - Post reproducible bugs and feature requests as a new issue.
    Please be sure to provide the following information if posting bugs:
    - GitPython version (e.g. `import git; git.__version__`)
    - Python version (e.g. `python --version`)
    - The encountered stack-trace, if applicable
    - Enough information to allow reproducing the issue

### How to make a new release

1. Update/verify the **version** in the `VERSION` file.
2. Update/verify that the `doc/source/changes.rst` changelog file was updated. It should include a link to the forthcoming release page: `https://github.com/gitpython-developers/GitPython/releases/tag/<version>`
3. Commit everything.
4. Run `git tag -s <version>` to tag the version in Git.
5. _Optionally_ create and activate a [virtual environment](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#creating-a-virtual-environment). (Then the next step can install `build` and `twine`.)
6. Run `make release`.
7. Go to [GitHub Releases](https://github.com/gitpython-developers/GitPython/releases) and publish a new one with the recently pushed tag. Generate the changelog.

### Projects using GitPython

- [PyDriller](https://github.com/ishepard/pydriller)
- [Kivy Designer](https://github.com/kivy/kivy-designer)
- [Prowl](https://github.com/nettitude/Prowl)
- [Python Taint](https://github.com/python-security/pyt)
- [Buster](https://github.com/axitkhurana/buster)
- [git-ftp](https://github.com/ezyang/git-ftp)
- [Git-Pandas](https://github.com/wdm0006/git-pandas)
- [PyGitUp](https://github.com/msiemens/PyGitUp)
- [PyJFuzz](https://github.com/mseclab/PyJFuzz)
- [Loki](https://github.com/Neo23x0/Loki)
- [Omniwallet](https://github.com/OmniLayer/omniwallet)
- [GitViper](https://github.com/BeayemX/GitViper)
- [Git Gud](https://github.com/bthayer2365/git-gud)

### LICENSE

[3-Clause BSD License](https://opensource.org/license/bsd-3-clause/), also known as the New BSD License. See the [LICENSE file][license].

One file exclusively used for fuzz testing is subject to [a separate license, detailed here](./fuzzing/README.md#license).
This file is not included in the wheel or sdist packages published by the maintainers of GitPython.

[contributing]: https://github.com/gitpython-developers/GitPython/blob/main/CONTRIBUTING.md
[license]: https://github.com/gitpython-developers/GitPython/blob/main/LICENSE
