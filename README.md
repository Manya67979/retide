# retide

Opinionated log housekeeping tool with dry-run support

Started as a weekend hack, grew on me.

## Usage

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## What it does

- Exit codes friendly for cron and CI
- Dry-run mode shows what would happen, touches nothing
- Scan directories for log files by glob pattern
- Archive matched logs into a timestamped .tar.gz
- Filter by age (--older-than) or size (--larger-than)

## Getting started

```bash
pip install -r requirements.txt
python -m logwash --help
```

## Project structure

```text
├── .github/
│   └── workflows/
│       └── ci.yml
├── docs/
│   ├── configuration.md
│   ├── development.md
│   ├── roadmap.md
│   └── usage.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   └── errors.py
├── tests/
│   └── test_cli.py
├── .editorconfig
├── .gitattributes
├── .gitignore
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── pyproject.toml
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## Changelog

- `0.1.1` - fix edge case in argument parsing
- `0.1.0` - first working version
