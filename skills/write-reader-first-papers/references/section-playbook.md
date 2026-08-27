# Section playbook

Use these section patterns as diagnostic guides, not mandatory templates. Reorder existing sections or paragraphs only when the edit contract authorizes structural revision. In language-only mode, use the playbook to identify missing logic but report the structural issue instead of silently rebuilding the document.

## Abstract

Use this order unless the venue or study requires another:

1. current need or trend;
2. practical obstacle and its consequence;
3. proposed method, model, system, dataset, or analysis and how it works;
4. evaluation scale plus one or two headline results;
5. scientific value and concrete downstream use.

Define every abbreviation at first use. Replace platform-interface details with a brief functional explanation. Keep unfavorable boundary results secondary unless the boundary itself is the central finding. Check the venue word limit after editing.

Do not promote implementation mistakes, debugging iterations, or corrective maintenance into the abstract’s problem, novelty, or value. If a material error affects the evidence, use the corrected evidence and disclose the affected scope in the appropriate reproducibility or validity statement.

Give the opening problem paragraph one job. Do not introduce a coordinate, path failure, implementation constraint, or other mechanism specific to the proposed method before the method itself appears. In the method paragraph, state what the method does first, then explain the numerical obstacle and the component that resolves it.

Keep the results paragraph selective. Report the evaluation scale, the primary outcome, and the comparison that establishes value; move secondary method-by-method percentages to the Results section.

## Highlights

Prefer three standalone items:

1. what was proposed;
2. what improvement or capability it produced;
3. what breadth of evidence validated it.

Do not use internal variant names, unexplained experiment codes, isolated edge-case numbers, or dense qualifications. Make each item understandable to an editor who has not read the abstract. Check the venue character limit after rendering punctuation.

Each highlight must describe the final work or its validated result. Exclude author effort, debugging chronology, and fixes that only restore intended behavior.

## Introduction

Move through need, bottleneck, gap, proposed work, contribution, and headline evidence. Reuse the abstract’s logic without repeating its sentences.

Explain domain or platform constraints by what they permit, prevent, or require. Introduce the proposed work before detailed evaluation protocols. End the introduction with concrete contributions or a compact roadmap only when it helps navigation.

For each listed contribution, name the pre-existing research or engineering need, the final mechanism or finding, and the evidence. Do not list a bug fix, a repaired experiment, or the difficulty of development as a contribution.

## Methods

Explain the study in the order readers need:

1. problem formulation, assumptions, and scope;
2. proposed method, model, system, dataset, or analytical procedure;
3. algorithmic or implementation details needed to reproduce the work;
4. data, experimental design, and comparison conditions;
5. baselines, ablations, metrics, and statistical analysis.

Do not make readers understand evaluation labels before they understand what is being evaluated.

Describe the final reproducible method, not a success story assembled from debugging chronology. Include a development error only when readers need it to interpret data exclusions, changed results, reproducibility, or the difference between preregistered and executed procedures.

## Results

Build a question-and-answer chain. A useful order is:

1. the primary outcome;
2. robustness, sensitivity, or boundary of the result;
3. comparison with relevant baselines;
4. mechanism or ablation evidence;
5. efficiency and practical behavior;
6. limitations and error analysis.

Open each subsection with the question or result, then present evidence, then interpretation. Keep diagnostic details after the headline result.

Compare the final corrected implementation with valid baselines and ablations. Never use the authors’ erroneous earlier build as evidence of improvement. Rerun or exclude every result affected by a code, configuration, data, or setup error, and identify the affected scope.

## Discussion and limitations

Name what the current evidence establishes. Then distinguish:

- tested scope;
- untested transfer;
- measurement limitations;
- implementation dependence;
- next experiment.

Avoid apologies, speculative defenses, and a long list of every possible future study.

When a material development error affects interpretation, distinguish the error, its correction, the results that were rerun or withdrawn, and the conclusion that remains supported. Do not rename the correction as robustness, adaptation, or innovation.

## Conclusion

Explain the work’s value before repeating evidence. A compact conclusion usually needs:

1. the capability created;
2. the strongest evidence;
3. why the capability matters to the field;
4. one natural closing sentence on the next directions.

Do not reproduce the results section as a list of numbers. Avoid separate, mechanical paragraphs titled “scientific next step” and “systems next step” unless the paper truly requires that distinction.

## Tables and figures

- Reference every table and figure in the body before it appears.
- Keep captions short: identify the object, comparison, and any essential scope.
- Move interpretation into the body.
- Keep table notes for definitions, denominators, and exceptional conditions.
- Avoid turning a caption into a miniature results section.
- Use reader-facing labels in figures; keep experimental codes in notes when needed.
- Inspect annotation placement after the figure is inserted at its final manuscript width. Downscaling can create collisions that are absent in the standalone image.
- Use short labels, deliberate line breaks, leader lines, and unobtrusive white backing where they prevent text from competing with curves or markers.

## Supplementary information

Apply the same language standard as the main paper. Define reused labels again when the SI must stand alone. Keep paths, hashes, filenames, and provenance exact when they are part of the released materials. Prefer soft references to main-paper section names when table numbering may change.

## Cover letter and submission text

Lead with the problem, contribution, evidence breadth, and journal fit. Keep detailed internal numbers out unless one number materially attracts editorial interest. Keep the letter near one page. Distinguish the main manuscript, supplementary material, data or code availability, highlights, and declarations by their submission roles.

In a rebuttal or revision summary, state reviewer-requested corrections and their effect directly. A corrected implementation can strengthen confidence in the revised evidence, but the act of fixing it is not a new contribution unless the revision introduces and evaluates a genuinely new method or capability.

## Bilingual synchronization

- Choose the scientific source version before editing.
- Read any project style guide and verified author samples for both languages; do not force one language’s sentence rhythm or punctuation habits onto the other.
- Maintain a project-specific term map for method names, datasets, metrics, baselines, stages, experimental conditions, abbreviations, and domain terms.
- Translate meaning and claim strength, not English syntax.
- Replace awkward Chinese calques with ordinary technical Chinese.
- Keep numbers, denominators, citation locations, labels, and section order synchronized.
- Recompile and reread both rendered versions after structural edits.
