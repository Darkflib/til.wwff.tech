+++
date = '2024-12-02T21:32:59Z'
draft = false
title = 'Uv Is Cool'
+++

## Uv is actually pretty cool and fast

Most people are familiar with pip in Python. It's a package manager that lets you install packages from the Python Package Index (PyPI)... and elsewhere.

The one drawback is that pip is slow. It's written in Python, and it's not the fastest thing in the world.

Enter Uv. Uv is a package manager that is written in Rust, and it's fast. It's really fast.

It also integrates nicely with pyproject.toml, so you can use it instead of Poetry or Pipenv if you want.

You can install Uv by running (on mac):

```bash
brew install uv
```

And then you can use it like this:

```bash
uv add requests
```

And that's it! You've installed the requests package, and it is now available to use in your Python project and present in your pyproject.toml file.

```text
Usage: uv [OPTIONS] <COMMAND>

Commands:
  run      Run a command or script
  init     Create a new project
  add      Add dependencies to the project
  remove   Remove dependencies from the project
  sync     Update the project's environment
  lock     Update the project's lockfile
  export   Export the project's lockfile to an alternate format
  tree     Display the project's dependency tree
  tool     Run and install commands provided by Python packages
  python   Manage Python versions and installations
  pip      Manage Python packages with a pip-compatible interface
  venv     Create a virtual environment
  build    Build Python packages into source distributions and wheels
  publish  Upload distributions to an index
  cache    Manage uv's cache
  self     Manage the uv executable
  version  Display uv's version
  help     Display documentation for a command
  ```
