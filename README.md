# Claude Code Education

A marketplace of Claude Code educational plugins for developers.

## Installation

Add this marketplace to Claude Code:

```bash
claude plugin marketplace add https://github.com/SeleznovIvan/claude-code-education
```

## Available Plugins

### cc-course

**Interactive Claude Code Developer Course**

A 5-module hands-on course that teaches Claude Code by having you build real configurations for your own repository.

**Install:**
```bash
claude plugin install cc-course@claude-code-education
```

**Features:**
- Work on YOUR repository, not toy examples
- 5 modules covering foundations, skills, extensions, agents, and workflows
- Built-in validators check your progress
- Role-specific guidance (frontend, backend, QA, DevOps, data)

**Duration:** ~9-10 hours (at your own pace)

**More info:** [GitHub Repository](https://github.com/SeleznovIvan/claude-code-course-plugin)

## Getting Started

```bash
# 1. Add the marketplace
claude plugin marketplace add https://github.com/SeleznovIvan/claude-code-education

# 2. Install the course plugin
claude plugin install cc-course@claude-code-education

# 3. Start Claude Code in your project
cd /path/to/your/repo
claude

# 4. Setup MCP server (one-time)
/cc-course:setup

# 5. Start the course!
/cc-course:start 1
```

## Adding Your Own Plugins

To add a plugin to this marketplace, submit a PR with:
1. Plugin entry in `.claude-plugin/marketplace.json`
2. Updated README with plugin description

## License

MIT
