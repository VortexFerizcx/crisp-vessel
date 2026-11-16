# crisp-vessel

![CI](https://img.shields.io/github/actions/workflow/status/VortexFerizcx/crisp-vessel/ci.yml?branch=main&label=CI) ![Python](https://img.shields.io/badge/python-3.9+-blue) ![License](https://img.shields.io/github/license/VortexFerizcx/crisp-vessel?color=blue) ![Version](https://img.shields.io/badge/version-0.9.3-green)

crisp-vessel is a terminal-first tool for batch text operations. It reads input files, processes each line with configurable rules (trim whitespace, uppercase, add line numbers), and outputs results to a file or stdout. Built with Click for argument parsing and Rich for colored output.

## Features

- Cross-platform: tested on Linux, macOS, and Windows
- Rich terminal output with colored, structured formatting and progress indicators
- Pytest test suite with coverage for core processing logic
- Stdin support for piping: `cat data.txt | crisp-vessel --output -`
- Line-by-line text processing with configurable trim, uppercase, and line numbering

## Prerequisites

- Python 3.9 or higher
- pip or pipx for installation

## Installation

```bash
pip install crisp-vessel
# or
pipx install crisp-vessel
# or from source
git clone https://github.com/VortexFerizcx/crisp-vessel.git
cd crisp-vessel && pip install -e .
```

## Usage

```bash
# Process a file with default settings
crisp-vessel --input data.txt --output result.txt

# Use a YAML config file and verbose logging
crisp-vessel --config config.yaml --verbose

# Pipe from stdin
cat data.txt | crisp-vessel --output -

# Show help and version
crisp-vessel --help
crisp-vessel --version
```

The processing pipeline reads each line, trims whitespace, optionally uppercases, and adds line numbers:
```
0001 | Hello World
0002 | Foo Bar
```

## Project Structure

```
crisp-vessel/
├── src/crisp_vessel/
│   ├── __init__.py
│   └── cli.py
├── tests/
│   └── test_cli.py
├── pyproject.toml
├── README.md  LICENSE  CHANGELOG.md  CONTRIBUTING.md  CODE_OF_CONDUCT.md
├── .github/
│   ├── workflows/ci.yml
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   └── PULL_REQUEST_TEMPLATE.md
└── .gitignore
```

## Running Tests

```bash
pytest
# with coverage report
pytest --cov=src --cov-report=term-missing
```

## FAQ

**Is this production-ready?**
Yes, crisp-vessel includes tests, CI/CD, and documentation. However, you should review the code and adapt it to your specific needs before deploying.

**Can I use this in my project?**
Yes, crisp-vessel is licensed under the GPL-3.0. See the [LICENSE](LICENSE) file for details.

**How do I report a bug?**
Please [open an issue](https://github.com/VortexFerizcx/crisp-vessel/issues/new?template=bug_report.md) using the bug report template.

**How do I request a feature?**
Please [open an issue](https://github.com/VortexFerizcx/crisp-vessel/issues/new?template=feature_request.md) using the feature request template.

**How can I contribute?**
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

Quick start:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Make your changes and run tests (see [Running Tests](#running-tests) above)
4. Commit with a clear message: `git commit -am 'Add: my feature'`
5. Push to your fork: `git push origin feature/my-feature`
6. Open a Pull Request

Please ensure all tests pass before submitting a pull request.

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for a list of changes and version history.

## License

This project is licensed under the GPL-3.0 -- see the [LICENSE](LICENSE) file for details.

Copyright (c) 2026 omar novak.
