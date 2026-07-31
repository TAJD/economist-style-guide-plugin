# Economist Style Plugins for Claude Code

A **Claude Code plugin** (skill) that edits and proofreads your writing the way The Economist's style guide would — clarity, precision and brevity for markdown, documentation, blog posts, READMEs and code comments.

> This is an independent project, not affiliated with or endorsed by The Economist.

## Install

```bash
# In Claude Code
/plugin marketplace add TAJD/economist-style-guide-plugin
/plugin install economist-style@economist-style-plugins
```

## Example

**Before**:
```
The data was analyzed and it was found that there were 
significant issues affecting many users.
```

**After**:
```
The analysis found [specify: how many?] issues affecting 
[specify: how many?] users.
```

Changes: Active voice, cut filler, flagged vague claims for specifics (the editor asks; it never invents numbers).

## What It Checks

✓ **Clarity issues**: Passive voice, jargon, complexity  
✓ **Precision problems**: Weasel words ("many", "significant"), vague claims, clichés  
✓ **Wordiness**: Fillers, redundancies, verbose expressions  
✓ **Consistency**: Dialect matching, style coherence  
✓ **House style**: Numbers, dates, punctuation, honorifics, headlines  
✓ **Common errors**: Affect/effect, less/fewer, that/which  

## Usage

The plugin activates automatically when editing text:

```
Review this document for clarity and precision
```

Claude will identify issues and suggest improvements following The Economist's editorial standards.

## Who It's For

- Technical documentation and READMEs
- Blog posts and articles
- Marketing copy
- Code comments and docstrings
- Any professional writing

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

- Issues: [GitHub Issues](https://github.com/TAJD/economist-style-guide-plugin/issues)
- Documentation: [economist-style/README.md](economist-style/README.md)
- Claude Code Docs: https://code.claude.com/docs
