# Hold-to-Peek Desktop (v0.4.7)

Clean Windows bundle for the Hold-to-Peek desktop helper (gateway + UI + launcher).

```
.
├── assets/
├── config/
├── desktop/
├── server/
├── HoldToPeekLauncher.pyw
└── .gitignore
```

Virtual environments are created automatically on first launch, so they are not included here.

## Launching

1. Install Python 3.12 (64-bit).
2. Double-click `HoldToPeekLauncher.pyw` (or run `pythonw HoldToPeekLauncher.pyw`).
3. The splash loader will create venvs, install dependencies, and start both the FastAPI gateway and the Tkinter desktop.
4. In the desktop Settings tab, enter your OpenRouter API key and model before sending captures.

## Optional Update Manifest

If you want the in-app update reminder, host a JSON file (e.g. on GitHub) and point to it in `config/app.config.json`:

```json
"updates": {
  "version_url": "https://raw.githubusercontent.com/<user>/<repo>/main/version.json",
  "download_url": "https://github.com/<user>/<repo>/releases"
}
```

Example manifest:

```json
{
  "latest": "0.4.7",
  "download_url": "https://github.com/<user>/<repo>/releases/latest",
  "notes": "Optional release notes here"
}
```

The desktop client compares `latest` to its bundled version and enables the “Open download” button when a newer build exists.
