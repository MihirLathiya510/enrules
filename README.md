# enrules

Claude Code plugin that makes Claude write like a human and work like a careful engineer.

The core problem with AI-assisted coding is not capability. It's behavior: editing before reading, broad rewrites for narrow tasks, padded explanations, generated-sounding prose, and overconfident claims about untested code. `enrules` addresses this with Markdown guidance loaded directly into context. No Python hooks, no external tooling, no post-processing.

The philosophy is in [CORE.md](CORE.md).

## What it does

When active, Claude:

- reads the relevant code and context before touching anything
- makes the smallest change that solves the task
- matches the repo's existing names, patterns, and style
- skips the AI vocabulary, filler transitions, opener/closer boilerplate, em dashes, and hollow prose
- writes like a specific engineer made a specific decision, not like a language model composing a response

## Skills

Four skills, each loaded independently:

| Skill | Use for |
|---|---|
| `enrules` | general repo work: coding, reading, explaining |
| `enrules-review` | code review, diff review, PR review |
| `enrules-debug` | bug fixes, test failures, runtime errors |
| `enrules-docs` | README, comments, commit text, PR descriptions |

## Install

From the parent directory:

```sh
claude --plugin-dir ./enrules
```

Verify inside Claude Code:

```sh
/plugin
/agents
```

The default agent is `enrules`. It loads automatically.

## Usage

Invoke a skill explicitly when the task is specialized:

```
/enrules:enrules-review
```

Or just work with the default agent active. Suggested prompts:

```
Fix this bug with the smallest safe change.
```

```
Review this diff for correctness, regressions, and missing checks.
```

```
Update the docs in the repo's existing style.
```

```
Explain what changed without filler.
```

## Structure

```
enrules/
├── .claude-plugin/
│   ├── plugin.json
│   └── marketplace.json
├── agents/
│   └── enrules.md
├── skills/
│   ├── enrules/SKILL.md
│   ├── enrules-review/SKILL.md
│   ├── enrules-debug/SKILL.md
│   └── enrules-docs/SKILL.md
├── CORE.md
├── README.md
└── settings.json
```

## Why no hooks

Markdown instructions are guidance, not hard enforcement. That's intentional. The plugin stays small, readable, portable, and cheap to load. If a project needs blocking behavior for risky commands, add a `hooks/hooks.json` layer on top.
