# Chinese manuscript friction patterns

Use this catalog when auditing or revising Chinese theses, dissertations, and papers. It refines [style-rules.md](style-rules.md) for patterns that recur in long Chinese technical manuscripts, especially those drafted with heavy AI assistance or written alongside an engineering codebase.

Every pattern is a **warning sign, not a verdict**. Flag an instance only when it causes a specific problem in meaning, logic, emphasis, or readability for a qualified examiner outside the author’s group. The examples below are synthetic; do not copy their wording, numbers, or domain into another manuscript.

## Finding categories

Classify each finding with one primary code. Add a secondary code only when both problems need different fixes.

| Code | Category | Core question |
|---|---|---|
| A | AI-style or formulaic voice | Does the sentence announce, summarize, or balance instead of saying something specific? |
| B | Colloquial, internal, or development vocabulary | Would the word sound out of place in a defended thesis or a journal article? |
| C | Opacity | Can a first-time reader parse the sentence and know what every term, number, and referent means? |
| D | Other writing defects | Is there a grammar error, collocation error, terminology drift, symbol clash, numeric inconsistency, or formatting slip? |

## A. AI-style and formulaic voice

### A1. Abstract verbs that hide the action

Watch for 承接、落实、贯通、打通、衔接、承担、支撑、赋能、服务（带宾语）、连接……与……, used without saying who does what to which object.

- Bad: 统一表示贯通建模、求值与求解三个环节。
- Better: 编译器在同一中间表示中确定变量编号和导数位置，求值程序和求解器直接使用这些编号。

A1 is the most frequent pattern in AI-assisted Chinese technical prose. Replace the abstract verb with the concrete operation, or delete the sentence if it only restates the previous one.

### A2. Empty metaphor nouns

Watch for 链路、闭环、体系、主线、抓手、底座、计算基础、范式、生态、全栈、边界 used as metaphors.

- 边界 is the commonest trap. It often carries several meanings in one document: a partition point, a scope limit, an interface, or a tolerance. Give it one meaning, define it at first use, and replace every other sense with a plain word such as 切分位置、适用范围、接口 or 容差.
- 闭环 and 链路 usually mean “the whole process runs on one device” or “every step is covered”. Say that instead.

### A3. Division-of-labor triplets

The template “X 负责……，Y 负责……，Z 负责……” or “X……，Y……，Z……” with parallel clauses often appears verbatim in the abstract, introduction, method chapter, and conclusion. Keep it once, where the division is defined. Elsewhere, write an ordinary sentence or refer back.

### A4. Meta-narration

Watch for 本节回答……问题、本章进一步回答两个问题、每组实验回答一个独立的问题、下面因此检验……、本节说明相应的设计选择、结果分两面、这里能够确认的是……

- Bad: 本节回答完整链路的计算重心如何随复用方式改变。
- Better: 本节测量完整求解过程中各阶段耗时随复用方式的变化。

### A5. Promotional or empty closing sentences

Watch for 为……提供了坚实/共同的基础、形成了……的方法体系、体现了……的作用、共同表明、具有重要意义, especially when they end every paragraph or section. End with the finding, its consequence, or the next test.

### A6. Abstract-noun subjects with agentive verbs

Watch for “结构信息承担……”“实验揭示了……”“证据评价……”“三类结果分别评价……”“修改行为和交付结果共同表明……”. Give the sentence a human, software, or data subject that can actually perform the action, or turn it into a result statement.

### A7. Bold slogan sentences and named principles

Watch for bold text inside running prose (e.g. \textbf{……协同}) and lists such as “第一项原则……第四项原则”. Bold is for defined terms at first use, not for emphasis. Convert slogan-style principles into ordinary sentences that state the condition and its consequence.

### A8. Dash reveals and colon-led definitions

Watch for “——这正是……”“——这三条正是……” and repeated “X：A，B，C” constructions. Use a dash only for a genuine parenthetical aside. Use a colon only when a list or formal definition follows.

### A9. Contrast templates

Apply the contrast rule in [style-rules.md](style-rules.md). In Chinese technical prose the variants include 而非、而不是、不由……决定、不是……的偶然配置、并非……而是. Long manuscripts often stack three or more of these in one paragraph. Keep only contrasts that separate two experimentally distinct claims.

### A10. Defensive qualifier stacking

Watch for repeated hedges such as “不等价于……”“由独立实验评价”“具体由……决定”“仅作为……记录”“不直接代表……” inside method sections. One scope statement in the right place is enough; move the rest to the limitations section or delete it.

## B. Colloquial, internal, and development vocabulary

### B1. Laboratory-process jargon

Words that describe how the authors ran the project rather than what the reader needs: 冻结、定版、补跑、重跑、回放、烟测、预检、复测、回归、同集回归、正控、协议（实验方案）、口径、档案、归档、批次（as project batch）、臂（experimental arm）、条件批、主估计量（when undefined）.

Replace with the methodological meaning: 冻结的编译器 → 实验期间版本固定的编译器; 口径 → 计时范围 / 统计方法 / 评价指标; 臂 → 对照组; 烟测任务 → 预检用试验任务.

### B2. Software-engineering vocabulary in scientific prose

暴露、消费、拷回、上传、下发、字段、打印、句柄、上下文、运行时、入口、出口、渲染、快照、种子、钉住、热路径、叶子帧、非拥有视图、能力掩码、能力契约、缓存键、静默（失败）、悄然.

Explain the effect in domain terms: 返回指向设备缓冲的非拥有视图 → 直接返回结果在显存中的位置，不复制数据; 静默忽略 → 不报错而直接忽略.

### B3. Colloquial verbs and phrasing

让、把……搬上/放回/交给、拿到、跨过、走……路径、停在、划算、值多少、一趟、两成、摊薄（used loosely）、只验、真收敛、就是、其实.

### B4. Unexplained English and calques

Words left in English or literally translated without need: token, warp, bootstrap, primer（语法引物）, fold（训练折）, budget（预算）, tie-breaker（破平项）, materialize（物化）, expose（暴露）, globalization（全局化）, replay（回放）. Give the field-standard Chinese term with the English in parentheses at first use, then use the Chinese term.

### B5. Project codes, file names, and dates

Task IDs, experiment codes, file extensions, code keywords, and run dates (e.g. “4月28日的三向比较”) belong in appendices or reproducibility records, not in the argument.

## C. Opacity

### C1. Coined terms used before definition

A long manuscript often coins several compound terms (例如“××验收”“××接口组”“会话级××”“××段”“××槽位”“结构身份”). For each coined term, check that:

1. it is defined in plain language at first use in **each** front-matter item (abstract, contribution list, conclusion), since examiners read these alone;
2. the same term keeps one meaning throughout;
3. it is necessary. If a plain phrase works, use the phrase.

### C2. Telegraphic noun stacks

- Bad: 迭代内把物性、方程求值和状态更新留在设备；工况间保留模型、块结构与线性上下文，只重算变化的数值。
- Better: 在一次求解的各轮迭代中，物性、方程求值和状态更新的数据始终保存在显存中；在连续求解多个工况时，保留已编译的模型和线性求解器的符号分析结果，只重新计算发生变化的数值。

### C3. Numbers without frame

Apply the four questions in [style-rules.md](style-rules.md) section 7. In addition, check:

- **快X倍 / 慢X倍** is ambiguous in Chinese (X 倍 or 1+X 倍). Prefer 加速比为X or 耗时为……的1/X.
- **Ratio direction**: “耗时比”“时间比” must state which is numerator.
- **分别** must map one-to-one to the listed items. Flag “分别” followed by more or fewer values than subjects.
- **Count consistency inside a paragraph**: if 15 trials are announced and 12 are described, explain the other 3 in the same place.
- **Inclusion criteria after results**: if a section says nine models but the table lists six, move the inclusion rule before the table.

### C4. Ambiguous referents

“该”“其”“这”“上述”“前者/后者”“这条路径”“这一层” at the start of a paragraph or after a list of several candidates. Repeat the noun.

### C5. Abbreviations before definition

Track the first occurrence of every abbreviation across the **whole compiled document**, not per file. Common slips: an abbreviation defined in chapter 4 but used in chapters 1–3; an abbreviation defined in a later section of the same chapter; abbreviations used in the abstract or conclusion that are only defined deep in the body.

### C6. Logic gaps between clauses

Watch for 因此、故、由此 linking two clauses that have no causal relation, conclusions drawn without the intermediate step (占比下降 → “固定开销被摊薄”), and two unrelated topics joined by 也 in one sentence.

## D. Consistency and mechanical defects

### D1. Terminology drift

One object, several names. Typical drift families in technical theses:

- component names: 模块 / 组件 / 工具 / 软件 / 服务;
- host vs device: 主机 / 宿主端;
- scale series: 序列 / 阶梯 / 尺度 / 档;
- state words: 残余 / 剩余 / 余;
- phase words: 气相 / 汽相;
- procedure words: 降阶 / 约化 / 指数约化;
- experiment groups: 组 / 臂 / 条件;
- the same entity labeled by a plant tag in text and by a short code in tables.

Build a term table and pick one form per concept. Respect any terminology policy supplied by the project.

### D2. Field-standard translations

Use the established Chinese term for well-known concepts, and check against the field’s standard vocabulary (national terminology standards, major textbooks, or the target journal). If a manuscript uses a nonstandard rendering, flag it and propose the standard one rather than inventing a new one.

### D3. Symbol overloading

One symbol with two or more meanings across chapters (e.g. N for both problem size and batch size). List every symbol in the notation table with its chapters, then rename the minority use.

### D4. Cross-section numeric consistency

The same quantity reported in the abstract, introduction, results, discussion, and conclusion must match, or the text must say why it differs (different batch, different metric, different subset). Check:

- headline speedups and percentages;
- counts of models, cases, runs, or trials;
- ranges (min–max) reported in text versus tables;
- the number of categories announced versus listed (“三个范围” vs a five-item definition in an appendix).

### D5. Formatting slips

- question sentences ending in 。;
- mixed Arabic and Chinese numerals for the same kind of count;
- ASCII quotes or en dashes in Chinese text where the Chinese form is required;
- hard-coded chapter numbers mixed with cross-reference commands;
- table headers bolded in some tables but not others;
- leftover blank lines or orphan one-sentence paragraphs after deletions.

### D6. Collocation and structure errors

Subject–predicate mismatch (估计量……计算、吻合……检查), verb–object mismatch (约束精度、压缩开销、调用参数), missing head nouns (“候选”“中位”“墙钟”), and duplicated meaning (最大……低于、重复复制).

## What not to flag

- Necessary contrasts that separate experimental claims.
- Long sentences that remain easy to parse.
- Field-standard English abbreviations that the audience uses daily, once defined.
- Deliberate parallel structure in definitions, procedures, and comparison tables.
- Original titles of published works, frozen historical records, and quoted sources, which should stay verbatim.
