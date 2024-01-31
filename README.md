#  pyco-apps.github.io

Company website to browse crafted software.

# developer

## get-started

- require [poetry](https://python-poetry.org/)
- require python with the appropriate version specified in [pyproject.toml](pyproject.toml)

```shell
git clone https://github.com/pyco-apps/pyco-apps.github.io.git
cd pyco-apps.github.io
poetry install
```

- work should be done on a `dev` branch

previewing the build website :

```shell
mkdocs serve --watch ./overrides
```

- once satisfied with your change create a pull-request to `main` branch.
- merging to `main` will automatically trigger a deployment of the website.