---
date: 2026-10-07T09:10:00
layout: content-page
stags: 
title: "2026-11-20: In prose, can apostrophe usage be deterministically distinguished from single quote usage?"
---

Short answer: no it can't.

<!--more-->

{{% section-navigation %}}

{{% content %}}

## Content {#content}

### Why ask this question?

Consider how Emacs Lisp uses single quotes: it only uses `'` as a prefix, and it is never matched. But in SQL variants, `''` is typically used as the main way to specify literal strings, and `'` isn't used alone at all. In these cases, it is one or the other.

Assuming we want to have the behavior of `''` to be automatic expansion when used in matched form, does this mean we can have `'` and `''` share a key in practice, because they would be mutually exclusive usages?

### Prose foils this

{{% ai-chatbot-prompt %}}

How can a text editor know if a ' should get auto-matched or not?

In the case of a word like `'90s`, how does it know not to expand the apostrophe out to be matched?

{{% /ai-chatbot-prompt %}}

{{% ai-chatbot-response chatbot="Gemini" %}}

Code editors use syntactic boundaries and regular expressions to check the characters immediately surrounding the cursor before deciding to insert a matching closing quote.

To prevent a word like `'90s` from expanding into `''90s`, editors rely on a specific rule: if the character immediately following the cursor is an alphanumeric character, auto-matching is skipped.

#### The Auto-Match Decision Logic

When you press the single quote key (`'`), the editor instantly runs a quick conditional check:

1. **Check After the Cursor**: Is the character directly to the right a letter or a number?
    - **Yes**: (e.g., the cursor is right before 90s). **Do not auto-match**. The editor assumes you are writing an apostrophe for an abbreviation or contraction.
    - **No**: (e.g., the cursor is before a space, a punctuation mark, or a newline). **Auto-match**. The editor assumes you are starting a new string literal.
2. **Check Before the Cursor**: Is the character directly to the left a letter or a number?
    - **Yes**: (e.g., you just typed a word and want to add s like user's). **Do not auto-match**.

#### Where it Still Fails

While this works perfectly for `'90s` or `don't`, the logic is purely structural, not semantic. It will still trip up in edge cases:

- If you type `'` right before a symbol or punctuation (e.g., `'...and then he left'`), it will falsely auto-match because a period or ellipsis is not alphanumeric.

{{% /ai-chatbot-response %}}

I think even more than what the AI chatbot mentions, we have issues. When we aren't talking about editing existing text but entering new text, words like `'90s` instantly give you problems. If apostrophes were only ever used *after* letters (rather after spaces) that would be one thing, and maybe we could entertain not splitting the usages onto two different key bindings. But this simply isn't the case, and so that is that.

{{% /content %}}

{{% section-navigation %}}
