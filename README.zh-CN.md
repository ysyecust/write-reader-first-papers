# 以读者为先的论文写作 Skill

[English README](README.md)

这是一个纯提示词驱动的 Agent Skill，用于修改和审阅学术论文。它帮助初次
阅读论文的人直接理解研究问题、贡献、证据、价值和适用边界，无需猜测内部术语，
也无需适应模板化、宣传式或生硬的表达。

该 Skill 同时支持
[Codex](https://developers.openai.com/codex/build-skills) 和
[Claude Code](https://code.claude.com/docs/en/skills)。它遵循开放的
Agent Skills 格式，不依赖脚本、网络服务或特定模型的 API。

## 能做什么

- 保护数字、分母、引文、术语和主张边界，避免润色改变科学事实。
- 区分有意设计的研究或工程贡献与实现错误、调试投入和纠正性维护。
- 按照读者理解信息所需的顺序重新组织论证。
- 修改生硬、过度防御、宣传式和模板化的表达。
- 在使用内部代号前，先用普通语言说明其含义。
- 解释实验结果的科学意义，同时避免超出证据范围。
- 保持中英文版本在含义、数字和主张强度上的一致。
- 审阅摘要、引言、方法、结果、结论、Highlights、图表说明、补充材料、
  Cover Letter 和审稿回复。

这是一个写作与论证工作流。它不以规避 AI 检测、掩饰作者身份或制造所谓
“人工写作痕迹”为目标。

## 工作方法

Skill 按以下顺序开展工作：

1. 确定事实来源，锁定不得改变的内容。
2. 梳理研究需求、实际障碍、所提工作、支撑证据、研究价值和适用边界，
   并判断每项所谓进展的真实来源。
3. 从逻辑、含义、句法、证据、贡献归因和语言声音六个角度识别阅读障碍。
4. 分别处理结构、论证、贡献归因、过渡、术语、句子和双语同步，避免一次性混改。
5. 将内容检查、证据核对、编译、成品阅读和投稿检查作为相互独立的验证环节。

更详细的规则位于 `references/`，Agent 只在需要时加载。

## 安装方法

### Codex 和 Codex Cloud

个人使用时，将 `skills/write-reader-first-papers/` 复制到：

```text
~/.agents/skills/write-reader-first-papers/
```

项目内使用时，将 `skills/write-reader-first-papers/` 复制或引入目标项目：

```text
.agents/skills/write-reader-first-papers/
```

需要在 Codex Cloud 中使用时，应将该目录提交到目标项目，使其随代码一起
进入云端工作环境。

### Claude Code

个人使用时，将 `skills/write-reader-first-papers/` 复制到：

```text
~/.claude/skills/write-reader-first-papers/
```

项目内使用时，将 `skills/write-reader-first-papers/` 复制到：

```text
.claude/skills/write-reader-first-papers/
```

`agents/openai.yaml` 只提供 Codex 的可选界面信息。Claude Code 可以忽略
该文件；两边共同执行的工作规则位于 `SKILL.md` 和 `references/`。

## 使用方法

可以显式调用：

```text
# Codex
$write-reader-first-papers 检查这篇论文的论证顺序和文字表达。

# Claude Code
/write-reader-first-papers 检查这篇论文的论证顺序和文字表达。
```

当用户请求与 `SKILL.md` 中的描述相符时，两种 Agent 也可以自动加载该 Skill。

示例请求：

- “重写这个摘要，让第一次阅读的人能够直接理解论文贡献。”
- “逐段检查全文是否存在生硬跳转和模板化表达。”
- “压缩所有图表说明，但保留必要定义。”
- “同步中英文版本，同时保证主张强度不发生变化。”
- “检查结论是否说明了研究价值，而不是再次罗列实验数字。”
- “检查贡献列表有没有把我们自己的调试过程和修复错误写成方法创新。”

## 仓库结构

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

## 参与贡献

欢迎提交 Issue 和 Pull Request。新增内容应当：

- 能够适用于不同研究领域；
- 不依赖某篇论文、某个机构或某家模型提供商；
- 足够简洁，值得占用提示词上下文；
- 始终服务于读者理解和证据保真。

## 许可证

MIT
