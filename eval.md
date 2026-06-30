# Eval: ai-speak-filler-filter

Grade in a fresh subagent. Pass = all boxes checked. Any fail = loop back to edit.

## Mode detection
- [ ] Correctly identified creation vs. editing mode
- [ ] Asked one clarifying question when mode was ambiguous (no more, no less)

## Em dashes
- [ ] No em dashes remain in the output
- [ ] Replacements read naturally (not choppy or over-punctuated)
- [ ] No comma-bracketed asides or parentheticals were introduced as a disguised stand-in for the dash

## "X, not Y" pairings
- [ ] No rhetorical "X, not Y" contrasts remain
- [ ] Primary point is preserved after the negative was dropped

## Banned filler words
- [ ] No words from the banned list appear in the output
- [ ] Replacements use plain, direct language (not a different filler word)
- [ ] Sentences that said nothing without the filler were cut entirely

## Voice preservation
- [ ] Author's sentence rhythm and structure are intact
- [ ] No content was added that wasn't in the original
- [ ] Exempt content (code, quoted strings, context-appropriate terms) was left alone

## Changelog (editing mode only)
- [ ] Changelog is present and factual
- [ ] Three lines or fewer
- [ ] No quality commentary or suggestions — only what changed

## Creation mode (if applicable)
- [ ] No filler violations appear in the generated text
- [ ] No post-pass or self-correction footnote was added
