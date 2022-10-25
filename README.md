# python-format-action

This action runs in addition to other tasks defined inside the workflow. It will check if the files that have been modified in the PR are formatted using `black` and `isort`.
This action will fail if the files are not formatted OR if the checkout code is not present.
Checkout code is needed as to find the configuration files needded for `black` and `isort` to run on.
This avoids misaligned or unformatted code present in the repository.



