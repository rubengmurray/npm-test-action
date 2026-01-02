# Auto NPM Test Action

A "batteries-included" GitHub Action to set up Node.js, install dependencies, and run your tests with zero-config.

## 🚀 Why use this?

Speed & Convenience!

- **Less Boilerplate:** Just check this README, and you're done.
* **Smart Versioning:** Automatically detects the required Node.js version from your `package.json` (`engines` field).
* **Built-in Caching:** Automatically caches `node_modules` to make your CI runs 30-40s faster!

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
      skip-cache: false # Optional: prevent caching (can be used to avoid any potential cache issues)
      skip-draft-prs: true # Optional: skip running tests on draft PRs (graceful if not PR based)

```

# Prerequisites

Ensure your `package.json` includes an `engines` field specifying the Node.js version, for example:

```json
{
  "engines": {
    "node": "20.12.2"
  },
}