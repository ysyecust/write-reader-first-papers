---
name: write-reader-first-papers
description: Rewrite, restructure, translate, or audit academic manuscripts so first-time readers can identify the problem, contribution, evidence, value, and limitations without decoding internal jargon or formulaic prose. Use for English or Chinese papers, abstracts, introductions, methods, results, conclusions, highlights, captions, tables, supplementary information, cover letters, rebuttals, and bilingual synchronization when the user asks for clearer language, natural authorial voice, direct wording, “说人话”, removal of unnecessary “not X but Y” or “不是……而是……” constructions, reader-first organization, or a final prose review.
---

# Write Reader-First Papers

Write for a capable first-time reader. Make the scientific logic visible before exposing internal labels, abbreviations, or dense result tables. Preserve evidence exactly while improving structure and language.

## Required references

Read [references/style-rules.md](references/style-rules.md) before changing prose.

Read [references/section-playbook.md](references/section-playbook.md) when editing front matter, reorganizing sections, shortening captions, or synchronizing Chinese and English.

Read [references/review-checklist.md](references/review-checklist.md) before the final handoff.

## Core standard

Apply these priorities in order:

1. Preserve scientific truth, numbers, denominators, citations, labels, and claim boundaries.
2. Let a reader understand why the work matters, what was built, how it was tested, and what changed.
3. State the positive proposition directly. Use contrast only when the distinction changes the scientific claim.
4. Introduce plain meaning before project-specific names, abbreviations, stages, variants, or experiment codes.
5. Make every important sentence easy to parse as subject, action, object, and consequence.
6. Keep caveats accurate and proportionate. Do not turn honesty into self-defeating prose.
7. Keep English and Chinese aligned in meaning, strength, numbers, and terminology.

## Workflow

### 1. Establish the source of truth

- Read the requested passage plus enough surrounding text to understand its role.
- Inspect tables, figures, supplementary files, and evidence records before changing factual claims.
- Record protected items: numbers, denominators, statistical qualifiers, method definitions, citation keys, labels, and cross-references.
- Determine whether the task authorizes critique only, wording edits, structural reordering, or claim changes.

### 2. Build the reader’s argument map

Write a one-line answer for each applicable question:

- What need or problem makes this work worth doing now?
- Why is the task difficult in practice?
- What framework, method, or system was created?
- What changes when it is used?
- What evidence supports that change?
- What can readers use the result for?
- Where does the demonstrated boundary end?

Reorder sections or paragraphs when the manuscript presents evaluation details before explaining the method, model, system, dataset, or hypothesis being evaluated.

### 3. Diagnose reader friction

Read the text through five lenses:

1. **Logic:** does the reader encounter the need, method, and evidence in the order required to understand them?
2. **Meaning:** does every internal term have a plain-language meaning before its abbreviation or label?
3. **Syntax:** can each sentence be parsed without rereading, and does each pronoun have a clear referent?
4. **Evidence:** can every quantitative or causal statement be traced to a stated comparison, sample, or source?
5. **Voice:** does the prose sound like a knowledgeable author explaining the work, rather than a template announcing importance?

### 4. Revise in separate passes

1. **Structure pass:** fix section order and paragraph sequence.
2. **Argument pass:** give each paragraph one job and connect evidence to its meaning.
3. **Transition pass:** inspect every sentence handoff. Move a method-specific mechanism or failure mode after the method and its purpose have been introduced.
4. **Terminology pass:** define terms and replace internal shorthand with reader-facing language.
5. **Sentence pass:** remove mechanical contrast, vague subjects, unnecessary nominalization, filler, stacked clauses, and translation artifacts.
6. **Evidence pass:** restore any lost qualifier and verify every number against the source.
7. **Bilingual pass:** synchronize meaning sentence by sentence; do not let either version make a stronger claim.

Do not polish every sentence into the same rhythm. Preserve natural variation and the author’s domain voice.

### 5. Verify the delivered document

- Search again for rejected phrases, inconsistent terms, unexplained labels, and obsolete wording.
- When the required tools are available, compile source documents and check undefined citations and references separately from prose quality.
- When a rendered document is available, reread its extracted text and inspect changed pages at their final size.
- Report content edits, evidence checks, compilation, and rendered-page review as separate gates. Mark unavailable gates as not run rather than silently treating them as passed.

## Agent portability

- Keep this skill self-contained. It must not depend on a particular paper, author, institution, research field, model provider, local memory, or Git history.
- For repository-scoped use in Codex or Codex Cloud, place the folder at `.agents/skills/write-reader-first-papers/`.
- For repository-scoped use in Claude Code, place the same folder at `.claude/skills/write-reader-first-papers/`.
- Resolve all reference files relative to this `SKILL.md`. Never assume a user-home or machine-specific path.
- The skill requires no bundled scripts, network services, external model calls, or local scientific toolchain. Use compilers, PDF tools, and repository checks only when the active environment already provides them.
- Adapt examples and terminology to the manuscript under review. Do not import names, numbers, claims, or writing habits from earlier projects.

## Non-negotiable writing rules

- Prefer “The method records validated decisions and applies them to later inputs” over “The method is not merely a procedure but a reusable knowledge framework.”
- Replace “This distinction is important” with the consequence that makes it important.
- Replace “matched subset,” “development configuration,” or similar internal shorthand with who selected what, from where, and why.
- Explain an interface or mechanism by what it allows and prevents. Avoid unexplained acronyms in abstracts and highlights.
- Pair headline numbers with the measured quantity, comparison, sample, and meaning. Do not turn abstracts and conclusions into ledgers.
- Present limitations after the demonstrated value. State the tested scope directly and name the next test.
- Avoid grand claims, invented novelty, unsupported causality, and silent strengthening during translation.
- Avoid blanket deletion of every negative word. Preserve necessary scientific distinctions, failure results, and boundary conditions.

## Output expectations

When editing files, provide:

- the revised files;
- a concise account of the argument or wording changes;
- protected facts that were checked;
- compilation and rendered-text results;
- any unresolved claim, terminology, or submission-policy issue.

When the user requests text only, return clean copy-ready prose without LaTeX commands unless LaTeX was requested.
