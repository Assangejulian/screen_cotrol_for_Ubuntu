# Contributing Guide

Thanks for your interest in improving this project.

## Development setup

1. Use Ubuntu 24.04 LTS with a graphical desktop session.
2. Install system dependencies:

```bash
sudo apt update
sudo apt install -y xdotool gnome-screenshot python3-pip
```

3. Create a virtual environment and install Python dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Contribution workflow

1. Fork the repository and create a feature branch.
2. Keep changes focused and small.
3. Run local checks before opening a pull request:

```bash
python3 -m py_compile screen_control.py
python3 screen_control.py --help
```

4. Open a PR with:
- What changed
- Why it changed
- How you tested it

## Coding rules

- Keep CLI JSON output stable (`ok`, `type`, and command-specific fields).
- Prefer backward-compatible changes for existing commands.
- Add or update documentation for behavior changes.

## Reporting bugs

Please include:
- Ubuntu version
- Desktop environment
- Command used
- Full JSON output
- Any error logs
