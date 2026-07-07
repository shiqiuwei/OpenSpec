# OpenSpec（中文文档）

<p align="center">
  <a href="https://github.com/Fission-AI/OpenSpec">
    <picture>
      <source srcset="../assets/openspec_bg.png">
      <img src="../assets/openspec_bg.png" alt="OpenSpec logo">
    </picture>
  </a>
</p>

<p align="center">
  <a href="https://github.com/Fission-AI/OpenSpec/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/Fission-AI/OpenSpec/actions/workflows/ci.yml/badge.svg" /></a>
  <a href="https://www.npmjs.com/package/@fission-ai/openspec"><img alt="npm version" src="https://img.shields.io/npm/v/@fission-ai/openspec?style=flat-square" /></a>
  <a href="../LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square" /></a>
  <a href="https://discord.gg/YctCnvvshC"><img alt="Discord" src="https://img.shields.io/discord/1411657095639601154?style=flat-square&logo=discord&logoColor=white&label=Discord&suffix=%20online" /></a>
</p>

<p align="center">
  <a href="../README.md">English</a> · <strong>中文</strong>
</p>

<details>
<summary><strong>最受欢迎的 Spec 框架之一</strong></summary>

[![Stars](https://img.shields.io/github/stars/Fission-AI/OpenSpec?style=flat-square&label=Stars)](https://github.com/Fission-AI/OpenSpec/stargazers)
[![Downloads](https://img.shields.io/npm/dm/@fission-ai/openspec?style=flat-square&label=Downloads/mo)](https://www.npmjs.com/package/@fission-ai/openspec)
[![Contributors](https://img.shields.io/github/contributors/Fission-AI/OpenSpec?style=flat-square&label=Contributors)](https://github.com/Fission-AI/OpenSpec/graphs/contributors)

</details>
<p></p>

我们的理念：

```text
→ 流动，而非僵化
→ 迭代，而非瀑布
→ 简单，而非复杂
→ 为存量项目而生，而不只适用于新项目
→ 可从个人项目扩展到企业规模
```

> [!TIP]
> **全新工作流现已可用！** 我们重构了 OpenSpec，推出了全新的“工件引导（artifact-guided）”工作流。  
> 运行 `/opsx:propose "你的想法"` 即可开始。→ 详见 [`docs/opsx.md`](./opsx.md)

<p align="center">
  关注 <a href="https://x.com/0xTab">@0xTab</a> 获取更新 · 加入 <a href="https://discord.gg/YctCnvvshC">OpenSpec Discord</a> 获取帮助
</p>

---

## 实际效果（示例）

```text
你：/opsx:explore
AI：你想探索什么？
你：我想加暗色模式，但不确定怎么做更干净。
AI：我先看下你目前的样式结构……
    这里最清晰的路径：CSS 变量 + 轻量主题上下文，
    再加系统偏好检测。不需要新依赖。要不要收敛成变更？
你：好，开始。

你：/opsx:propose add-dark-mode
AI：已创建 openspec/changes/add-dark-mode/
    ✓ proposal.md — 为什么做、改什么
    ✓ specs/       — 需求与场景
    ✓ design.md    — 技术方案
    ✓ tasks.md     — 实施清单
    可以开始实现！

你：/opsx:apply
AI：开始执行任务……
    ✓ 1.1 添加主题 context provider
    ✓ 1.2 创建切换组件
    ✓ 2.1 添加 CSS 变量
    ✓ 2.2 接入 localStorage
    所有任务完成！

你：/opsx:archive
AI：已归档到 openspec/changes/archive/2025-01-23-add-dark-mode/
    规范已更新，可进入下一个功能。
```

<details>
<summary><strong>OpenSpec Dashboard</strong></summary>

<p align="center">
  <img src="../assets/openspec_dashboard.png" alt="OpenSpec dashboard preview" width="90%">
</p>

</details>

---

## 为什么团队采用 OpenSpec

个人开发时，OpenSpec 能让你与 AI 在同一仓库里保持一致。  
团队协作时，难点会迁移：一个功能常常横跨 API 服务、Web 应用和共享库；需求由一个团队维护，另一个团队落地代码……

**[Stores](./stores-beta/user-guide.md)** 就是答案——把规划放在独立仓库中。  
它沿用你熟悉的 `openspec/` 结构（specs + changes），并通过 `git push` 像普通代码一样共享。

- **跨仓功能规划**：一个变更，一份计划，即使代码最终落在三个仓库
- **共享需求源**：平台团队拥有 specs；业务团队在本仓库只读引用，避免 Wiki 漂移
- **先规划后编码**：先在 store 固化计划，再推进到代码仓库

> Stores 目前是 **Beta**。建议从 [Stores 用户指南](./stores-beta/user-guide.md) 开始。

---

## 快速开始

**需要 Node.js 20.19.0 或更高版本。**

全局安装 OpenSpec：

```bash
npm install -g @fission-ai/openspec@latest
```

进入你的项目并初始化：

```bash
cd your-project
openspec init
```

然后和你的 AI 开始协作：

- **还不确定做什么？** 从 `/opsx:explore` 开始：低风险探索，读取现有代码，权衡方案，先收敛计划再写代码。  
  （可参考 [Explore 指南](./explore.md)）
- **目标已明确？** 直接用 `/opsx:propose <你要实现的内容>`。

以上都在默认 profile 中可用。  
如果你希望启用扩展工作流（`/opsx:new`、`/opsx:continue`、`/opsx:ff`、`/opsx:verify`、`/opsx:bulk-archive`、`/opsx:onboard`），可通过 `openspec configure` 进行切换。

> [!NOTE]
> 不确定你的工具是否受支持？查看完整列表：[`docs/supported-tools.md`](./supported-tools.md)  
> 同时支持 pnpm、yarn、bun、nix。详见：[`docs/installation.md`](./installation.md)

---

## 文档

**从这里开始：** [`docs/README.md`](./README.md)（文档主页）  
如果你是新用户，建议先读 [`docs/getting-started.md`](./getting-started.md)，再读 [`docs/how-commands-work.md`](./how-commands-work.md)。

- [快速上手](./getting-started.md)：第一步
- [先 Explore 再动手](./explore.md)：先探索方案，再提交实现
- [命令如何工作](./how-commands-work.md)：Slash 命令与 CLI 的边界
- [核心概念总览](./overview.md)：一页理解全局模型
- [示例与配方](./examples.md)：完整变更案例
- [工作流](./workflows.md)：常用组合与实践模式
- [存量项目接入](./existing-projects.md)：在 Brownfield 项目中采用 OpenSpec
- [编辑变更](./editing-changes.md)：更新工件、回退、处理手工改动
- [命令手册](./commands.md)：Slash 命令与技能说明
- [CLI 参考](./cli.md)
- [Stores（Beta）](./stores-beta/user-guide.md)：在独立仓库规划并共享
- [支持工具](./supported-tools.md)：集成与安装路径
- [概念](./concepts.md)
- [多语言支持](./multi-language.md)
- [自定义](./customization.md)
- [FAQ](./faq.md) · [故障排查](./troubleshooting.md) · [术语表](./glossary.md)

---

## 社区 Schema

第三方 schema bundle 可通过独立仓库分发，提供更具偏好和场景化的工作流扩展（类似生态扩展机制）。

→ 在自定义文档中查看目录：  
[`docs/customization.md#community-schemas`](./customization.md#community-schemas)

---

## 为什么是 OpenSpec？

AI 编程助手很强大，但当需求只存在于聊天上下文时，结果往往不稳定。  
OpenSpec 增加了一层轻量规范：在任何代码落地之前，先把“做什么”对齐清楚。

- **先对齐再实现**：人和 AI 对齐规格后再写代码
- **结构化管理**：每个变更独立目录，包含 proposal/specs/design/tasks
- **流动式迭代**：可随时更新任意工件，不强制僵硬阶段门
- **工具中立**：通过 slash 命令适配 30+ AI 助手与工作流

### 对比

**对比 [Spec Kit](https://github.com/github/spec-kit)（GitHub）**  
Spec Kit 更全面但偏重：阶段门严格、Markdown 负担更大、Python 环境要求更明显。OpenSpec 更轻、更适合快速迭代。

**对比 [Kiro](https://kiro.dev)（AWS）**  
Kiro 功能强，但绑定其 IDE 与模型生态。OpenSpec 不锁工具，优先兼容你现有工作方式。

**对比“没有规范层”**  
只靠 prompt 与历史上下文，AI 输出容易漂移。OpenSpec 用更低的流程成本提升可预测性。

---

## 更新 OpenSpec

**升级包**

```bash
npm install -g @fission-ai/openspec@latest
```

**刷新代理指令**

在每个项目目录执行一次，重新生成 AI 指引并确保最新 slash 命令可用：

```bash
openspec update
```

---

## 使用建议

**模型选择**  
OpenSpec 在高推理模型上效果更好。规划与实现阶段都建议优先使用强推理模型。

**上下文卫生（Context Hygiene）**  
开始实现前建议清理上下文；实现过程中持续保持上下文整洁，可明显提升一致性。

---

## 贡献

**小改动**  
Bug 修复、错别字、微小改进可直接提交 PR。

**大改动**  
新功能、较大重构、架构调整建议先提交 OpenSpec 变更提案，先对齐目标与边界，再进入实现。

撰写提案时，请遵循 OpenSpec 的核心原则：面对不同编码代理、模型和使用场景，方案应尽量具备普适性。

**欢迎 AI 生成代码**  
前提是完成测试与验证。若 PR 含 AI 生成代码，请注明所用编码代理与模型（例如：“Generated with Claude Code using …”）。

### 本地开发

- 安装依赖：`pnpm install`
- 构建：`pnpm run build`
- 测试：`pnpm test`
- 本地开发 CLI：`pnpm run dev` 或 `pnpm run dev:cli`
- 提交规范（单行）：`type(scope): subject`

---

## 其他

<details>
<summary><strong>遥测（Telemetry）</strong></summary>

OpenSpec 会收集匿名使用统计。

采集内容仅包括命令名称与版本号，用于了解使用模式；不采集参数、路径、正文内容或个人隐私数据。CI 环境默认自动禁用。

**关闭方式：**

```bash
export OPENSPEC_TELEMETRY=0
# 或
export DO_NOT_TRACK=1
```

</details>

<details>
<summary><strong>维护者与顾问</strong></summary>

详见 [`MAINTAINERS.md`](../MAINTAINERS.md)

</details>

## 许可证

MIT
