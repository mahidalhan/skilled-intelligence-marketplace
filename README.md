# Skilled Intelligence

**Claude Code plugin marketplace for intelligent development tools.**

## Install

```bash
# Add marketplace
/plugin marketplace add mahidalhan/skilled-intelligence-marketplace

# Install plugins (choose what you need)
/plugin install code-intelligence@skilled-intelligence
/plugin install skill-tools@skilled-intelligence
/plugin install learning-tools@skilled-intelligence
/plugin install creative-tools@skilled-intelligence
/plugin install workflow-tools@skilled-intelligence
/plugin install git-tools@skilled-intelligence
```

## Plugins

| Plugin | Description |
|--------|-------------|
| **code-intelligence** | Code search and architecture analysis via Exa API |
| **skill-tools** | Deterministic skill creation with quality constraints |
| **learning-tools** | Interactive teaching with chunked explanations |
| **creative-tools** | Diagrams, UI design, generative art |
| **workflow-tools** | Session handoffs, planning, orchestration |
| **git-tools** | Smart commits and PR descriptions |

## Usage Examples

```bash
# code-intelligence (requires EXA_API_KEY in .env)
How do I use React hooks for state management?

# skill-tools
Create a skill for processing CSV files

# learning-tools
Explain how React hooks work

# creative-tools
Create a mermaid diagram of the authentication flow

# workflow-tools
/create-handoff
/daily-standup

# git-tools
/commit
/describe-pr
```

## Status Line Script

Custom status line that displays real-time session information in Claude Code.

![Status Line Preview](assets/statusline-preview.png)

**Displays:** Current directory, model name, context window usage, git branch/changes, session cost.

### Setup

```bash
# Install jq
brew install jq

# Copy script
cp statusline.sh ~/.claude/statusline.sh
chmod +x ~/.claude/statusline.sh

# Configure
claude config set status_line.command ~/.claude/statusline.sh
```

Restart Claude Code to see it in action.

## Links

- [Claude Plugins Guide](https://code.claude.com/docs/en/plugins)
- [Exa API](https://docs.exa.ai/reference/context) (for code-intelligence)

## License

MIT
