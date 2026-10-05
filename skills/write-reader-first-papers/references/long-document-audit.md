# Long-document prose audit

Use this procedure when the user asks for a complete, located list of prose problems in a thesis, dissertation, book-length report, or multi-file manuscript. The default edit contract is **review-only**: produce findings, do not modify content files.

## 1. Fix the scope from the build, not the folder

- Start from the root source file (e.g. `main.tex`) and follow every `\include`, `\input`, `\subfile`, or equivalent to list the files that are actually compiled. Ignore drafts, archives, and backups that the build does not reach.
- Record which included files are generated (tables, macros, data dumps). Exclude their body from prose review but still review captions, notes, and headers written by hand.
- Note project writing rules (terminology policy, style guide, AGENTS-style instructions). Findings that violate an explicit project rule rank above generic style issues.
- Record file sizes. Long Chinese LaTeX files often have very long lines; plan reading by byte offset or line range so that no part is skipped.

## 2. Read everything, in chunks

- Read every line. Do not sample, skim, or rely on keyword search to find problems; searches miss transitions, logic gaps, and undefined terms.
- When parallel reviewers or subagents are available, split the document into chunks of roughly 30–100 KB, keeping chapter boundaries where possible. Give every reviewer the **same rubric** (categories, examples, output format) so that results merge cleanly.
- Ask reviewers to be exhaustive within their chunk. A thesis chapter commonly yields 100–150 genuine findings; a request for “representative examples” will under-report.
- Ask reviewers to note cross-chunk suspicions (a number or term that should match another chapter) in a separate list. The consolidator checks these in step 4.
- Confirm that each reviewer’s report arrived complete. Long messages can be truncated in transit; recover the full text from the reviewer’s own output or log before merging.

## 3. Record each finding in a fixed format

```
- `file:line` | category | 原文:「exact quoted fragment, ≤80 characters」 | 问题: concise diagnosis | 建议改写: concrete replacement text
```

- Line numbers must refer to the current file version as displayed by the reading tool.
- Quote enough text to locate the fragment with a search.
- Use the categories in [chinese-friction-patterns.md](chinese-friction-patterns.md) (A AI voice, B colloquial/internal, C opacity, D other defects), or the equivalent English categories for English manuscripts.
- Give an actual rewrite, not just an instruction to rewrite. Mark any rewrite that depends on facts the reviewer could not verify (for example, “按实际变量填写”).
- End each file’s section with a two- or three-line summary of its recurring patterns.

## 4. Run whole-document passes after the line-by-line reading

Line-by-line reviewers cannot see the whole manuscript. The consolidator runs these passes over all compiled files:

1. **Term census.** Count high-risk words per file (internal jargon, abstract verbs, metaphor nouns, contrast templates, bold markup). Report a file-by-term table; it shows where a global replacement will remove most findings at once.
2. **Terminology table.** For each concept with more than one name, list all variants and their locations, and propose one form. Check the project’s terminology policy first.
3. **Abbreviation first use.** For every abbreviation, find the first occurrence in compile order and the first definition. Flag every use before the definition.
4. **Symbol table.** Compare the notation list with actual use; flag overloaded symbols.
5. **Numeric cross-check.** Collect every headline number that appears in more than one place (abstract, contribution list, chapter summaries, conclusion, appendices) and compare. Report mismatches as items for the author to verify; do not decide which value is correct without the source data.
6. **Front-matter compression check.** Read the abstract, contribution list, and conclusion as a stranger would. Flag every coined term, internal group name, or number without its comparison.

## 5. Verify before delivering

- Spot-check at least ten findings spread across files: open the cited line and confirm the quoted fragment is there.
- Confirm that no content file changed (`git status` or equivalent).
- State clearly which findings are judgments (readability, whether a term counts as defined) and which are mechanical facts (duplicated definition, mismatched number).

## 6. Deliver a prioritized report

Structure the report as:

1. **Scope and method.** Files covered, files excluded, categories, line-number version.
2. **Global issues.** The census table, terminology drift families, project-rule violations, numeric mismatches to verify, and the front-matter compression problem. Recommend fixing these globally first; a consistent term table and a definition pass usually remove a large share of the line-level findings.
3. **Per-file findings.** In compile order, each finding in the fixed format, with clickable locations when the medium supports links.

In the chat reply, point to the report, highlight only the decisions that need the author (numbers to verify, terms to choose, which sections to fix first), and offer to start editing from the highest-priority section. Do not paste the full list into the reply.

## Fix order when the author authorizes edits

1. Apply project terminology rules and the chosen term table.
2. Define coined terms and abbreviations at first use; replace unnecessary internal vocabulary.
3. Rewrite the abstract, contribution list, chapter summaries, and conclusion.
4. Work through the remaining line-level findings chapter by chapter, under a language-only edit contract unless the author authorizes structural changes.
5. Rerun the census and the abbreviation and numeric passes, then compile and reread the rendered text.
