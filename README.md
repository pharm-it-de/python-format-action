# python-format-action

This action runs in addition to other tasks defined inside the workflow. It will check if the files that have been modified in the PR are formatted using `black` and `isort`.
This action will fail if the files are not formatted OR if the checkout code is not present.
Checkout code is needed as to find the configuration files needded for `black` and `isort` to run on.
This avoids misaligned or unformatted code present in the repository.
This action checkout code , setup python and install the dependencies and run the `black` and `isort` commands.

### Usage

```yaml
...
   steps:
      - name: Format Code check
        uses: pharm-it-de/python-format-action@main
...
```
It is advised to use this action before any other aciton that runs tests or builds the code.
This will ensure code is formatted before running tests or building the code. 
Incase the code is not formatted, it will fail-fast and not run any other action.

### Inputs

#### "config":
The variable `config` stores the path to the configuration file. Default is `pyproject.toml` present at root.

If you want to use a different configuration file, you can specify the path to the configuration file using the `config` input.
Example: If the configuration file is present in the 'app' folder named 'testconfig.toml' then you can specify this as:

```yaml
...
 steps:
      - name: Format Code check
        uses: pharm-it-de/python-format-action@main
        with:
          config: ./app/testconfig.toml # filename with path
...
```

### Release Management
The creators of a community action have the option to use tags, branches, or SHA values to manage releases of the action. 
We are going to use 'main' branch in all of our repositories to use the latest version of *python-format-action*

[https://docs.github.com/en/actions/learn-github-actions/finding-and-customizing-actions#using-release-management-for-your-custom-actions]



