# Screen Control for Ubuntu 24.04 LTS

Current version: `v0.1.0`

A lightweight screen automation helper for Ubuntu 24.04 LTS, designed to work with models that have native image understanding.

This project provides:
- Basic mouse and keyboard control
- Window focus utilities
- Screenshot capture for visual feedback loops

## Features

Supported commands:
- `screenshot`: take a full-screen screenshot and save to `~/openclaw_screens`
- `click`: left/right click, optional double click
- `move`: move mouse to a coordinate
- `drag`: drag from one coordinate to another
- `scroll`: scroll at a coordinate
- `type`: type text
- `type-guard`: verify/refocus target window before typing
- `hotkey`: common shortcuts (`copy`, `paste`, `undo`, etc.)
- `press`: press a single key with repeat/delay
- `focus`: focus a window by regex name
- `focus-probe`: inspect active window and mouse position
- `click-retry`: multi-point click retries around a base point
- `position`: get current mouse position

## Requirements

- Ubuntu 24.04 LTS (GUI session)
- `xdotool`
- `gnome-screenshot`
- Python 3.10+
- `pyautogui` (recommended; the script falls back to `xdotool` when possible)

## Install

```bash
sudo apt update
sudo apt install -y xdotool gnome-screenshot python3-pip
python3 -m pip install -r requirements.txt
```

## Usage

```bash
python3 screen_control.py screenshot
python3 screen_control.py click --position 500,400
python3 screen_control.py type --text "hello world"
python3 screen_control.py focus --name "Firefox|Chrome"
python3 screen_control.py position
```

Each command prints a JSON result (`ok`, `type`, and action-specific fields) for easy integration with agents and toolchains.

## Project Files

- `screen_control.py`: main CLI tool
- `SKILL.md`: referenced skill instructions
- `README.md`: project overview and setup
- `DISCLAIMER.md`: safety/legal disclaimers
- `LICENSE`: MIT license
- `CHANGELOG.md`: release history
- `CONTRIBUTING.md`: contribution process
- `CODE_OF_CONDUCT.md`: community behavior standard
- `.github/workflows/ci.yml`: CI checks for push/PR
- `CONTRIBUTORS.md`: contributor list

## Notes

- Run this tool only in a trusted desktop session.
- Test with non-critical windows/apps first.
- `pyautogui` may fail in headless environments; fallback behavior depends on available desktop tooling.

## Contributors

- [@Assangejulian](https://github.com/Assangejulian)
