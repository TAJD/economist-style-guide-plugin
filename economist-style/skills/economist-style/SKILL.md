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
