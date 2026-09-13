# Business Podcast Commentary

一套用于分析商业播客和长访谈的 Agent Skill：把逐字稿重构为有证据边界、可核查、可用于决策的深度商业评述。

它不会只做内容摘要，而是回答四个问题：

1. 嘉宾真正提出了哪些重要判断？
2. 哪些数字和外部事实能够被公开来源支持？
3. 这门生意如何运转，关键约束和利益分配在哪里？
4. 哪些结论只是编辑推演，什么新证据可能推翻它？

## 核心能力

- **总结概括**：围绕商业问题组织内容，不按逐字稿顺序机械复述。
- **事实核查**：识别会影响核心结论的“承重事实”，搜索并打开独立来源进行验证。
- **商业分析**：拆解投入、生产、分发、获客、变现、结算和反馈回路。
- **证据分层**：严格区分说话者原话、公开证据、无法验证的信息和编辑推演。
- **隐性信号**：分析高成本选择、言行差和异常表达，同时保留反方解释与可证伪条件。
- **飞书交付**：在具备 `lark-doc` 能力时，输出高可读性的飞书富文档。

## 适合分析什么

- 商业播客、创始人访谈、投资人对谈
- 财报电话会、行业圆桌、长篇商业讨论
- 需要事实核查、经营视角或投资视角的逐字稿

不适合单纯的语音转写、娱乐内容摘录或只有几句话的简单摘要。

## 快速开始

### 1. 下载完整仓库

下载后保留完整目录，不要只复制 `SKILL.md`；核心方法位于 `references/`。

### 2. 放入 Skill 目录

常见位置：

```text
Claude Code: ~/.claude/skills/business-podcast-commentary/
Codex:       ~/.codex/skills/business-podcast-commentary/
```

Windows 中的 `~` 代表当前用户目录，例如：

```text
C:\Users\你的用户名\.claude\skills\business-podcast-commentary\
```

### 3. 调用

```text
使用 $business-podcast-commentary 分析这份商业播客逐字稿。
```

如果希望得到更明确的任务结果，可以这样说：

```text
使用 $business-podcast-commentary 分析这份逐字稿。
重点核查会影响核心结论的数据，区分嘉宾原话、公开证据和编辑推演，最后列出值得继续监控的指标。
```

## 使用要求

- 必须提供逐字稿、访谈文本或 Agent 可以读取的源文档。
- 事实核查需要 Agent 具备网页搜索和打开原始来源的能力。
- 写入飞书文档需要可用的 `lark-doc` 能力以及用户授权。
- 本仓库不包含 API Key、Token、私人逐字稿或个人知识记录。

## 文件结构

```text
business-podcast-commentary/
├── SKILL.md                 # Skill 主体
├── agents/openai.yaml       # 显示名称与默认调用语
├── references/              # 核查、证据、推演和飞书版式方法
├── README.md                # 使用说明
├── DISCLAIMER.md            # 责任边界
└── LICENSE                  # MIT License
```

## 重要边界

公开来源支持某项说法，不代表来源绝对正确。“编辑推演”和“隐性信号”是基于有限材料的分析，不是事实认定或对个人动机的确定判断。

本项目不构成投资、证券、法律、财务或专业公关意见。详见 [免责声明](DISCLAIMER.md)。

## License

[MIT License](LICENSE) © 2026 Marcus Eran

MIT 是许可证名称，源自 Massachusetts Institute of Technology；不表示本项目与麻省理工学院存在隶属、合作、认证或背书关系。
