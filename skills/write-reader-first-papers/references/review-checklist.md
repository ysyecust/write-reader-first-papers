# Final review checklist

## Scope and source fidelity

- [ ] The review-only, language-only, or structural edit contract was identified before work began.
- [ ] Review-only work did not modify content files or silently substitute a rewritten manuscript for findings.
- [ ] Language-only work preserved document structure, information density, unaffected wording, and deliberate author or venue conventions except where the user explicitly requested a change.
- [ ] Relevant writing guides, terminology policies, venue conventions, and verified author samples were consulted when available.
- [ ] Every new or strengthened factual proposition, entity, number, date, quotation, citation, and causal link is traceable to the provided source.

## Argument

- [ ] The opening explains the need before implementation details.
- [ ] The framework or method appears before its evaluation machinery.
- [ ] Each listed contribution addresses a research or engineering need that exists independently of an author-introduced defect.
- [ ] The claimed mechanism remains part of the final work; debugging effort and corrective maintenance are not presented as value.
- [ ] Every section has a clear reader question or claim.
- [ ] Each paragraph has one main job, and adjacent sentences hand off naturally.
- [ ] Method-specific mechanisms and their failure modes appear only after the method is introduced.
- [ ] Evidence is followed by its meaning and practical value.
- [ ] The conclusion explains the framework’s value instead of listing results again.

## Language

- [ ] Direct affirmative statements replace unnecessary “not X but Y” constructions.
- [ ] Necessary contrasts remain where they protect scientific distinctions.
- [ ] Empty signals such as “this distinction is important” have been replaced by consequences.
- [ ] Internal labels are defined in plain language before first use.
- [ ] Pronouns and demonstratives have clear antecedents.
- [ ] Long, clause-heavy sentences have been reviewed aloud.
- [ ] Promotional and generic AI phrases have been removed or supported by metrics.
- [ ] Paragraph openings and endings do not repeat a mechanical template.
- [ ] Long sentences, passive voice, nominalization, questions, metaphors, repeated nouns, and sentence-length patterns were not changed merely because they were suspected AI tells.

## Claims and evidence

- [ ] Numbers and denominators match source evidence.
- [ ] Sampling conditions that affect interpretation remain visible.
- [ ] Each contribution claim identifies a final mechanism or finding and supporting evidence from the valid final implementation or analysis.
- [ ] Improvements use valid baselines or ablations, never the authors’ erroneous earlier version.
- [ ] Results affected by code, configuration, data, or setup errors were rerun or excluded.
- [ ] Material corrections are disclosed with their affected scope and are not renamed as innovation, robustness, or adaptation.
- [ ] Correlation, attribution, transfer, and generalization claims match the experiment.
- [ ] Limitations define scope without becoming the headline.
- [ ] No edit invents novelty, causality, reproducibility, or external validity.

## Front matter and presentation

- [ ] The abstract fits the venue limit and defines abbreviations.
- [ ] Highlights are standalone and fit the character limit.
- [ ] Abstracts, highlights, contribution lists, conclusions, and cover letters describe the final work rather than its debugging history.
- [ ] Keywords use field-standard terms.
- [ ] Captions are concise and tables/figures are cited before appearance.
- [ ] Figure labels, leaders, curves, and markers do not collide at the final manuscript size.
- [ ] The cover letter is concise and editor-facing.
- [ ] Submission declarations reflect the authors’ confirmed facts and current venue rules.

## Bilingual and artifact checks

- [ ] English and Chinese make the same claims with the same strength.
- [ ] Terminology is consistent across main text, SI, figures, and tables.
- [ ] Main text and SI use compatible method, dataset, metric, condition, and experiment names.
- [ ] Data paths, DOI, hashes, and repository descriptions are exact.

## Verification gates

- [ ] The manuscript was reread through the logic, meaning, syntax, evidence, attribution, and voice lenses.
- [ ] Contribution attribution was checked against the final design and valid final evidence, plus valid comparisons and correction records when applicable.
- [ ] The final diff was checked against the edit contract, and incidental edits outside the authorized scope were reverted.
- [ ] Available source validators or compilers were run; unavailable checks are identified.
- [ ] Undefined references and citations were checked when the document format supports them.
- [ ] Rendered text was reread when a rendered document was available.
- [ ] Changed pages were visually inspected when layout could move and a renderer was available.
- [ ] Content, compilation, artifact, and submission checks are reported separately.
