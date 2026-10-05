---
name: write-reader-first-papers
description: Rewrite, restructure, translate, or audit academic manuscripts so first-time readers can identify the problem, contribution, evidence, value, and limitations without decoding internal jargon or formulaic prose. Use for English or Chinese papers, theses, dissertations, abstracts, introductions, methods, results, conclusions, highlights, captions, tables, supplementary information, cover letters, rebuttals, and bilingual synchronization when the user asks for clearer language, natural authorial voice, direct wording, “说人话”, removal of unnecessary “not X but Y” or “不是……而是……” constructions, reader-first organization, a final prose review, an exhaustive located audit of AI-style, colloquial, or hard-to-read wording across a long manuscript, or a contribution audit that separates research and engineering contributions from implementation mistakes, debugging effort, and corrective maintenance.
---

# Write Reader-First Papers

Write for a capable first-time reader. Make the scientific logic visible before exposing internal labels, abbreviations, or dense result tables. Preserve evidence exactly while improving structure and language.

## Required references

Read [references/style-rules.md](references/style-rules.md) before changing prose.

Read [references/section-playbook.md](references/section-playbook.md) when editing front matter, reorganizing sections, shortening captions, or synchronizing Chinese and English.

Read [references/chinese-friction-patterns.md](references/chinese-friction-patterns.md) when reviewing or revising Chinese prose, including the Chinese half of a bilingual document.

Read [references/long-document-audit.md](references/long-document-audit.md) when the user asks for a complete, located list of prose problems in a thesis, dissertation, or other multi-file manuscript.

Read [references/review-checklist.md](references/review-checklist.md) before the final handoff.

## Core standard

Apply these priorities in order:

1. Preserve scientific truth, numbers, denominators, citations, labels, and claim boundaries.
2. Attribute contribution to the final method, architecture, algorithm, dataset, or finding—not to effort spent correcting an implementation mistake. A change that only restores intended behavior is a correction, not an innovation.
3. Let a reader understand why the work matters, what was built, how it was tested, and what changed.
4. State the positive proposition directly. Use contrast only when the distinction changes the scientific claim.
5. Introduce plain meaning before project-specific names, abbreviations, stages, variants, or experiment codes.
6. Make every important sentence easy to parse as subject, action, object, and consequence.
7. Keep caveats accurate and proportionate. Do not turn honesty into self-defeating prose.
8. Keep English and Chinese aligned in meaning, strength, numbers, and terminology.

## Workflow

### 1. Establish the source of truth

- Read the requested passage plus enough surrounding text to understand its role.
- Inspect tables, figures, supplementary files, and evidence records before changing factual claims.
- Record protected items: numbers, denominators, statistical qualifiers, method definitions, citation keys, labels, and cross-references.
- If the project provides a writing guide, terminology policy, venue template, or verified samples from the author, read the relevant source before editing. Treat deliberate authorial and venue conventions as evidence, not as defects. They do not override scientific truth or the user’s explicit instructions.
- Set the edit contract before changing anything:
  - **Review-only:** return findings and evidence without changing files or silently supplying a rewritten manuscript.
  - **Language-only or final cleanup:** preserve section order, paragraph order, lists, tables, quotations, code blocks, and information density unless the user explicitly requests shortening or expansion. Change only the smallest span needed to resolve an identified language problem.
  - **Structural revision:** reorganize only the scope the user authorized, while preserving protected facts and claim strength.
- Trace every new or strengthened factual proposition, entity, number, date, quotation, citation, and causal link to a source in the provided materials. If it cannot be traced, do not add it; report the evidence gap instead.
- Distinguish design rationale and final validated behavior from development history such as issue threads, commits, failed runs, and debugging notes. Development records may establish provenance or expose an error; they do not by themselves establish novelty or value.
- For each contribution, novelty, or value claim, identify the pre-existing problem, the final mechanism or finding, and the supporting evidence. When the claim is comparative, also identify the valid comparison. Ask whether the difficulty would still exist in a correct implementation or valid baseline.

### 2. Build the reader’s argument map

Write a one-line answer for each applicable question:

- What need or problem makes this work worth doing now?
- Why is the task difficult in practice?
- What framework, method, or system was created?
- Which difficulties belong to the research problem or a valid baseline, and which were introduced by the authors’ implementation, configuration, data handling, or experimental setup?
- Which claimed mechanisms remain part of the final work, and what evidence establishes their effect? When the effect is comparative, which valid comparison isolates it?
- What changes when it is used?
- What evidence supports that change?
- What can readers use the result for?
- Where does the demonstrated boundary end?

Reorder sections or paragraphs when the manuscript presents evaluation details before explaining the method, model, system, dataset, or hypothesis being evaluated.

### 3. Diagnose reader friction

Read the text through six lenses:

1. **Logic:** does the reader encounter the need, method, and evidence in the order required to understand them?
2. **Meaning:** does every internal term have a plain-language meaning before its abbreviation or label?
3. **Syntax:** can each sentence be parsed without rereading, and does each pronoun have a clear referent?
4. **Evidence:** can every quantitative or causal statement be traced to a stated comparison, sample, or source?
5. **Attribution:** does each contribution solve a problem that exists independently of an accidental defect, and is it supported by valid final evidence rather than a comparison with the broken version?
6. **Voice:** does the prose sound like a knowledgeable author explaining the work, rather than a template announcing importance?

### 4. Revise in separate passes

1. **Structure pass:** fix section order and paragraph sequence.
2. **Argument pass:** give each paragraph one job and connect evidence to its meaning.
3. **Contribution pass:** classify every claimed advance as a research contribution, an intentional engineering contribution, a development correction, or process history. Remove corrective work and effort from contribution lists; retain material error disclosures where they affect interpretation or reproducibility.
4. **Transition pass:** inspect every sentence handoff. Move a method-specific mechanism or failure mode after the method and its purpose have been introduced.
5. **Terminology pass:** define terms and replace internal shorthand with reader-facing language.
6. **Sentence pass:** remove mechanical contrast, vague subjects, unnecessary nominalization, filler, stacked clauses, and translation artifacts.
7. **Evidence pass:** restore any lost qualifier, verify every number against the source, and exclude or rerun results affected by implementation or experimental errors.
8. **Bilingual pass:** synchronize meaning sentence by sentence; do not let either version make a stronger claim.

Do not polish every sentence into the same rhythm. Preserve natural variation and the author’s domain voice.

### 5. Verify the delivered document

- Search again for rejected phrases, inconsistent terms, unexplained labels, and obsolete wording.
- Compare the final diff with the edit contract. For review-only work, confirm that no content file changed. For language-only work, revert incidental edits to structure, untouched sentences, information density, or author-specific style outside the operation the user requested.
- Search contribution lists, abstracts, highlights, conclusions, cover letters, and rebuttals for claims based on “we encountered,” “we fixed,” repeated attempts, debugging effort, or comparison with an erroneous earlier build. Reclassify them using [references/style-rules.md](references/style-rules.md).
- Confirm that any material correction is disclosed in the appropriate method, reproducibility, validity, or revision record and that the reported evidence comes from the corrected implementation.
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
- Do not treat sentence length, passive voice, nominalization, question headings, metaphors, repeated nouns, or regular sentence rhythm as AI evidence by themselves. Change them only when they cause a specific problem in meaning, logic, emphasis, or readability.
- In language-only mode, leave text that does not exhibit an identified problem unchanged. Do not use “human voice” as permission to add anecdotes, first-person language, casual phrasing, examples, or concrete details that the source does not contain.
- Do not present debugging effort, failed attempts, author-introduced defects, or fixes that merely restore the intended specification as scientific or engineering contributions.
- A failure first noticed during development may motivate a real contribution only when it persists in a correct implementation or valid baseline, the response remains part of the final design, and corrected experiments isolate its effect.
- Never claim improvement by comparing the corrected system with its own erroneous version. Use a valid baseline and rerun every affected result.
- Avoid grand claims, invented novelty, unsupported causality, and silent strengthening during translation.
- Avoid blanket deletion of every negative word. Preserve necessary scientific distinctions, failure results, and boundary conditions.

## Output expectations

When reviewing without edit authorization, provide prioritized findings with locations, supporting evidence, and recommended action. Do not include a rewritten manuscript unless the user requests one.

For a complete audit of a long manuscript, follow [references/long-document-audit.md](references/long-document-audit.md): cover every compiled file, record each finding as location, category, quoted fragment, diagnosis, and suggested rewrite, place global issues (term census, terminology drift, abbreviation first use, numeric mismatches) before per-file lists, and spot-check cited locations before delivery.

When editing files, provide:

- the revised files;
- a concise account of the argument or wording changes;
- protected facts that were checked;
- contribution claims that were retained, reclassified, removed, or left unresolved, including any development error that affected reported evidence;
- compilation and rendered-text results;
- any unresolved claim, terminology, or submission-policy issue.

When the user requests text only, return clean copy-ready prose without LaTeX commands unless LaTeX was requested.
