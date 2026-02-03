---
name: safe-chain
description: Enforce malware scanning by routing package manager commands through safe-chain
---

# Safe Chain Skill

This skill improves security by automatically routing package manager commands through safe-chain.

## Covered commands

When running the following commands, you must **always** route them through safe-chain:

### Node.js/JavaScript

- `npm` -> `safe-chain npm`
- `npx` -> `safe-chain npx`
- `yarn` -> `safe-chain yarn`
- `pnpm` -> `safe-chain pnpm`
- `pnpx` -> `safe-chain pnpx`
- `bun` -> `safe-chain bun`
- `bunx` -> `safe-chain bunx`

### Python

- `pip` -> `safe-chain pip`
- `pip3` -> `safe-chain pip3`
- `uv` -> `safe-chain uv`
- `uvx` -> `safe-chain uv tool run`
- `poetry` -> `safe-chain poetry`
- `pipx` -> `safe-chain pipx`

## Execution rules

1. **Required for package installs and updates**
   - ✅ Correct: `safe-chain npm install express`
   - ❌ Incorrect: `npm install express`

2. **Required for running scripts**
   - ✅ Correct: `safe-chain npx create-react-app my-app`
   - ❌ Incorrect: `npx create-react-app my-app`

3. **Required for global installs**
   - ✅ Correct: `safe-chain npm install -g typescript`
   - ❌ Incorrect: `npm install -g typescript`

4. **Required for updating existing dependencies**
   - ✅ Correct: `safe-chain npm update`
   - ❌ Incorrect: `npm update`

## Verification

To confirm that safe-chain is working correctly:

```bash
# Test a Node.js package
safe-chain npm install safe-chain-test

# Test a Python package
safe-chain pip3 install safe-chain-pi-test

# Check the safe-chain version
safe-chain --version
```

## Exceptions

The following commands do not need to go through safe-chain:

- `npm run <script>` (runs scripts in package.json)
- `npm test`
- `npm start`
- `npm --version` (version check only)

## Important note

WARNING: **While this skill is enabled, do not execute package manager commands directly.**

safe-chain scans installed packages in real time and protects against malware and malicious code. Using this skill significantly reduces the risk of supply chain attacks.
