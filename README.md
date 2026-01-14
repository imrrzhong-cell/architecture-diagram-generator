# 🏗️ Architecture Diagram Generator

> **系统架构图生成器** - 基于 PIPELINE 方法论的专业级架构图自动生成工具

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skill](https://img.shields.io/badge/Claude_Code-Skill-blue.svg)](https://claude.ai/claude-code)
[![Methodology](https://img.shields.io/badge/Methodology-PIPELINE-green.svg)](#pipeline-方法论)

---

## ✨ 特性

- 🎯 **自动化生成** - 从代码/文档/图片自动提取架构信息
- 📊 **数据驱动** - 结构化 JSON 数据资产，可复用、可维护
- 🎨 **专业级输出** - 遵循架构可视化最佳实践
- 🔄 **多格式支持** - HTML、PDF、PNG、SVG、Mermaid、Graphviz
- 🌐 **多系统支持** - Web 应用、微服务、数据平台、SaaS 等
- 📱 **响应式设计** - 适配各种屏幕尺寸

---

## 🎬 快速开始

### 使用 Claude Code Skill

将 `architecture-diagram.md` 放入您的 Claude Code skills 目录：

```bash
# macOS/Linux
cp architecture-diagram.md ~/.claude/skills/

# Windows
copy architecture-diagram.md %USERPROFILE%\.claude\skills\
```

然后在 Claude Code 中：

```
请帮我生成一个 [系统名称] 的架构图
```

### 示例

```
请帮我生成一个 CRM 系统的架构图
```

Claude Code 会自动：
1. 📖 分析系统代码/文档
2. 🧠 构建领域知识图谱
3. 📐 设计语义结构
4. 🎨 应用视觉语法
5. 💻 生成可交互的架构图

---

## 📐 PIPELINE 方法论

本工具基于 **四层 PIPELINE** 方法论：

```
输入（代码/文档/图片）
    ↓
[STEP 1] Domain Model（领域模型）
    → 抽取知识图谱
    → 定义实体、关系、层级
    → 构建领域词典
    ↓
[STEP 2] Semantic Structure（语义结构）
    → 构建二维映射模型
    → Terminal × BusinessLayer
    → 多对多关系、层级折叠
    ↓
[STEP 3] Visual Grammar（视觉语法）
    → 拓扑语法、视觉编码
    → 对齐规则、约束条件
    → 设计规范
    ↓
[STEP 4] Rendering Engine（渲染引擎）
    → HTML 交互式架构图
    → PDF/PNG/SVG 导出
    → JSON 数据资产
    ↓
输出：架构图 + 数据 + 文档
```

---

## 📁 项目结构

```
architecture-diagram-generator/
├── README.md                    # 项目文档
├── architecture-diagram.md      # Claude Code Skill 定义
├── LICENSE                      # MIT 开源协议
├── CONTRIBUTING.md              # 贡献指南
├── examples/                    # 示例
│   ├── crm-architecture-*.json # CRM 系统领域模型
│   ├── crm-architecture-*.html # CRM 系统渲染器
│   └── 99platform-architecture-*.html # 电商平台示例
└── docs/                        # 文档
    ├── PIPELINE-EXECUTION-SUMMARY.md
    └── CRM-PIPELINE-SUMMARY.md
```

---

## 🎨 输出示例

### CRM 系统架构图

```bash
# 查看 CRM 示例
open examples/crm-architecture-renderer.html
```

**包含内容**：
- 🔵 **客户管理** - 档案、分层、标签、画像、360 视图
- 🔵 **销售管理** - 线索→商机→报价→合同→订单→回款
- 🟢 **营销管理** - 活动、旅程、多渠道、自动化
- 🟠 **服务管理** - 工单、知识库、呼叫中心、SLA
- 🟣 **数据分析** - 销售/客户/营销/服务/预测
- 🔵 **全渠道** - PC Web / Mobile App / Mobile Web / Open API

### 电商平台架构图

详见 `examples/99platform-architecture-renderer.html`

---

## 🛠️ 核心概念

### 1. 领域模型 (Domain Model)

**6 类基础实体**：
- **Entity（实体）** - 平台类型、业务场景、用户角色、系统模块
- **Concept（概念域）** - 业务概念、技术概念
- **Relations（关系）** - is-a, part-of, maps-to, supported-by, depends-on
- **Hierarchy（层级结构）** - L1-L7 层级定义
- **Domain Dictionary（领域词典）** - 中英文术语对照
- **Constraints（约束条件）** - 业务规则、技术限制

### 2. 语义结构 (Semantic Structure)

**二维映射模型**：
```
Row = Business Layers
Column = Terminals
Cell = Business Units / Capabilities
```

**映射规则**：
- 多对多映射 (m:n)
- 多层域折叠 (hierarchy folding)
- 多语义归属 (domain binding)

### 3. 视觉语法 (Visual Grammar)

**4 类语法**：
- **Topology Grammar（拓扑语法）** - 布局规则
- **Visual Encoding（视觉编码）** - 颜色、边框、字体、间距
- **Alignment Rules（对齐规则）** - 水平/垂直对齐
- **Information Density Constraints** - 信息密度控制

### 4. 渲染引擎 (Rendering Engine)

**4 路渲染**：
- Route A: AI 图生图（不稳定）
- Route B: 程序渲染（推荐）✅
- Route C: Design System
- Route D: Hybrid Pipeline（最佳）✅

---

## 📊 支持的架构类型

- ✅ **分层架构** (Layered Architecture)
- ✅ **微服务架构** (Microservices)
- ✅ **事件驱动架构** (Event-Driven)
- ✅ **DDD 架构** (Domain-Driven Design)
- ✅ **六边形架构** (Hexagonal)
- ✅ **云原生架构** (Cloud-Native)
- ✅ **前后端分离** (Frontend-Backend Separation)
- ✅ **数据平台** (Data Platform)
- ✅ **SaaS 平台** (Multi-tenant SaaS)

---

## 🎯 使用场景

### 产品规划
- 系统架构设计
- 技术选型决策
- 功能模块规划

### 技术分享
- 团队技术分享
- 架构评审会议
- 客户演示汇报

### 文档补充
- 系统设计文档
- API 文档
- 新人培训材料

### 系统集成
- 第三方系统对接
- API 接口设计
- 数据同步方案

---

## 🔧 高级用法

### 基于代码生成

```
请生成 /path/to/project 的架构图
重点关注：微服务拆分和数据流
输出：HTML + PDF
```

### 基于文档生成

```
请根据 README.md 生成架构图
项目路径：/path/to/project
需要：详细的架构说明
```

### 基于现有架构图

```
请根据这张架构图生成新版本
[上传图片]
需要：转成可编辑的 HTML 版本
```

---

## 📦 输出文件

每次生成会创建以下文件：

| 文件 | 说明 | 格式 |
|------|------|------|
| `{system}-domain-model.json` | 领域模型 - 知识图谱 | JSON |
| `{system}-semantic-structure.json` | 语义结构 - 二维映射 | JSON |
| `{system}-visual-grammar.json` | 视觉语法 - 图形规范 | JSON |
| `{system}-renderer.html` | 渲染引擎 - 交互式架构图 | HTML |
| `{system}-pipeline-summary.md` | 执行报告 - 完整文档 | Markdown |

---

## 🌟 核心价值

### 1. 数据驱动设计
- 从代码/文档自动提取，不是手动绘制
- 结构化 JSON 数据，可版本控制
- 一次生成，多次使用

### 2. 多格式输出
- 一份数据源
- 支持 HTML/PDF/PNG/SVG/Mermaid/Graphviz
- 满足不同场景需求

### 3. 自动化潜力
- 可构建 SaaS 级别的自动制图引擎
- 可集成到 CI/CD 流程
- 代码变更时自动更新架构图

### 4. 业务一致性
- 约束条件内置
- 视觉规范统一
- 业务逻辑准确

---

## 🤝 贡献

欢迎贡献！请查看 [CONTRIBUTING.md](CONTRIBUTING.md) 了解详情。

### 贡献方式

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

---

## 📝 许可证

本项目采用 [MIT License](LICENSE) 开源协议。

---

## 🙏 致谢

- Claude Code - 强大的 AI 编程助手
- PIPELINE 方法论 - 四层架构图生成方法
- 所有贡献者

---

## 📮 联系方式

- Issues: [GitHub Issues](https://github.com/YOUR_USERNAME/architecture-diagram-generator/issues)
- Discussions: [GitHub Discussions](https://github.com/YOUR_USERNAME/architecture-diagram-generator/discussions)

---

## 🎉 开始使用

立即体验架构图自动生成的魅力！

```bash
# 1. 克隆仓库
git clone https://github.com/YOUR_USERNAME/architecture-diagram-generator.git

# 2. 安装 Claude Code Skill
cp architecture-diagram.md ~/.claude/skills/

# 3. 查看 CRM 示例
open examples/crm-architecture-renderer.html

# 4. 开始生成您的架构图！
```

---

<div align="center">

**Made with ❤️ using Claude Code**

[⭐ Star](../../stargazers) | [🍴 Fork](../../network/members) | [📖 Documentation](docs/) | [💡 Examples](examples/)

</div>
