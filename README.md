# spacify-pre-commit

The [prek](https://github.com/j178/prek) and [pre-commit](https://pre-commit.com) hook for
[spacify](https://github.com/avanserv/spacify), the formatter for the vertical rhythm of Python
code. It installs spacify's prebuilt wheel from PyPI, so you don't need a Rust toolchain.

Put it after `ruff-format`, so spacify sees ruff's line wrapping:

```yaml
repos:
  - repo: https://github.com/astral-sh/ruff-pre-commit
    rev: v0.1.1
    hooks:
      - id: ruff-format
  - repo: https://github.com/avanserv/spacify-pre-commit
    rev: v0.1.1
    hooks:
      - id: spacify
```

Pass `args: [--check]` to report files instead of rewriting them. spacify reads its configuration
from `pyproject.toml`; see its [README](https://github.com/avanserv/spacify#configuration).

This repository holds no code. Each spacify release updates the pinned version here and tags this
repository with the same version, so `prek autoupdate` picks it up.
