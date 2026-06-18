# Playwright Python Tool

A lightweight browser automation starter kit built with [Playwright](https://playwright.dev/). Use it to write end-to-end tests, scrape dynamic websites, and automate repetitive browser tasks across Chromium, Firefox, and WebKit.

[![Playwright](https://img.shields.io/badge/Playwright-1.57.0-2EAD33?logo=playwright&logoColor=white)](https://playwright.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](LICENSE)

---

## Overview

**Playwright Python Tool** is a ready-to-use project scaffold for browser automation. It ships with Playwright pre-installed so you can start scripting interactions, capturing screenshots, and validating web applications without extra setup.

| Item | Details |
|------|---------|
| **Repository** | [PlaywritePython-tool](https://github.com/Sandeepkumar13M/PlaywritePython-tool) |
| **Author** | [Sandeepkumar13M](https://github.com/Sandeepkumar13M) |
| **Playwright version** | `^1.57.0` |
| **Package manager** | npm |

---

## Features

- **Cross-browser support** — Chromium, Firefox, and WebKit out of the box
- **Headless or headed mode** — run tests in CI or watch the browser live
- **Auto-waiting** — Playwright waits for elements to be actionable before interacting
- **Portable archive** — `my-playwright-tools.zip` included for offline sharing
- **Python-ready** — add Playwright Python scripts alongside the Node.js setup

---

## Project Structure

```
Playwright-Python-Tool/
├── README.md
├── my-playwright-tools.zip          # Portable copy of the project
└── my-playwright-tools/
    ├── package.json                 # Project metadata & dependencies
    ├── package-lock.json
    ├── google_test.py               # Python test script (starter)
    └── node_modules/                # Installed dependencies
```

---

## Prerequisites

Before you begin, make sure you have:

- **Node.js** 18 or later — [Download Node.js](https://nodejs.org/)
- **npm** (comes with Node.js)
- **Git** — to clone this repository

Optional (for Python scripts):

- **Python** 3.8+ — [Download Python](https://www.python.org/downloads/)
- **Playwright for Python** — install with `pip install playwright`

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Sandeepkumar13M/PlaywritePython-tool.git
cd PlaywritePython-tool
```

### 2. Install dependencies

If `node_modules` is not present, install packages from the project folder:

```bash
cd my-playwright-tools
npm install
```

### 3. Install Playwright browsers

Download the browser binaries Playwright needs:

```bash
npx playwright install
```

On Linux you may also need system dependencies:

```bash
npx playwright install-deps
```

---

## Usage

### Node.js — quick smoke test

Create a file such as `my-playwright-tools/example.js`:

```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch({ headless: true });
  const page = await browser.newPage();

  await page.goto('https://playwright.dev/');
  console.log(await page.title());

  await browser.close();
})();
```

Run it:

```bash
node example.js
```

### Python — starter script

Install Playwright for Python (one-time):

```bash
pip install playwright
playwright install
```

Example `google_test.py`:

```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=True)
    page = browser.new_page()
    page.goto("https://www.google.com")
    print(page.title())
    browser.close()
```

Run it:

```bash
python google_test.py
```

### Run Playwright CLI tools

```bash
npx playwright --help
npx playwright codegen https://example.com   # Record actions & generate code
npx playwright test                          # Run tests (after adding a test suite)
```

---

## Common Commands

| Command | Description |
|---------|-------------|
| `npm install` | Install Node.js dependencies |
| `npx playwright install` | Download browser binaries |
| `npx playwright codegen <url>` | Record browser actions and export code |
| `npx playwright test` | Run Playwright Test suite |
| `npx playwright show-report` | Open the HTML test report |

---

## Configuration

Edit `my-playwright-tools/package.json` to add npm scripts, for example:

```json
{
  "scripts": {
    "test": "playwright test",
    "codegen": "playwright codegen"
  }
}
```

For advanced settings (timeouts, base URL, reporters), add a `playwright.config.js` or `playwright.config.ts` in `my-playwright-tools/`.

---

## Troubleshooting

### `playwright: command not found`

Use `npx` to run Playwright without a global install:

```bash
npx playwright install
```

### Browsers fail to launch on Linux

Install system libraries:

```bash
npx playwright install-deps
```

### Git "dubious ownership" on Windows

If the repo folder was created under another user account:

```bash
git config --global --add safe.directory "D:/PLAYWRIGHT TEST"
```

---

## Contributing

Contributions are welcome. To propose a change:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-change`)
3. Commit your changes (`git commit -m "Add my change"`)
4. Push to the branch (`git push origin feature/my-change`)
5. Open a Pull Request

---

## License

This project is licensed under the **ISC License**. See `my-playwright-tools/package.json` for details.

---

## Links

- [Playwright Documentation](https://playwright.dev/docs/intro)
- [Playwright Python Docs](https://playwright.dev/python/docs/intro)
- [GitHub Repository](https://github.com/Sandeepkumar13M/PlaywritePython-tool)

---

<p align="center">
  Built with Playwright by <a href="https://github.com/Sandeepkumar13M">Sandeepkumar13M</a>
</p>
