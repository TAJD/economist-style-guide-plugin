# Economist Style Plugins for Claude Code

Claude Code plugins for applying professional editorial standards to your writing.

## Available Plugins

### economist-style

Applies The Economist style guide principles to written content:

- **Clarity**: Active voice, simple words, direct statements
- **Precision**: Specific facts over vague claims, weasel word detection
- **Brevity**: Concise over verbose, redundancy removal
- **Dialect-aware**: Matches document's existing conventions (British, American, etc.)

Perfect for:
- Technical documentation
- Blog posts and articles
- Marketing copy
- Code comments and README files
- Any professional writing

## Installation

```bash
# In Claude Code
/plugin marketplace add YOUR_USERNAME/economist-style-plugins
/plugin install economist-style@economist-style-plugins
```

Replace `YOUR_USERNAME` with your GitHub username.

## Usage

The plugin activates automatically when editing text:

```
Review this document for clarity and precision
```

Claude will identify issues and suggest improvements following The Economist's editorial standards.

## What It Checks

✓ **Clarity issues**: Passive voice, jargon, complexity  
✓ **Precision problems**: Weasel words ("many", "significant"), vague claims  
✓ **Wordiness**: Fillers, redundancies, verbose expressions  
✓ **Consistency**: Dialect matching, style coherence  
✓ **Common errors**: Affect/effect, less/fewer, that/which  

## Example

**Before**:
```
The data was analyzed and it was found that there were 
significant issues affecting many users.
```

**After**:
```
Analysis revealed three critical issues affecting 847 users (23%).
```

Changes: Active voice, removed vagueness, added specifics.

## Features

- **Progressive disclosure**: Loads detailed rules only when needed
- **Dialect-aware**: Respects existing conventions (doesn't force British or American)
- **Context-sensitive**: Understands markdown, HTML, code documentation
- **Zero configuration**: Works immediately after installation

## Documentation

See [economist-style/README.md](economist-style/README.md) for detailed documentation.

## Contributing

Contributions welcome! Areas of interest:

- Additional style rules and patterns
- Industry-specific guides (technical, financial, academic)
- New dialect conventions
- Documentation improvements

## License

MIT License - See [LICENSE](LICENSE) for details.

## Author

Tom Dickson

## Support

- Issues: [GitHub Issues](https://github.com/YOUR_USERNAME/economist-style-plugins/issues)
- Documentation: [economist-style/README.md](economist-style/README.md)
- Claude Code Docs: https://code.claude.com/docs
