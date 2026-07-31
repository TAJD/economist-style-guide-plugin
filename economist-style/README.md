# Economist Style Guide Plugin for Claude Code

Apply The Economist's editorial standards to your writing - clarity, precision, brevity and dialect-aware editing.

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
The research team analyzed the data and found sales rose 
[specify: by how much?]. Customers responded positively to 
the new program.
```

### Changes Made
1. ✓ Passive → active voice
2. ✓ "significant increase" → flagged for a specific figure (the editor asks; it never invents numbers)
3. ✓ "Many" → deleted (vague quantifier)
4. ✓ "it was found that there were" → reduced (brevity)
5. ✓ Dialect preserved: kept "analyzed" and "program" (American English)

## Plugin Structure

```
economist-style/
├── .claude-plugin/
│   └── plugin.json              # Plugin metadata
├── skills/
│   └── economist-style/
│       ├── SKILL.md             # Main skill instructions
│       └── reference/
│           ├── ECONOMIST-SIGNATURE.md  # One-page distillation of house style
│           ├── CLARITY.md       # Passive voice, jargon, complexity
│           ├── PRECISION.md     # Weasel words, fillers, clichés
│           ├── WORDS.md         # A-Z rulings on misused words
│           ├── DIALECT-CONVENTIONS.md  # British/American conventions
│           ├── COMMON-ERRORS.md # Frequent mistakes, sensitivity
│           ├── PUNCTUATION.md   # Commas, dashes, quotation marks
│           ├── NUMBERS.md       # Numerals, percentages, dates
│           ├── STRUCTURE.md     # Paragraphs, leads, conclusions
│           ├── TONE.md          # Voice, register, adjective restraint
│           ├── ABBREVIATIONS.md # Acronyms, Latin terms
│           ├── CAPITALIZATION.md # Titles, institutions, geographic
│           └── SPECIAL-CONTEXTS.md # Foreign words, quotations, lists
└── README.md
```

## Contributing

Improvements welcome! Focus areas:

- Additional dialect-specific terminology
- More weasel word patterns
- Industry-specific style guides (tech, finance, etc.)
- Additional file type support

## References

- *The Economist Style Guide* (12th edition, Profile Books, 2018) — the authoritative source; the Economist's free online style guide has been taken down
- [Claude Code Documentation](https://code.claude.com/docs)
- [More about the implementation](https://tom-dickson.com/blog/teaching-claude-economist-style/)

## License

MIT License - feel free to adapt for your organisation's style guide.

## Version

1.4.1 - Added Orwell's six elementary rules to SKILL.md (verified against the style guide's introduction); tone guidance kept as paraphrase to avoid reproducing copyrighted text

1.4.0 - Added ECONOMIST-SIGNATURE.md quick reference (loaded first), WORDS.md A-Z usage rulings, honorifics convention (Mr/Ms + surname after first mention), and a clichés/dead-metaphors check; housekeeping on installation docs

1.3.0 - Corrected rules against the official Economist Style Guide (11th edition): number spell-out cutoff (one to ten), date format (January 1st 2025), no serial comma, double quotation marks, co-operate/co-ordinate hyphenation, singular collective nouns, sentence-case headlines; relabelled general inclusive-language guidance that is not Economist doctrine

1.2.0 - Added punctuation, numbers, structure, tone, abbreviations, capitalization, special contexts, gender-neutral language, and sensitivity guidelines

## Author

Tom Dickson
