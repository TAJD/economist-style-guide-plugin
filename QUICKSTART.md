# Quick Setup Steps

## Publish to GitHub (5 minutes)

### 1. Navigate to the directory
```bash
cd /path/to/economist-style-marketplace
```

### 2. Initialize Git
```bash
git init
git branch -M main
```

### 3. Stage all files
```bash
git add .
git commit -m "Initial commit: Economist style guide plugin"
```

### 4a. Create GitHub repo (using GitHub CLI)
```bash
gh repo create economist-style-plugins --public --source=. --push
```

### 4b. OR create GitHub repo manually
1. Go to https://github.com/new
2. Repository name: `economist-style-plugins`
3. Description: "Claude Code plugin for The Economist style guide"
4. Make it **Public**
5. Click "Create repository"
6. Then run:
```bash
git remote add origin git@github.com:YOUR_USERNAME/economist-style-plugins.git
git push -u origin main
```

## Install & Test (2 minutes)

### 1. Start Claude Code
```bash
claude
```

### 2. Add your marketplace
```
/plugin marketplace add YOUR_USERNAME/economist-style-plugins
```

### 3. Install the plugin
```
/plugin install economist-style@economist-style-plugins
```

### 4. Restart Claude Code
Exit and restart:
```bash
claude
```

### 5. Test it
Create a test file with style issues:

```bash
echo "The data was analyzed by the team and it was found that there were many significant problems affecting various users." > test.md
```

Then ask Claude:
```
Review test.md for style issues
```

Expected output: Claude identifies passive voice, vague quantifiers ("many", "various", "significant"), and suggests specific improvements.

## Done!

Your plugin is now:
- ✓ Published on GitHub
- ✓ Installable by anyone
- ✓ Working in your Claude Code

## Share It

Tell others to install:
```
/plugin marketplace add YOUR_USERNAME/economist-style-plugins
/plugin install economist-style@economist-style-plugins
```

## Update Later

When you improve the plugin:

1. Edit files
2. Update version in `economist-style/.claude-plugin/plugin.json`
3. Commit and push:
```bash
git add .
git commit -m "v1.1.0: Description of changes"
git push
```

Users update with:
```
/plugin update economist-style@economist-style-plugins
```