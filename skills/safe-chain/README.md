# Safe Chain Agent Skill

An agent skill that uses [Aikido Safe Chain](https://github.com/AikidoSec/safe-chain) to safely run package manager commands.

## Overview

This skill protects the system from malware and malicious packages by automatically routing package manager commands (npm, yarn, pnpm, pip, etc.) through safe-chain whenever a coding agent uses them.

## Prerequisites

Before using this skill, safe-chain must be installed:

```bash
# See the official documentation for installation
# https://github.com/AikidoSec/safe-chain
```

## Features

### Supported package managers

- **Node.js/JavaScript**: npm, npx, yarn, pnpm, pnpx, bun, bunx
- **Python**: pip, pip3, uv, poetry, pipx

### Behavior

When Claude Code installs or executes packages, this skill automatically:

1. Detects package manager commands
2. Prefixes the command with `safe-chain`
3. Executes the command through safe-chain
4. Runs real-time malware scanning

## Examples

### Installing packages

❌ **Normal execution (without the skill):**

```bash
npm install express
```

✅ **Using the Safe Chain skill:**

```bash
safe-chain npm install express
```

### Running packages

❌ **Normal execution (without the skill):**

```bash
npx create-react-app my-app
```

✅ **Using the Safe Chain skill:**

```bash
safe-chain npx create-react-app my-app
```

## Benefits

- **Malware protection**: Scans packages before installation
- **Supply chain defense**: Blocks malicious packages
- **Transparent**: Works without changing existing workflows
- **Automation**: Claude Code automatically uses the correct commands

## Skill location

This skill is placed in `../.agents/skills/safe-chain/`, and Claude Code automatically detects and uses it.

## License

This skill is built on top of the [Aikido Safe Chain](https://github.com/AikidoSec/safe-chain) project.

## References

- [Aikido Safe Chain GitHub](https://github.com/AikidoSec/safe-chain)
- [Claude Code Skills Documentation](https://code.claude.com/docs/en/skills)
- [Agent Skills Open Standard](https://github.com/anthropics/skills)

Sources:

- [Extend Claude with skills - Claude Code Docs](https://code.claude.com/docs/en/skills)
- [Agent Skills - Claude API Docs](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
- [Aikido Safe Chain](https://github.com/AikidoSec/safe-chain)
