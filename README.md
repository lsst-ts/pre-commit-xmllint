# xmllint pre-commit hook

This is a hook feeding all files through xmllint. '*xmllint*' command is
assumed to exists in command path (*please use alias if you don't want to have
command in a path, or modify the hook*).

## Operation

*format-xmllint* overwrites malformed files with reformated file.

~check-xmllint~ hook runs xmllint --format and fails if any modified file
doesn't match xmllint --format output. We don't advise to use that option.

## Setting up

Create or add following to .pre-commit-config.yaml in repository you would like to check:

```yaml
repos:
  - repo: https://github.com/lsst-ts/pre-commit-xmllint
    rev: v1.0.0
    hooks:
      - id: format-xmllint
```

and install the hook:

```sh
pre-commit install
```
