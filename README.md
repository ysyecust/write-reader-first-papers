# Write Reader-First Papers

[中文说明](README.zh-CN.md)

An instruction-only Agent Skill for revising academic writing so first-time
readers can understand the problem, contribution, evidence, value, and
limitations without decoding internal jargon or formulaic prose.

The skill works with both
[Codex](https://developers.openai.com/codex/build-skills) and
[Claude Code](https://code.claude.com/docs/en/skills). It follows the open
Agent Skills format and requires no scripts, network services, or
model-specific API.

## What it does

- Protects numbers, denominators, citations, terminology, and claim boundaries.
- Reorganizes arguments around the order in which readers need information.
- Rewrites awkward, overly defensive, promotional, or template-like prose.
- Replaces unexplained internal labels with reader-facing language.
- Connects results to their scientific meaning without overstating the evidence.
- Keeps English and Chinese versions aligned in meaning and claim strength.
- Reviews abstracts, introductions, methods, results, conclusions, highlights,
  captions, supplementary information, cover letters, and rebuttals.

This is a writing and reasoning workflow. It does not attempt to evade AI
detectors, disguise authorship, or invent a human writing history.

## How it works

The skill applies a reader-first sequence:

1. Establish the source of truth and protect factual content.
2. Map the need, obstacle, proposed work, evidence, value, and boundary.
3. Diagnose reader friction through logic, meaning, syntax, evidence, and voice.
4. Revise structure, argument flow, transitions, terminology, sentences, and
   bilingual alignment in separate passes.
5. Report content, evidence, compilation, rendering, and submission checks as
   separate verification gates.

Detailed rules are loaded progressively from the `references/` directory.

## Installation

### Codex and Codex Cloud

For personal use, copy `skills/write-reader-first-papers/` to:

```text
~/.agents/skills/write-reader-first-papers/
```

For a repository-scoped skill, copy or vendor
`skills/write-reader-first-papers/` into the target repository:

```text
.agents/skills/write-reader-first-papers/
```

Commit the repository-scoped folder so Codex Cloud receives it with the source
checkout.

### Claude Code

For personal use, copy `skills/write-reader-first-papers/` to:

```text
~/.claude/skills/write-reader-first-papers/
```

For project use, copy `skills/write-reader-first-papers/` to:

```text
.claude/skills/write-reader-first-papers/
```

The optional `agents/openai.yaml` file supplies Codex interface metadata.
Claude Code can ignore it; the shared behavior is defined by `SKILL.md` and
`references/`.

## Usage

Invoke the skill explicitly:

```text
# Codex
$write-reader-first-papers Review the manuscript for argument flow and language.

# Claude Code
/write-reader-first-papers Review the manuscript for argument flow and language.
```

Both agents may also load it automatically when a request matches the
description in `SKILL.md`.

Example requests:

- “Rewrite this abstract so a first-time reader can understand the contribution.”
- “Review the full manuscript for unclear transitions and formulaic prose.”
- “Shorten every figure and table caption without losing necessary definitions.”
- “Synchronize the English and Chinese versions without strengthening claims.”
- “Check whether the conclusion explains the value of the work rather than
  repeating numbers.”

## Repository structure

```text
.
├── README.md
├── README.zh-CN.md
├── LICENSE
└── skills/
    └── write-reader-first-papers/
        ├── SKILL.md
        ├── agents/
        │   └── openai.yaml
        └── references/
            ├── review-checklist.md
            ├── section-playbook.md
            └── style-rules.md
```

## Contributing

Issues and pull requests are welcome. Keep additions:

- general across research fields;
- independent of a particular manuscript, institution, or model provider;
- concise enough to justify their prompt-context cost;
- focused on reader comprehension and evidence fidelity.

## License

MIT
