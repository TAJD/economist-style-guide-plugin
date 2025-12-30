# Economist Style Guide Plugin for Claude Code

Apply The Economist's editorial standards to your writing - clarity, precision, brevity, and British English conventions.

## Features

- **Automatic activation**: Claude applies style guidance when you edit markdown, HTML, or documentation
- **Progressive disclosure**: Loads detailed rules only when needed
- **Weasel word detection**: Identifies vague language and suggests specifics
- **Filler removal**: Flags redundant phrases and empty intensifiers
- **Dialect-aware**: Matches document's existing conventions (British, American, etc.)
- **Passive voice detection**: Suggests active voice alternatives

## Installation

### Via Local Marketplace (Development)

```bash
# Create test marketplace directory
mkdir -p ~/economist-style-marketplace/.claude-plugin
cd ~/economist-style-marketplace

# Copy this plugin
cp -r /path/to/economist-style-plugin .

# Create marketplace.json
cat > .claude-plugin/marketplace.json << 'EOF'
{
  "name": "economist-style-marketplace",
  "owner": {
    "name": "Your Name"
  },
  "plugins": [
    {
      "name": "economist-style",
      "source": "./economist-style-plugin",
      "description": "Apply The Economist style guide to written content"
    }
  ]
}
EOF

# Start Claude Code and install
claude
/plugin marketplace add ~/economist-style-marketplace
/plugin install economist-style@economist-style-marketplace
```

### Via Git Repository (Production)

Once published to a Git repository:

```bash
/plugin marketplace add your-username/economist-style-plugins
/plugin install economist-style@economist-style-plugins
```

## Usage

### Automatic Application

The skill activates automatically when you work with text:

```bash
# Just ask Claude to edit your content
"Please review this markdown file for style issues"
"Fix the grammar in this document"
"Edit this for clarity and precision"
```

Claude will apply Economist style principles automatically.

## What Gets Checked

### Clarity
- Passive voice → Active voice
- Complex words → Simple alternatives
- Jargon → Plain English
- Hedge words → Direct statements

### Precision
- Vague quantifiers → Specific numbers
- Weasel words → Evidence-based claims
- Filler phrases → Deletion
- Redundancies → Concise expressions

### Dialect Consistency
- Detects document's existing conventions (British, American, etc.)
- Only flags inconsistencies within the same document
- Matches spelling patterns (-ise vs -ize)
- Preserves established style

### Common Errors
- Affect/effect confusion
- Less/fewer mistakes
- That/which usage
- Split infinitives (when awkward)
- Dangling modifiers

## File Types Supported

- **Markdown**: `.md`, `.markdown`
- **HTML**: `.html`, `.htm`
- **Code documentation**: Python, JavaScript, TypeScript, Java, C/C++ (comments and docstrings)
- **Plain text**: `.txt`

## Examples

### Before
```
The data was analyzed by the research team and it was found that 
there was a significant increase in sales. Many customers responded 
positively to the new program.
```

### After
```
The research team analyzed the data and found sales rose 23% 
year-on-year. Customers responded positively to the new program.
```

### Changes Made
1. ✓ Passive → active voice
2. ✓ "significant increase" → "23% year-on-year" (specific)
3. ✓ "Many" → deleted (vague quantifier)
4. ✓ "it was found that there were" → reduced (brevity)
5. ✓ Dialect preserved: kept "analyzed" and "program" (American English)

## Plugin Structure

```
economist-style-plugin/
├── .claude-plugin/
│   └── plugin.json              # Plugin metadata
├── skills/
│   └── economist-style/
│       ├── SKILL.md             # Main skill instructions
│       └── reference/
│           ├── CLARITY.md       # Detailed clarity rules
│           ├── PRECISION.md     # Weasel words & fillers
│           ├── DIALECT-CONVENTIONS.md  # British/American conventions
│           └── COMMON-ERRORS.md # Frequent mistakes
└── README.md
```

## Contributing

Improvements welcome! Focus areas:

- Additional dialect-specific terminology
- More weasel word patterns
- Industry-specific style guides (tech, finance, etc.)
- Additional file type support

## References

- [The Economist Style Guide](https://www.economist.com/styleguide/introduction)
- [Claude Code Documentation](https://code.claude.com/docs)

## License

MIT License - feel free to adapt for your organisation's style guide.

## Version

1.0.0 - Initial release

## Author

Tom Lucidor
