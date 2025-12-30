# Publishing Your Economist Style Plugin

## Step 1: Prepare the Repository Structure

Your plugin needs to be in a Git repository with this structure:

```
economist-style-plugins/               # Repository root
├── .claude-plugin/
│   └── marketplace.json               # Marketplace manifest
├── economist-style/                   # Plugin directory
│   ├── .claude-plugin/
│   │   └── plugin.json
│   ├── skills/
│   │   └── economist-style/
│   │       ├── SKILL.md
│   │       └── reference/
│   │           ├── CLARITY.md
│   │           ├── PRECISION.md
│   │           ├── DIALECT-CONVENTIONS.md
│   │           └── COMMON-ERRORS.md
│   └── README.md
├── README.md                          # Repository README
└── LICENSE                            # License file
```

## Step 2: Create GitHub Repository

### Option A: Command Line

```bash
# Navigate to the plugin directory
cd economist-style-marketplace

# Initialize git
git init

# Create main branch
git branch -M main

# Add all files
git add .

# Commit
git commit -m "Initial commit: Economist style guide plugin"

# Create repository on GitHub (requires GitHub CLI)
gh repo create economist-style-plugins --public --source=. --remote=origin --push

# Or manually create on github.com and then:
git remote add origin git@github.com:YOUR_USERNAME/economist-style-plugins.git
git push -u origin main
```

### Option B: GitHub Web Interface

1. Go to https://github.com/new
2. Repository name: `economist-style-plugins`
3. Description: "Claude Code plugin for The Economist style guide"
4. Public repository
5. Don't initialize with README (you already have one)
6. Click "Create repository"
7. Follow the push commands shown

## Step 3: Prepare Repository Files

### Update marketplace.json

The marketplace.json should reference your plugin directory:

```json
{
  "name": "economist-style-plugins",
  "owner": {
    "name": "Your Name or Organization"
  },
  "plugins": [
    {
      "name": "economist-style",
      "source": "./economist-style",
      "description": "Apply The Economist style guide - clarity, precision, brevity"
    }
  ]
}
```

### Create Repository README.md

```markdown
# Economist Style Plugins for Claude Code

Claude Code plugins for applying professional editorial standards to your writing.

## Available Plugins

### economist-style

Applies The Economist style guide principles:
- Clarity: Active voice, simple words, direct statements
- Precision: Specific facts over vague claims
- Brevity: Concise over verbose
- Dialect-aware: Matches document conventions

## Installation

```bash
/plugin marketplace add YOUR_USERNAME/economist-style-plugins
/plugin install economist-style@economist-style-plugins
```

## Usage

The plugin activates automatically when editing text:

```
Review this document for clarity and precision
```

See [economist-style/README.md](economist-style/README.md) for details.

## License

MIT
```

### Add LICENSE File

Create a LICENSE file (MIT suggested):

```
MIT License

Copyright (c) 2025 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Step 4: Restructure Files

Before committing, restructure to match the expected format:

```bash
cd economist-style-marketplace

# Rename the plugin directory
mv economist-style-plugin economist-style

# Remove test files
rm test-document.md
rm INSTALL.md

# Update marketplace.json source path
# (should point to ./economist-style not ./economist-style-plugin)
```

## Step 5: Push to GitHub

```bash
# Stage all changes
git add .

# Commit
git commit -m "Plugin ready for public use"

# Push
git push origin main
```

## Step 6: Test Installation from GitHub

```bash
# Start Claude Code
claude

# Add your marketplace
/plugin marketplace add YOUR_USERNAME/economist-style-plugins

# Install the plugin
/plugin install economist-style@economist-style-plugins

# Restart Claude Code
# Exit and restart: claude

# Test it
# Create a test file and ask Claude to review it
```

## Step 7: Document for Users

Add to your repository README:

### Quick Start

```markdown
## Quick Start

1. Install the marketplace:
   ```
   /plugin marketplace add YOUR_USERNAME/economist-style-plugins
   ```

2. Install the plugin:
   ```
   /plugin install economist-style@economist-style-plugins
   ```

3. Restart Claude Code

4. Use it:
   ```
   Review this document for style issues
   ```

## What It Checks

- ✓ Clarity: Passive voice, jargon, complexity
- ✓ Precision: Weasel words, fillers, vague claims
- ✓ Brevity: Redundancies, wordiness
- ✓ Consistency: Dialect matching

## Examples

**Before**: "The data was analyzed and it was found that there were significant issues."

**After**: "Analysis revealed three critical issues."
```

## Step 8: Announce & Share

### Share on:

1. **Claude Code Community** - Discord #claude-code channel
2. **GitHub Topics** - Add topics: `claude-code`, `claude-plugin`, `style-guide`
3. **README badges** - Add installation count, license, etc.

### Community Marketplaces

Submit to:
- https://claude-plugins.dev/
- https://claudecodemarketplace.com/

## Maintenance

### Version Updates

When you improve the plugin:

1. Update `economist-style/.claude-plugin/plugin.json` version:
   ```json
   {
     "version": "1.1.0"
   }
   ```

2. Commit and push:
   ```bash
   git add .
   git commit -m "v1.1.0: Add new precision checks"
   git push
   ```

3. Users update with:
   ```
   /plugin update economist-style@economist-style-plugins
   ```

### Semantic Versioning

- **1.0.0** → **1.0.1**: Bug fixes
- **1.0.0** → **1.1.0**: New features (backward compatible)
- **1.0.0** → **2.0.0**: Breaking changes

## Troubleshooting

### Plugin not found?

- Check repository is public
- Verify marketplace.json syntax
- Ensure plugin directory name matches source in marketplace.json

### Skill not loading?

- Check SKILL.md frontmatter syntax
- Verify file is named exactly `SKILL.md` (case-sensitive)
- Look at Claude Code logs with `claude --debug`

### Users can't install?

- Confirm repository URL is correct
- Check no typos in plugin name
- Verify marketplace.json is valid JSON

## Example Final Structure

```
economist-style-plugins/          # Your repo
├── .claude-plugin/
│   └── marketplace.json          # Points to ./economist-style
├── economist-style/              # Plugin directory
│   ├── .claude-plugin/
│   │   └── plugin.json          # Version 1.0.0
│   ├── skills/
│   │   └── economist-style/
│   │       ├── SKILL.md
│   │       └── reference/
│   │           ├── CLARITY.md
│   │           ├── PRECISION.md
│   │           ├── DIALECT-CONVENTIONS.md
│   │           └── COMMON-ERRORS.md
│   └── README.md
├── README.md                     # Marketplace README
└── LICENSE
```

## Commands Summary

```bash
# Setup
cd economist-style-marketplace
git init
git add .
git commit -m "Initial commit"

# Create GitHub repo (CLI)
gh repo create economist-style-plugins --public --source=. --push

# Or (manual)
# 1. Create repo on github.com
# 2. Then:
git remote add origin git@github.com:YOUR_USERNAME/economist-style-plugins.git
git push -u origin main

# Install from GitHub
claude
/plugin marketplace add YOUR_USERNAME/economist-style-plugins
/plugin install economist-style@economist-style-plugins
```

You're done! Your plugin is now publicly available.