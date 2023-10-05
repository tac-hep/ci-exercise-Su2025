APC 524 - Homework 3

In this repo is a basic project, with some code in `src/unc/__init__.py` and some tests in `tests/`. The
main code has no dependencies other than Python 3.8+, while the tests require `pytest` and `uncertainties`.

Add the following files:

* `pyproject.toml`: Setup a basic project. Include at least:
    * A build backend. `hatchling` recommended, but any one should work.
    * A project table with at least name, version, and requires-python.
    * An project.optional-dependencies table with a `test` extra (dependencies listed above).
* `.pre-commit-config.yaml`: Add at least the following checks:
    * Basic checks (pre-commit/pre-commit-hooks) with at least `trailing-whitespace`.
    * Black
    * Ruff with at least the default checks (E, F, W), bugbear (B), isort (I), Ruff-specific (RUF), and PyUpgrade (UP).
* `noxfile.py`: Add at least one session that runs your tests. Optionally, you can add a formatting session or anything else useful, but at least include:
    * `tests`: `nox -s tests` should run your tests. Use the `tests` extra defined above, do not list dependencies explicitly here.
* `.github/workflow/ci.yml`: Add two jobs.
    - Format: this should run pre-commit. Manually implement, or use the pre-commit action, or nox. Doesn't matter how you do it, but it should show the diff on failure.
    - Tests: run your tests. Either through nox or by hand, but again, use the `tests` extra, don't list `pytest`, etc. Use `ubuntu-latests` and run both minimum and maximum supported Pythons (3.8 and 3.12), either with a matrix, or with nox, or both.

As you add these, verify it works at each step. There might be mistakes in the code that you will expose with these checks, fix them if needed and list each fix in `CHANGELOG.md`. You do not need to list automatic formatting changes, just bugfixes.
