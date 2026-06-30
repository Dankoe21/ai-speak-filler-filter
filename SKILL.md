---
name: ai-speak-filler-filter
description: Removes AI-speak, filler words, and rhetorical tics from any substantial text.
  Use when the user says "remove AI-speak," "remove filler," "filter filler," "make this less
  AI-sounding," "remove AI wording," "filter AI wording," "clean AI-speak," "clean filler," or
  "clean AI wording." Applies to docs, READMEs, emails, blog posts, skill files, or any
  text with significant prose.
---

# AI-Speak Filler Filter

Remove AI-speak and filler from any substantial text. Two modes depending on whether you're
creating or editing.

---

## Mode detection

**Creation** — user asks you to write something new, with ai-speak-filler-filter active.
Apply the rules below in real time. Produce clean output from the start; no post-pass needed.

**Editing** — user provides existing text to clean.
Rewrite silently. After the clean version, add a brief changelog (see format below).

If the mode is ambiguous, ask one question: "Is this existing text, or should I write it fresh?"

---

## The three rules

### 1. Em dashes
Replace em dashes used for dramatic pauses or tacked-on asides with a period, comma, or
conjunction. The content itself should carry the emphasis. Rewrite the sentence rather than
patching it: don't swap the dash for a parenthetical, and don't wrap the same aside in a pair
of commas instead. A comma-bracketed aside (`X, the thing in question, did Y`) is the same
interruption with different punctuation, not a fix.

Before: `Our tool automates entry—allowing teams to focus on growth—while reducing errors.`
After: `Our tool automates entry, freeing teams to focus on growth and reducing errors.`

Before (disguised, not fixed): `Our tool automates entry, the part that used to eat your morning, while reducing errors.`

### 2. "X, not Y" pairings
State the primary point directly. Drop the negative contrast — it adds length without adding meaning.

Before: `Focus on progress, not perfection.`
After: `Focus on progress.`

### 3. Banned filler words
See `references/ai-speak-banned-filler-words.md` for the full list. Main categories:

- **Cliché openers:** *delve into, let's dive in, navigate the landscape, embark on a journey, at the forefront of*
- **Hype verbs:** *leverage, utilize, streamline, revolutionize, empower, harness, facilitate*
- **Transition overload:** *moreover, furthermore, notably, subsequently, as previously mentioned*
- **Soft qualifiers:** *it's worth mentioning, generally speaking, it goes without saying, undeniably*
- **Empty adjectives:** *robust, seamless, comprehensive, cutting-edge, game-changing, pivotal*
- **Metaphor fluff:** *tapestry, testament, catalyst, beacon, cornerstone, paradigm, plethora*
- **Conclusion signposts:** *in conclusion, in summary, ultimately, that being said, moving forward*

Replace each with plain, direct language. If the sentence says nothing without the filler word,
cut the sentence.

---

## Editing mode changelog format

After the rewrite, add a short changelog. Keep it factual, three lines max:

```
Changes: removed em dashes (3), replaced "leverage" / "streamline" with direct verbs,
cut "it's worth noting" opener, dropped "moving forward" sign-off.
```

No commentary on quality or suggestions for further improvement — just what changed.

---

## Boundaries

- Preserve the author's voice, sentence rhythm, and structure. The goal is to remove tics,
  not to rewrite style.
- Don't flag words that are genuinely the right word in context (e.g., "catalyst" in a
  chemistry doc, "paradigm" in a philosophy paper).
- Code, inline variable names, and quoted strings are exempt.
- If the text is very short (one or two sentences), apply rules silently with no changelog.
