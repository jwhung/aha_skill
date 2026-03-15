# AHA Skills Collection

<div align="center">

**Some skills make you go AHA.**

**Personalized Claude Code Skills Collection**

</div>

---

<details>
<summary><b>🌐 Language / 语言</b></summary>

**[English](#english) | [简体中文](#中文)**

</details>

---

## 中文

<div align="center">

这是个人定制的 Claude Code Skills 集合，每个 skill 都经过精心设计和优化。

</div>

### 📚 目录

- [Skills 列表](#skills-列表-1)
- [安装方法](#安装方法-1)
- [使用指南](#使用指南-1)
- [开发规范](#开发规范-1)
- [贡献指南](#贡献指南-1)

---

### 🎯 Skills 列表

#### 1. 共情文章生成 (empathetic-article)

**功能**：基于"共情-思考-解惑"的爆款内容方法论，将用户提供的模糊中心思想扩展为一篇具有传播力、深度与温度并存的公众号文章。

**触发场景**：
- 用户需要写公众号文章、深度文章、自媒体内容
- 提到"写文章"、"写推送"、"写内容"
- 写作风格需要走心、有深度、有传播力

**核心特性**：
- 灵活配置（情感曲线、叙述视角、文章长度、结构模式）
- 智能素材搜集（历史案例、当代故事、科学研究、文学作品）
- 多种写作模式（经典三段式、留白模式、多线索并行、倒叙式）
- 拒绝套路化，强调真诚和细节

**位置**：`empathetic-article/SKILL.md`

---

#### 2. 图书拆解 (book-breakdown)

**功能**：为书籍生成结构化导读文档，采用《如何阅读一本书》的四层阅读法 × 2 Sigma 掌握学习法。

**触发场景**：
- 提到"读书笔记"、"书籍拆解"、"阅读理解"、"书籍导读"
- 需要总结书籍内容、提取核心概念
- 想要深度理解一本书

**核心特性**：
- 四层阅读法框架（检视阅读、分析阅读、批判阅读、主题阅读）
- 关键术语大白话解释
- 逐章深度笔记模板
- 2 Sigma 测试题设计
- 进度追踪表

**位置**：`book-breakdown/SKILL.md`

---

#### 3. 求真圆桌 (truth-roundtable)

**功能**：AI 圆桌讨论框架，以"求真"为目标，自动召集 3-4 位代表不同立场的历史/当代人物进行多轮深度对话。

**触发场景**：
- 需要"圆桌讨论"、"思想实验"、"多角度分析"、"深度辩论"
- 询问某个议题的不同观点
- 需要辩证思考

**核心特性**：
- 自适应举例机制
- 理性主持人引导
- 每轮提炼争议点并生成可视化思维框架
- 知识网络生成
- 支持多种对话指令（继续、深入、引入新人物、保存）

**人物库**：涵盖科学/理性主义、哲学/思想、经济/社会、心理学/认知、当代科技/AI、科幻/想象力等领域

**位置**：`truth-roundtable/SKILL.md`

**来源**：初始灵感来源于 [李继刚](https://github.com/lijiageng) 的圆桌讨论框架，已根据 Anthropic skill 规范进行改写和优化。

---

#### 4. Skill Creator (skill-creator)

**功能**：创建新 skills、修改和改进现有 skills、评估 skill 性能的完整工具链。

**触发场景**：
- 用户想要创建新 skill
- 编辑或优化现有 skill
- 运行评估测试 skill
- Benchmark skill 性能

**核心特性**：
- 完整的 skill 开发流程（意图捕获 → 访谈研究 → 编写 SKILL.md → 测试用例 → 运行评估 → 改进迭代）
- 支持测试用例设计和评估
- 定性和定量评估方法
- Description 优化以提高触发准确度
- 支持盲对比测试

**位置**：`skill-creator/SKILL.md`

**来源**：来自 [Anthropic 官方](https://github.com/anthropics/claude-code) 的 skill-creator，用于创建、测试和优化 Claude Code skills。

---

#### 5. Modern UI Designer (modern-ui-designer)

**功能**：全流程现代化 UI 设计系统，帮助创建规范、可访问、响应式的用户界面组件代码。

**触发场景**：
- 用户需要设计/重构 UI 界面
- 提到"设计界面"、"UI组件"、"现代化界面"、"设计系统"
- 编写 UI 代码时需要设计规范和改进建议
- 显式调用如"帮我设计"、"设计一个按钮组件"等

**核心特性**：
- 设计系统基础（设计令牌：颜色、间距、排版、阴影、圆角）
- 主题系统（亮色/暗黑模式切换）
- 现代化设计趋势（玻璃态拟物、微交互动画、渐变与色彩）
- 组件设计与实现（按钮、输入框、卡片、导航、表单、表格、模态框）
- 多框架支持（Tailwind CSS、CSS-in-JS、原生 CSS、UI 组件库）
- 无障碍设计（WCAG 2.1 合规、键盘导航、屏幕阅读器支持、色彩对比度）

**位置**：`modern-ui-designer/SKILL.md`

---

### 🚀 安装方法

#### 方法一：直接复制

1. 将 skill 目录复制到你的 Claude skills 目录：
   ```bash
   # Windows
   cp -r empathetic-article C:/Users/YourUsername/.claude/skills/

   # macOS/Linux
   cp -r empathetic-article ~/.claude/skills/
   ```

2. 重启 Claude Code 使 skills 生效

#### 方法二：符号链接（推荐）

使用符号链接可以方便地在仓库更新后同步到本地：

```bash
# Windows (需要管理员权限)
mklink /D C:\Users\YourUsername\.claude\skills\empathetic-article D:\aha_skill\empathetic-article

# macOS/Linux
ln -s D:/aha_skill/empathetic-article ~/.claude/skills/empathetic-article
```

#### 方法三：使用 .skill 文件打包

```bash
# 使用 skill-creator 中的打包脚本
python -m scripts.package_skill <skill-folder-path>
```

---

### 📖 使用指南

#### 基本使用

在 Claude Code 中，当你的请求匹配 skill 的 description 时，Claude 会自动调用相应的 skill。

#### 示例

**共情文章生成**：
```
写一篇关于职业倦怠的公众号文章
```

**图书拆解**：
```
为《思考，快与慢》生成读书笔记
```

**求真圆桌**：
```
我们来圆桌讨论一下人工智能是否拥有真正的创造力
```

**Skill Creator**：
```
我想创建一个新 skill，帮我写代码生成流程图
```

#### 高级技巧

1. **明确触发场景**：在请求中包含 skill description 中的关键词
2. **提供上下文**：详细描述你的需求和期望
3. **迭代优化**：根据输出结果调整输入，持续优化

---

### 🛠️ 开发规范

#### Skill 目录结构

```
skill-name/
├── SKILL.md (必需)
│   ├── YAML frontmatter (name, description required)
│   └── Markdown instructions
└── Bundled Resources (可选)
    ├── scripts/    - 可执行代码
    ├── references/ - 参考文档
    └── assets/     - 资源文件
```

#### Frontmatter 规范

```yaml
---
name: skill-name
description: 简洁描述技能功能和使用场景。包含触发关键词和使用上下文。
---
```

**Description 编写原则**：
- 明确说明技能功能
- 包含触发关键词和场景
- 当前 Claude 有"undertrigger"倾向，description 可以稍微"pushy"一些
- 确保用户能理解何时使用该技能

#### 内容编写原则

1. **渐进式披露**：核心内容在 SKILL.md，详细信息在 references/
2. **保持简洁**：SKILL.md 理想长度 < 500 行
3. **清晰引用**：明确指引何时读取参考文件
4. **解释原因**：说明"为什么"而不只是"做什么"
5. **避免过度约束**：不要使用太多 MUST/ALWAYS/NEVER

#### 测试和评估

参考 `skill-creator/SKILL.md` 中的完整流程：

1. 编写测试用例
2. 运行评估（with-skill vs baseline）
3. 定性和定量评估
4. 迭代改进
5. 优化 description

---

### 🤝 贡献指南

欢迎贡献新的 skills 或改进现有 skills！

#### 贡献流程

1. Fork 本仓库
2. 创建你的 feature branch (`git checkout -b feature/amazing-skill`)
3. 遵循开发规范编写 skill
4. 测试你的 skill
5. 提交更改 (`git commit -m 'Add amazing skill'`)
6. 推送到 branch (`git push origin feature/amazing-skill`)
7. 创建 Pull Request

#### Skill 贡献检查清单

- [ ] 符合 Anthropic skill 规范
- [ ] 包含清晰的 name 和 description
- [ ] Description 包含触发关键词和场景
- [ ] SKILL.md 长度合理（< 500 行）
- [ ] 内容清晰、易于理解
- [ ] 包含使用示例
- [ ] 经过充分测试

---

### 📝 许可证

本项目采用 MIT 许可证。详见 [LICENSE](LICENSE) 文件。

---

### 🔗 相关资源

- [Claude Code 官方文档](https://docs.anthropic.com/claude-code)
- [Claude Code GitHub](https://github.com/anthropics/claude-code)
- [Skill 开发最佳实践](https://docs.anthropic.com/claude-code/skills)

---

### 📮 联系方式

如有问题或建议，请通过以下方式联系：

- GitHub Issues: [jwhung/aha_skill](https://github.com/jwhung/aha_skill/issues)
- Email: eduardohung47@gmail.com

---

**Happy Coding with Claude! 🚀**

---

## English

<details close>
<summary><b>📖 Table of Contents</b></summary>

- [Skills List](#skills-list)
- [Installation](#installation)
- [Usage Guide](#usage-guide)
- [Development Standards](#development-standards)
- [Contributing](#contributing)

</details>

---

### 🎯 Skills List

#### 1. Empathetic Article Generator (empathetic-article)

**Purpose**: Generate viral, deep, and engaging articles based on the "Empathy-Reflection-Insight" methodology. Transform vague ideas into impactful articles with depth and warmth.

**Trigger Scenarios**:
- User needs to write WeChat official account articles, deep articles, or media content
- Mentions "write article", "write post", "create content"
- Writing style needs to be heartfelt, deep, and shareable

**Key Features**:
- Flexible configuration (emotional curve, narrative perspective, article length, structure mode)
- Smart material gathering (historical cases, contemporary stories, scientific research, literary works)
- Multiple writing modes (classic three-stage, empathy-only without resolution, multi-threaded, flashback)
- Rejects formulaic writing, emphasizes sincerity and details

**Location**: `empathetic-article/SKILL.md`

---

#### 2. Book Breakdown (book-breakdown)

**Purpose**: Generate structured reading guides using the "Four Levels of Reading" from "How to Read a Book" combined with Bloom's 2 Sigma Mastery Learning method.

**Trigger Scenarios**:
- Mentions "reading notes", "book breakdown", "reading comprehension", "book guide"
- Needs to summarize book content or extract core concepts
- Wants to deeply understand a book

**Key Features**:
- Four-level reading framework (elementary, inspectional, analytical, syntopical)
- Plain language explanations of key terms
- Chapter-by-chapter deep note templates
- 2 Sigma test design
- Progress tracking table

**Location**: `book-breakdown/SKILL.md`

---

#### 3. Truth Roundtable (truth-roundtable)

**Purpose**: AI roundtable discussion framework that gathers 3-4 historical/contemporary figures representing different viewpoints for deep multi-round dialogues in pursuit of truth.

**Trigger Scenarios**:
- Needs "roundtable discussion", "thought experiment", "multi-perspective analysis", "deep debate"
- Asks about different viewpoints on an issue
- Needs dialectical thinking

**Key Features**:
- Adaptive example mechanism
- Rational moderator guidance
- Extracts controversy points each round and generates visual thinking frameworks
- Knowledge network generation
- Supports multiple dialogue commands (continue, dive deeper, introduce new character, save)

**Character Library**: Covers science/rationalism, philosophy/thought, economics/society, psychology/cognition, contemporary tech/AI, sci-fi/imagination, and more

**Location**: `truth-roundtable/SKILL.md`

**Source**: Initially inspired by [Li Jigang's](https://github.com/lijiageng) roundtable discussion framework, adapted and optimized according to Anthropic skill specifications.

---

#### 4. Skill Creator (skill-creator)

**Purpose**: Complete toolchain for creating new skills, modifying and improving existing skills, and evaluating skill performance.

**Trigger Scenarios**:
- User wants to create a new skill
- Edit or optimize an existing skill
- Run evaluation tests for skills
- Benchmark skill performance

**Key Features**:
- Complete skill development workflow (intent capture → interview/research → write SKILL.md → test cases → run evaluation → iterate/improve)
- Supports test case design and evaluation
- Qualitative and quantitative evaluation methods
- Description optimization to improve trigger accuracy
- Supports blind comparison testing

**Location**: `skill-creator/SKILL.md`

**Source**: From [Anthropic Official](https://github.com/anthropics/claude-code) skill-creator, used for creating, testing, and optimizing Claude Code skills.

---

#### 5. Modern UI Designer (modern-ui-designer)

**Purpose**: Comprehensive modern UI design system for creating accessible, responsive component code with design tokens, theme systems, and WCAG 2.1 accessibility compliance.

**Trigger Scenarios**:
- User needs to design/redesign UI interfaces
- Mentions "UI design", "interface design", "UI components", "modern interfaces", "design systems"
- Writing UI code and needs design guidelines and improvement suggestions
- Explicitly requests like "help me design", "design a button component"

**Key Features**:
- Design system foundation (design tokens: colors, spacing, typography, shadows, border-radius)
- Theme system (light/dark mode switching)
- Modern design trends (glassmorphism, micro-interactions, gradients, color accents)
- Component design and implementation (buttons, inputs, cards, navigation, forms, tables, modals)
- Multi-framework support (Tailwind CSS, CSS-in-JS, vanilla CSS, UI component libraries)
- Accessibility design (WCAG 2.1 compliance, keyboard navigation, screen reader support, color contrast)

**Location**: `modern-ui-designer/SKILL.md`

---

### 🚀 Installation

#### Method 1: Direct Copy

1. Copy the skill directory to your Claude skills directory:
   ```bash
   # Windows
   cp -r empathetic-article C:/Users/YourUsername/.claude/skills/

   # macOS/Linux
   cp -r empathetic-article ~/.claude/skills/
   ```

2. Restart Claude Code for skills to take effect

#### Method 2: Symbolic Link (Recommended)

Using symbolic links makes it easy to sync local updates from the repository:

```bash
# Windows (requires administrator privileges)
mklink /D C:\Users\YourUsername\.claude\skills\empathetic-article D:\aha_skill\empathetic-article

# macOS/Linux
ln -s D:/aha_skill/empathetic-article ~/.claude/skills/empathetic-article
```

#### Method 3: Using .skill File Package

```bash
# Use the packaging script from skill-creator
python -m scripts.package_skill <skill-folder-path>
```

---

### 📖 Usage Guide

#### Basic Usage

In Claude Code, when your request matches a skill's description, Claude will automatically invoke the corresponding skill.

#### Examples

**Empathetic Article Generator**:
```
Write a WeChat article about job burnout
```

**Book Breakdown**:
```
Generate reading notes for "Thinking, Fast and Slow"
```

**Truth Roundtable**:
```
Let's have a roundtable discussion about whether AI possesses genuine creativity
```

**Skill Creator**:
```
I want to create a new skill to help me write code for flowcharts
```

#### Advanced Tips

1. **Be Clear About Trigger Scenarios**: Include keywords from the skill description in your request
2. **Provide Context**: Describe your needs and expectations in detail
3. **Iterate and Optimize**: Adjust your input based on output results for continuous improvement

---

### 🛠️ Development Standards

#### Skill Directory Structure

```
skill-name/
├── SKILL.md (required)
│   ├── YAML frontmatter (name, description required)
│   └── Markdown instructions
└── Bundled Resources (optional)
    ├── scripts/    - Executable code
    ├── references/ - Reference documentation
    └── assets/     - Asset files
```

#### Frontmatter Specification

```yaml
---
name: skill-name
description: Brief description of skill functionality and usage scenarios. Include trigger keywords and usage context.
---
```

**Description Writing Principles**:
- Clearly explain the skill's functionality
- Include trigger keywords and scenarios
- Claude currently has an "undertrigger" tendency, so descriptions can be slightly "pushy"
- Ensure users understand when to use the skill

#### Content Writing Principles

1. **Progressive Disclosure**: Core content in SKILL.md, detailed information in references/
2. **Keep It Concise**: SKILL.md ideal length < 500 lines
3. **Clear References**: Clearly guide when to read reference files
4. **Explain Why**: Explain the "why" not just the "what"
5. **Avoid Over-Constraint**: Don't use too many MUST/ALWAYS/NEVER

#### Testing and Evaluation

Refer to the complete workflow in `skill-creator/SKILL.md`:

1. Write test cases
2. Run evaluation (with-skill vs baseline)
3. Qualitative and quantitative evaluation
4. Iterative improvement
5. Optimize description

---

### 🤝 Contributing

Contributions of new skills or improvements to existing skills are welcome!

#### Contribution Workflow

1. Fork this repository
2. Create your feature branch (`git checkout -b feature/amazing-skill`)
3. Write your skill following development standards
4. Test your skill
5. Commit your changes (`git commit -m 'Add amazing skill'`)
6. Push to the branch (`git push origin feature/amazing-skill`)
7. Create a Pull Request

#### Skill Contribution Checklist

- [ ] Complies with Anthropic skill standards
- [ ] Includes clear name and description
- [ ] Description includes trigger keywords and scenarios
- [ ] SKILL.md has reasonable length (< 500 lines)
- [ ] Content is clear and easy to understand
- [ ] Includes usage examples
- [ ] Thoroughly tested

---

### 📝 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) file for details.

---

### 🔗 Related Resources

- [Claude Code Official Documentation](https://docs.anthropic.com/claude-code)
- [Claude Code GitHub](https://github.com/anthropics/claude-code)
- [Skill Development Best Practices](https://docs.anthropic.com/claude-code/skills)

---

### 📮 Contact

For questions or suggestions, please contact:

- GitHub Issues: [jwhung/aha_skill](https://github.com/jwhung/aha_skill/issues)
- Email: eduardohung47@gmail.com

---

**Happy Coding with Claude! 🚀**

---

<div align="center">

Made with ❤️ by [jwhung](https://github.com/jwhung)

</div>
