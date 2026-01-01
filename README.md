# Auto NPM Test Action

A "batteries-included" GitHub Action to set up Node.js, install dependencies, and run your tests with zero-config.

## 🚀 Why use this?

Most Node.js workflows require the same boilerplate over and over. This action reduces that to a single step while remaining flexible:

* **Smart Versioning:** REQUIRED: Automatically detects the required Node.js version from your `package.json` (`engines` field).
* **Built-in Caching:** Automatically caches `node_modules` to make your CI runs lightning fast.

## 📦 Usage

Create or update a file at `.github/workflows/test.yml`:

```yaml
name: CI Tests

on: [pull_request]

jobs:
  run-tests:
    uses: rubengmurray/npm-test-action/.github/workflows/test.yml@main
    with:
      test-command: 'test:unit'  # Optional: defaults to 'test'

```

# Prerequisites

Ensure your `package.json` includes an `engines` field specifying the Node.js version, for example:

```json
{
  "engines": {
    "node": "20.12.2"
  },
}