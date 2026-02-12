# Claude Plugins Marketplace Setup Guide

This document describes how to create the `SeleznovIvan/claude-plugins` marketplace repository to enable easy plugin installation via:

```bash
claude plugin marketplace add SeleznovIvan/claude-plugins
claude plugin install cc-course@ivan-plugins
```

## Repository Structure

Create a new GitHub repository `SeleznovIvan/claude-plugins` with this structure:

```
claude-plugins/
├── .claude-plugin/
│   └── marketplace.json    # Required: marketplace manifest
├── README.md               # Documentation for the marketplace
├── LICENSE                 # MIT license
└── .gitignore
```

## File Contents

### `.claude-plugin/marketplace.json`

```json
{
  "name": "ivan-plugins",
  "owner": {
    "name": "Ivan Seleznov",
    "email": "your-email@example.com"
  },
  "metadata": {
    "description": "Ivan's Claude Code plugins - courses, tools, and utilities",
    "version": "1.0.0"
  },
  "plugins": [
    {
      "name": "cc-course",
      "source": {
        "source": "github",
        "repo": "SeleznovIvan/claude-code-course-plugin"
      },
      "description": "Interactive 5-module course teaching Claude Code development. Learn by building real configurations for your own repository.",
      "version": "1.0.0",
      "author": {
        "name": "Ivan Seleznov"
      },
      "homepage": "https://github.com/SeleznovIvan/claude-code-course-plugin",
      "repository": "https://github.com/SeleznovIvan/claude-code-course-plugin",
      "license": "MIT",
      "keywords": ["course", "learning", "tutorial", "skills", "education", "training"],
      "category": "education"
    }
  ]
}
```

### `README.md`

```markdown
# Ivan's Claude Code Plugins

A marketplace of Claude Code plugins for developers.

## Installation

Add this marketplace to Claude Code:

```bash
claude plugin marketplace add SeleznovIvan/claude-plugins
```

## Available Plugins

### cc-course

**Interactive Claude Code Developer Course**

A 5-module hands-on course that teaches Claude Code by having you build real configurations for your own repository.

**Install:**
```bash
claude plugin install cc-course@ivan-plugins
```

**Features:**
- Work on YOUR repository, not toy examples
- 5 modules covering foundations, skills, extensions, agents, and workflows
- Built-in validators check your progress
- Role-specific guidance (frontend, backend, QA, DevOps, data)

**Duration:** ~9-10 hours (at your own pace)

**More info:** [GitHub Repository](https://github.com/SeleznovIvan/claude-code-course-plugin)

## Adding Your Own Plugins

To add a plugin to this marketplace, submit a PR with:
1. Plugin entry in `marketplace.json`
2. Updated README with plugin description

## License

MIT
```

### `.gitignore`

```
.DS_Store
*.log
node_modules/
```

### `LICENSE`

MIT License (standard MIT license text)

## Setup Steps

1. **Create the repository on GitHub**
   ```bash
   # Create new repo on GitHub: SeleznovIvan/claude-plugins
   # Then clone it locally
   git clone https://github.com/SeleznovIvan/claude-plugins.git
   cd claude-plugins
   ```

2. **Create the directory structure**
   ```bash
   mkdir -p .claude-plugin
   ```

3. **Create all files** (marketplace.json, README.md, LICENSE, .gitignore)

4. **Commit and push**
   ```bash
   git add .
   git commit -m "Initial marketplace setup with cc-course plugin"
   git push origin main
   ```

5. **Test the marketplace**
   ```bash
   # Add the marketplace
   claude plugin marketplace add SeleznovIvan/claude-plugins

   # Verify it's listed
   claude plugin marketplace list

   # Install the course plugin
   claude plugin install cc-course@ivan-plugins

   # Verify installation
   claude plugin list
   ```

## After Marketplace is Created

Update the course plugin's README.md and CLAUDE.md with new installation instructions:

### New Installation Section

```markdown
## Installation

### Via Marketplace (Recommended)

```bash
# Add the marketplace (one-time)
claude plugin marketplace add SeleznovIvan/claude-plugins

# Install the course plugin
claude plugin install cc-course@ivan-plugins
```

### Manual Installation

```bash
git clone https://github.com/SeleznovIvan/claude-code-course-plugin.git ~/.claude/plugins/cc-course
```
```

### New Getting Started Section

```markdown
## Getting Started

```bash
# 1. Add the marketplace
claude plugin marketplace add SeleznovIvan/claude-plugins

# 2. Install the course plugin
claude plugin install cc-course@ivan-plugins

# 3. Start Claude Code in your project
cd /path/to/your/repo
claude

# 4. Setup MCP server (one-time)
/cc-course:setup

# 5. Start the course!
/cc-course:start 1
```
```

## Marketplace Schema Reference

See [Claude Code Plugin Marketplace Docs](https://code.claude.com/docs/en/plugin-marketplaces) for:

- Full marketplace.json schema
- Plugin source options (GitHub, git URL, npm, relative paths)
- Version pinning with `ref` and `sha`
- Private repository authentication
- Managed marketplace restrictions for teams

## Future Plugins

When adding more plugins to this marketplace, add entries to the `plugins` array in `marketplace.json`:

```json
{
  "name": "new-plugin-name",
  "source": {
    "source": "github",
    "repo": "SeleznovIvan/new-plugin-repo"
  },
  "description": "What this plugin does",
  "version": "1.0.0",
  "author": { "name": "Ivan Seleznov" },
  "keywords": ["relevant", "tags"],
  "category": "category-name"
}
```
