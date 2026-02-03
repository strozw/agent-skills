# Agent Skills Collection

A personal collection of agent skills for enhancing Claude Code and other AI coding assistants with additional capabilities.

## Available Skills

### Safe Chain

Protects your system from malware and malicious packages by automatically routing package manager commands through [Aikido Safe Chain](https://github.com/AikidoSec/safe-chain).

**Features:**

- Automatic malware scanning for npm, yarn, pnpm, pip, and other package managers
- Real-time protection against supply chain attacks
- Transparent integration with existing workflows
- Supports Node.js/JavaScript and Python ecosystems

**Prerequisites:**

- [Aikido Safe Chain](https://github.com/AikidoSec/safe-chain) must be installed

[Learn more →](./skills/safe-chain/README.md)

## Installation

### Using npx skills add

You can install these skills using the [Vercel Skills](https://github.com/vercel-labs/skills) CLI:

```bash
# Install the safe-chain skill
npx skills add https://github.com/strozw/agent-skills/tree/main/skills/safe-chain
```

This command will:

1. Download the skill from this repository
2. Place it in your `~/.agents/skills/` directory
3. Make it available to Claude Code and other compatible agents

### Manual Installation

Alternatively, you can manually copy the skill directories:

```bash
# Clone this repository
git clone https://github.com/strozw/agent-skills.git

# Copy skills to your agents directory
cp -r agent-skills/skills/* ~/.agents/skills/
```

### Verifying Installation

After installation, verify that the skill is available:

```bash
# List installed skills
ls ~/.agents/skills/
```
