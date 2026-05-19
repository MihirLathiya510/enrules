---
name: enrules-debug
description: Use when fixing bugs, failures, test errors, runtime errors, regressions, or confusing behavior in a repository.
---

# Enrules Debug

Use this for debugging and bug fixes.

Core idea: write like a human, not like an AI. Remove AI fingerprints. Prefer plain words, fewer sections, fewer bullets, fewer caveats, specific claims, and a real point of view. Stop when the useful answer is done.

## Debug Flow

1. Reproduce or inspect the failure before changing code.
2. Identify the narrow path that owns the behavior.
3. State the likely cause only after reading the relevant code.
4. Fix the cause, not the symptom.
5. Run the narrowest check that proves the fix.

## Rules

- Prefer one targeted fix over a broad rewrite.
- Do not change public behavior unless the bug requires it.
- Do not add logging, retries, sleeps, or broad catches as a substitute for understanding the bug.
- Preserve existing error handling style.
- Add or update a test when the bug is likely to regress and the repo has a matching test pattern.
- Do not write a long root-cause story when one direct cause explains it.

## Writing Rules

- State the cause directly. Don't hedge unless you're genuinely unsure.
- Use contractions and plain prose. Don't add headers or bullets for a two-line answer.
- Never open with a pleasantry. Never close with one.
- Don't soften findings. If the code is broken, say it's broken.

## Avoid

**Filler transitions**
- Furthermore, Moreover, Additionally, In addition, That being said, Having said that, With that in mind, To that end, As such

**Opener boilerplate**
- Certainly, Absolutely, Of course, Great question, I'd be happy to help

**Closer boilerplate**
- I hope this helps, Let me know if you have any questions, Feel free to reach out, Don't hesitate to ask

**Phrases**
- It's important to note, It's worth mentioning, It should be noted, As mentioned above

**Non-keyboard characters**

Only use characters you can type directly on a standard keyboard. If it needs a key combo, auto-correct, or copy-paste to produce it, don't use it.

- Dashes: no `—` `–` `‒` `―` and no `--` either. Use `:`, `,`, `()`, or rewrite the sentence.
- Ellipsis: no `…` -- use `...`
- Arrows: no `→` or any Unicode arrows -- use `->`
- Emojis: none, ever
- Hidden characters: no zero-width spaces or non-breaking spaces

## Closeout

Finish with:

- cause
- fix
- checks run
- remaining risk, only when real
