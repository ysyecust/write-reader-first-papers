# Reader-first academic style rules

## Respect source style and edit scope

When a project supplies a writing guide, venue convention, terminology policy, or verified author sample, use it to interpret the author’s intended voice. Generic AI-voice warnings must not erase a deliberate punctuation habit, sentence pattern, disciplinary convention, or level of formality.

For language-only cleanup, intervene minimally. Preserve the document structure, information density, and unaffected wording unless the user explicitly requests shortening or expansion. A clearer paraphrase may use different words, but every new factual proposition, entity, number, date, quotation, citation, and causal relation must remain traceable to the source.

## 1. Write the proposition directly

Use affirmative sentences that say what the work does.

Avoid using contrast as a default rhetorical engine:

- not X but Y
- not merely X; rather, Y
- not only X but also Y
- 与其说……不如说……
- 不是……而是……
- 并非……而是……
- 不仅……而且……

Keep a contrast only when readers must distinguish two experimentally different claims. Otherwise state Y directly.

Bad:

> The proposed method is not merely accurate but also practically useful.

Better:

> The proposed method reduces median error by 18% and runs within the available memory limit.

Bad:

> 这不是一次性的试错，而是一种可持续积累的过程。

Better:

> 该过程保存每次验证通过的规则，并将其用于后续案例。

## 2. Explain consequences instead of announcing distinctions

Delete empty metacommentary such as:

- This distinction is important.
- It is worth noting that...
- Importantly / Notably / Crucially...
- 需要指出的是……
- 值得注意的是……
- 这一区分十分重要。

State what changes:

Bad:

> Each result has a route and a validation level. This distinction is important.

Better:

> The route records how much of the original case was reused; the validation level records whether the result opened, solved, preserved structure, and reproduced numerical outputs.

## 3. Translate internal language into reader language

Do not expose an internal label before its meaning.

Bad:

> Variant B is evaluated on the matched test set.

Better:

> All methods are evaluated on the same 240 held-out samples. Section 3.2 explains how those samples were selected.

When a label is needed later:

> The retrieval-assisted configuration, called Variant B below, adds retrieved examples before inference.

Watch for unexplained labels such as Variant A, Stage 2, Level 3, Exp-4, matched set, development set, artifact, fidelity score, and sentinel case. Define or replace them according to audience.

## 4. Make terms concrete

Use general terms consistently. A method is a procedure, a model is a representation, a system is an implemented collection of components, a dataset is a defined set of observations, and a workflow is an ordered set of actions. If a paper gives any term a narrower meaning, define it once and keep that meaning.

Prefer verbs and observable outcomes:

- “the simulator opens and solves the case” over “execution feasibility is established”
- “the script compares streams one by one” over “stream-level fidelity assessment is performed”
- “尝试次数上限” over “尝试预算”
- “执行脚本” over “运行器”
- “可逐项比对” over “可差分比较”
- “能够说明的问题” over “支持的主张” when writing for a broad Chinese audience

## 5. Give each sentence one main job

Break a sentence when it simultaneously defines a method, reports three results, adds a caveat, and interprets the result.

For English, investigate sentences above roughly 40 words. For Chinese, investigate sentences above roughly 90 characters. These are review thresholds, not hard limits.

Prefer explicit subjects. Replace repeated “this,” “it,” “these results,” “该方法,” “这一点,” and “其” when the referent could be ambiguous.

## 6. Remove common AI voice

Treat these as warning signs when they add no precise meaning:

- delve, landscape, pivotal, transformative, holistic, seamless
- robust, comprehensive, systematic, effective, significant without a metric
- underscores, highlights, showcases, serves as, paves the way
- moreover, furthermore, notably, importantly at every paragraph opening
- “a wide range of,” “in the context of,” “in order to,” “it can be seen that”
- “系统性地、全面地、有效地、显著地” without evidence
- empty labels such as “the key is:” or “原因如下：” that merely announce the next sentence or list
- repeated paragraph openings such as “moreover,” “therefore,” “此外,” or “因此” when they act as decorative road signs rather than logical transitions
- “this means,” “this shows,” “这意味着,” or “这表明” when the sentence only restates the preceding result
- reveal-style dashes or colon-led list introductions that add emphasis without adding a logical relation
- rigid three-part lists and repeated sentence templates
- promotional endings that repeat “future work” without naming a test

Use technical adjectives only when the paper defines or measures them.

Do not use sentence length, passive voice, nominalization, question headings, metaphors, repeated full nouns, body-level sequence words, or uniform or varied sentence length as automatic evidence of AI writing. These are ordinary writing devices. Revise them only when the particular use obscures meaning, creates a false claim, breaks the author’s style, or produces a demonstrably mechanical passage.

## 7. Frame numbers as evidence

For every headline number, answer:

1. What was measured?
2. Compared with what?
3. On which denominator or sample?
4. Why does the change matter?

Use one or two memorable numbers in an abstract. Put detailed route results, confidence intervals, ablations, and secondary checks in results or tables.

Do not hide conditioning that changes interpretation. Explain sampling in methods and use the shortest accurate wording in abstracts or highlights.

## 8. Be confident without becoming defensive

State the contribution first. State the tested boundary later in direct language.

Weak and defensive:

> Before broader conclusions can be drawn, independent acquisition runs and additional simulators are required.

Reader-first:

> The current study establishes the framework on two simulators and their official archives. Independent runs, user-built flowsheets, and additional simulators are the next tests of transfer.

Do not foreground a weak or special-case result when it is not the paper’s central contribution. Do not conceal it when it defines the claim boundary.

## 9. Separate contribution from development history

Do not turn the authors’ development effort into a property of the research output. For every sentence that frames a challenge, fix, iteration, or recovery as novelty or value, classify what happened:

- **Research contribution:** a method, model, algorithm, dataset, or analysis intentionally developed for a research problem, or a finding established from valid evidence about that problem.
- **Engineering contribution:** an intentional architecture or system capability that meets a stated requirement independently of one accidental defect. Name its engineering scope and support its effect with evidence.
- **Development correction:** a change to faulty code, configuration, data handling, experimental setup, or documentation that restores the intended specification. Report it as correction or quality control, not as contribution.
- **Process history:** debugging time, repeated attempts, discarded implementations, and the sequence in which the authors found and fixed problems. Include it only when provenance, reproducibility, or interpretation requires it.

Apply the relevant tests before retaining a contribution claim:

1. **Independent-problem test:** would the difficulty remain under a correct implementation or valid experimental setup?
2. **Final-design test:** does the proposed mechanism remain necessary and intentional in the final method or system?
3. **Valid-comparison test:** when the claim is comparative, is the effect measured against a legitimate baseline or ablation rather than the authors’ broken earlier version?
4. **Corrected-evidence test:** if an error affected the experiment, were the affected runs repeated after the error was removed, with the reported numbers drawn from the corrected runs?

Failure during development is not automatically irrelevant. A valid baseline may expose a genuine numerical, scientific, or systems limitation, and debugging may reveal it. Claim the resulting contribution only from the independent problem, final mechanism, and valid final evidence—not from the difficulty or effort of discovering it.

Bad:

> After repeated parser failures, we developed an innovative repair strategy that substantially improved coverage.

If the parser failures came from an implementation mistake:

> We corrected the parser before evaluation. All reported coverage results use the corrected implementation.

If the final system includes a separately designed and evaluated validation capability:

> The input validator checks schema and conservation constraints before simulation; the ablation in Section 4.3 measures how these checks affect invalid-case detection.

Do not use pre-correction results as a baseline. If an error changes published or submitted evidence, state what was affected, replace the evidence, and reassess the conclusion without presenting the correction as an advance.

## 10. Optimize for humans and machines

A human reader needs motivation, causal flow, and concrete language. An AI reader needs stable terms, explicit entities, denominators, and unambiguous references.

Write claims in a parseable form:

> Across 12 datasets, the proposed calibration reduces median absolute error from 0.42 to 0.31.

Avoid:

> This improvement further confirms its substantial value under the selected setting.

## 11. Preserve a human authorial voice

- Vary paragraph and sentence length naturally.
- Use the terminology that practitioners actually use.
- Prefer a precise ordinary word over a coined compound.
- Read the sentence aloud. Rewrite it if a domain author would not say it in a seminar.
- Let a paragraph end with its finding or consequence, not a generic claim of importance.
- Do not over-polish direct technical prose into ornate academic language.

## 12. Check the handoff between sentences

Individually correct sentences can still form a paragraph that feels abrupt. For every adjacent pair, ask whether the first sentence gives the reader a reason to expect the concept introduced by the second.

Keep each paragraph on one level of the argument:

- A problem paragraph states the required capability, the practical obstacle, and its consequence.
- A method paragraph introduces the proposed mechanism before discussing that mechanism's numerical difficulty.
- A results paragraph states the measured outcome before interpretation or qualification.

Bad:

> Local optimization can converge to different stationary points. The solution path can turn.

The second sentence assumes a continuation construction that has not been introduced.

Better:

> Local optimization can converge to different stationary points. We therefore connect the target objective to a simpler reference objective. Because the resulting solution path can turn, we track it with an arc-length parameter.

Reread paragraph openings and sentence transitions manually. Mechanical phrase matching cannot determine whether the reader has been prepared for a new concept.

Also compare the grammatical shape of adjacent sentences. If two or more sentences repeat the same clause order, punctuation pattern, and ending without a deliberate rhetorical purpose, change the smallest number of sentences needed to break the template. Preserve deliberate parallelism in definitions, procedures, legal clauses, and compact comparison lists.
