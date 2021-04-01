# detect-secrets-test-data
This repo contains files having (faked) hard-coded secrets in them, such as passwords, API keys, etc...

Its purpose is to demonstrate several ways to use [Semgrep](https://github.com/returntocorp/semgrep/) to detect the secrets.

---
## Pre-commit hook
1. create a `.pre-commit-config.yaml` in the root of your project. (see [example](.pre-commit-config.yaml))
1. install the [pre-commit package](https://github.com/pre-commit/pre-commit): `$ python3 -m pip install pre-commit && pre-commit install`

![Screen Shot of terminal with git commit](https://user-images.githubusercontent.com/18272293/113333166-1bbb5400-92f0-11eb-89aa-4ee1be3b3f58.png)

---
## PR check
Create a GitHub workflow similar to [this one](.github/workflows/semgrep-pr-check.yml)
![Screen Shot of a failed PR](https://user-images.githubusercontent.com/18272293/113335314-c2085900-92f2-11eb-9a68-d55c7e8b7c54.png)

---
## Ad hoc scans right from GitHub UI
Create a GitHub workflow similar to [this one](.github/workflows/run-semgrep-baseline.yml)
Once in place, you can run the workflow right from GitHub web UI:
![Screen Shot showing manual run of a workflow](https://user-images.githubusercontent.com/18272293/113335535-11e72000-92f3-11eb-9691-8891c11a85ea.png)

Findings will show in the *Security* tab
![Screen Shot of GitHub security tab showing alerts](https://user-images.githubusercontent.com/18272293/113333954-1579a780-92f1-11eb-8d13-3cdc4246ec6b.png)
