---
name: economist-style
description: Apply The Economist style guide to written content. Use when editing markdown, HTML, documentation, or any written text that needs professional editing for clarity, precision, and brevity. Detects weasel words, fillers, passive voice, and style issues.
---

# The Economist Style Guide

Apply these principles to all written content, including markdown files, HTML, code documentation, and technical writing.

## Core Principles

1. **Clarity first**: Use short words, active voice, and concrete examples
2. **Precision**: Replace vague quantifiers with specific numbers and facts
3. **Brevity**: Choose concise over verbose expressions
4. **Dialect awareness**: Match the document's existing spelling and conventions (British, American, etc.)

## Tone: The "Do Nots"

The Economist's introduction explicitly prohibits these:

- **Do not be stuffy**: Use everyday speech, not the language of lawyers or bureaucrats
- **Do not be hectoring or arrogant**: Those who disagree are not necessarily stupid
- **Do not be too pleased with yourself**: Let analysis speak; avoid self-congratulation
- **Do not be too chatty**: Maintain professional distance
- **Do not be too didactic**: Guide, don't lecture
- **Do not be sloppy**: Edit ruthlessly; cut anything superfluous

## Analysis Workflow

When reviewing text, follow this sequence:

### 1. Detect Document Dialect
**IMPORTANT**: Before making any suggestions, detect the document's existing spelling dialect:
- Look for spellings like "colour" vs "color", "organise" vs "organize"
- Check date formats (1st January vs January 1st)
- Observe punctuation style (single vs double quotes)
- **Match the document's existing conventions** - do not impose a dialect

### 2. Structural Review
- Check for buried ledes (main point should come first)
- Verify logical flow and argument structure
- Ensure each paragraph has a clear purpose

### 3. Clarity Analysis
For detailed passive voice and clarity rules, read `reference/CLARITY.md`

Quick checks:
- Flag passive voice constructions
- Identify jargon and suggest plain alternatives
- Find unnecessarily complex words
- Detect hedge words that weaken statements

### 4. Precision Check
For detailed precision rules, read `reference/PRECISION.md`

Quick checks:
- Identify vague quantifiers ("many", "often", "significant")
- Flag weasel words and empty fillers
- Suggest specific numbers or evidence
- Remove redundant phrases

### 5. Dialect Conventions (if applicable)
Only if the user explicitly requests dialect checking, or if there are inconsistencies within the document, read `reference/DIALECT-CONVENTIONS.md`

### 6. Common Errors
For frequently encountered mistakes, read `reference/COMMON-ERRORS.md`

### 7. Punctuation Check
For detailed punctuation rules (commas, semicolons, dashes, quotation marks), read `reference/PUNCTUATION.md`

Quick checks:
- Verify comma usage (serial comma, restrictive clauses)
- Check dash and hyphen usage
- Ensure consistent quotation mark style

### 8. Numbers and Figures
For number formatting guidelines, read `reference/NUMBERS.md`

Quick checks:
- Spell out numbers one to nine, use numerals for 10+
- Verify percentage formatting (% symbol, percentage points vs percentages)
- Check date and currency formatting

### 9. Structure Review
For document organisation guidelines, read `reference/STRUCTURE.md`

Quick checks:
- Each paragraph has a clear topic sentence
- Lead/opening hooks the reader
- Logical flow from paragraph to paragraph
- Conclusion adds value (not just summary)

### 10. Tone Assessment
For voice and register guidance, read `reference/TONE.md`

Quick checks:
- Authoritative but not arrogant
- Avoid excessive adjectives and intensifiers
- Neutral language on contested issues
- No preaching or lecturing

### 11. Abbreviations (on-demand)
If the document contains abbreviations or acronyms, read `reference/ABBREVIATIONS.md`

### 12. Capitalisation (on-demand)
If there are capitalisation questions (titles, institutions, geographic terms), read `reference/CAPITALIZATION.md`

### 13. Special Contexts (on-demand)
For quotations, foreign words, lists, or tables, read `reference/SPECIAL-CONTEXTS.md`

## Output Format

When providing feedback:

1. List issues by category (clarity, precision, dialect consistency if applicable)
2. Provide line/paragraph references
3. Show original text and suggested replacement
4. Explain the reasoning briefly

Example:
```
**Clarity Issue** (Para 2, Line 3)
Original: "The data was analysed by the research team"
Suggested: "The research team analysed the data"
Reason: Active voice is clearer and more direct
```

## When Not to Apply

- Direct quotations (preserve original wording)
- Code examples (unless in comments/documentation)
- Technical terms with no plain alternative
- Proper nouns and brand names
- Established dialect/spelling patterns (match what's already there)
