# 系统架构图生成器 Skill

## 使用场景

当你需要生成任何系统的精细架构图时，使用此 Skill。

**支持的系统类型**：
- Web 应用（前后端分离、单体、微服务）
- 移动应用（iOS/Android/跨平台）
- 数据平台（数据仓库、BI、实时计算）
- SaaS 平台（多租户、多产品）
- 基础设施（DevOps、监控、日志）
- 任何软件系统

**核心能力**：
- 自动抽取领域知识图谱
- 构建语义结构模型
- 生成视觉语法规范
- 渲染可交互的架构图

---

## 工作流程（PIPELINE）

完整流程分为 4 层：

```
输入（代码/文档/图片）→ 语义建模 → 图形建模 → 渲染输出

Domain Model → Semantic Structure → Visual Grammar → Rendering Engine
领域模型 → 语义结构 → 视觉语法 → 渲染引擎
```

### STEP 1: 抽取知识图谱（Domain Model）

**目标**：把系统的代码/文档/图片变成结构化的"知识"

**6 类基础实体**：

1. **Entity（实体）**
   - 平台类型（PC、Mobile、API等）
   - 业务场景（交易、社交、内容等）
   - 用户角色（管理员、普通用户等）
   - 系统模块（用户中心、订单系统等）
   - 数据域（业务域、支撑域、基础设施域）
   - 外部依赖（第三方服务）

2. **Concept（概念域）**
   - 业务概念（订单、支付、商品等）
   - 技术概念（缓存、队列、数据库等）
   - 领域特定术语

3. **Relations（关系）**
   - is-a（分类）
   - part-of（组成）
   - maps-to（映射）
   - supported-by（支持）
   - belongs-to（归属域）
   - runs-on（运行环境）
   - depends-on（依赖）

4. **Hierarchy（层级结构）**
   - L1: 接入层（终端/渠道）
   - L2: 业务场景层
   - L3: 用户角色层
   - L4: 业务能力层
   - L5: 核心系统层
   - L6: 数据/支撑层
   - L7: 基础设施层

5. **Domain Dictionary（领域词典）**
   - 业务术语中英文对照
   - 技术术语标准化

6. **Constraints（约束条件）**
   - 业务规则约束
   - 技术架构约束
   - 部署环境约束

### STEP 2: 构建语义结构（Semantic Structure）

**目标**：把知识图谱转成"二维映射关系模型"

**核心模型**：
```
Row = Business Layers
Column = Terminals
Cell = Business Units / Capabilities
```

**映射规则**：
- 多对多映射 (m:n)
- 多层域折叠 (hierarchy folding)
- 多语义归属 (domain binding)

**输出格式**：JSON/YAML

### STEP 3: 声明图形语法（Visual Grammar）

**目标**：告诉画图引擎如何将结构映射成图形

**4 类语法**：

1. **Topology Grammar（拓扑语法）**
   - layout = matrix(rows, columns)
   - 网格对齐规则
   - 层级关系表达

2. **Visual Encoding（视觉编码）**
   - encode color by domain（按领域编码颜色）
   - encode border by system type（按系统类型编码边框）
   - encode font weight by hierarchy（按层级编码字重）
   - encode spacing by semantic grouping（按语义分组编码间距）

3. **Alignment Rules（对齐规则）**
   - align horizontally by terminal
   - align vertically by business layer
   - preserve row continuity
   - preserve cell boundaries

4. **Information Density Constraints**
   - min_cells_per_row
   - max_cells_per_row
   - label_length limits

### STEP 4: 渲染输出（Rendering）

**支持 4 路渲染**：

- **Route A**: AI 图生图（不稳定，不推荐）
- **Route B**: 程序渲染（推荐）- Mermaid, Graphviz, D3.js, HTML+CSS
- **Route C**: Design System - Figma/Sketch
- **Route D**: Hybrid Pipeline（最佳）- 组合多种输出

**默认使用 Route B + D**：
1. 生成 HTML + CSS 交互式架构图
2. 可选导出 PDF/PNG/SVG
3. 提供可复用的 JSON 数据资产

---

## 知识获取策略

### 策略 1: 代码库分析（优先）

**适用场景**：用户有代码访问权限

**分析步骤**：
1. 探索项目结构（package.json, pom.xml, go.mod 等）
2. 识别模块/包组织方式
3. 搜索关键类和函数
4. 分析依赖关系
5. 读取配置文件（docker-compose.yml, k8s yaml）

**命令示例**：
```
探索: 寻找项目根目录、配置文件、文档目录
搜索: 搜索 "架构"、"architecture"、"design" 关键词
分析: 识别前后端分离、微服务、数据库等
```

### 策略 2: 文档分析

**适用场景**：有 README、设计文档

**分析内容**：
- README.md（项目介绍、快速开始）
- docs/ 目录（架构文档、API 文档）
- ADR（Architecture Decision Records）
- 设计文档（设计稿、流程图）

### 策略 3: 图片分析

**适用场景**：有现有架构图、手绘草图

**分析能力**：
- 读取图片内容
- 提取文本和结构
- 理解视觉元素
- 重建为结构化数据

### 策略 4: Web 搜索（补充）

**适用场景**：获取行业标准架构

**搜索内容**：
- 行业标准架构模式
- 最佳实践
- 参考架构（如微服务、DDD、事件驱动）

---

## 执行步骤

当用户调用此 Skill 时：

### 第一阶段：信息收集

1. **询问用户**
   - 系统名称/类型
   - 知识来源（代码/文档/图片/描述）
   - 架构图用途（内部/外部/演示）
   - 重点关注（业务/技术/数据）

2. **自动探索**（如果有代码访问权限）
   - 使用 Glob 查找配置文件
   - 使用 Grep 搜索关键词
   - 使用 Read 读取关键文档
   - 构建初步理解

### 第二阶段：模型构建

3. **生成 Domain Model（JSON）**
   - 抽取 6 类实体
   - 定义关系
   - 建立层级
   - 词典翻译

4. **生成 Semantic Structure（JSON）**
   - 定义维度（行/列）
   - 构建矩阵映射
   - 应用约束规则

5. **生成 Visual Grammar（JSON）**
   - 声明布局语法
   - 定义视觉编码
   - 设置约束条件

### 第三阶段：渲染输出

6. **生成渲染引擎（HTML）**
   - 应用视觉语法
   - 生成交互式界面
   - 添加导出功能

7. **提供多种输出**（可选）
   - PDF（打印/演示）
   - PNG（截图/文档）
   - SVG（设计/编辑）
   - JSON（数据资产）

8. **生成总结文档**
   - PIPELINE 执行报告
   - 架构说明文档
   - 使用指南

---

## 输出文件规范

### 文件命名规范
```
{system-name}-domain-model.json           # 领域模型
{system-name}-semantic-structure.json     # 语义结构
{system-name}-visual-grammar.json         # 视觉语法
{system-name}-renderer.html               # 渲染引擎
{system-name}-pipeline-summary.md         # 执行总结
```

### JSON 结构规范

**Domain Model**:
```json
{
  "meta": {...},
  "domain_model": {
    "entities": {...},
    "relations": {...},
    "hierarchy": {...},
    "domain_dictionary": {...},
    "constraints": {...},
    "visual_encoding": {...}
  }
}
```

**Semantic Structure**:
```json
{
  "meta": {...},
  "semantic_structure": {
    "layout_model": "matrix",
    "dimensions": {...},
    "terminal_mapping": {...},
    "layer_mapping": {...},
    "matrix_cells": {...},
    "mapping_rules": {...},
    "constraints": {...}
  }
}
```

**Visual Grammar**:
```json
{
  "meta": {...},
  "visual_grammar": {
    "topology_grammar": {...},
    "visual_encoding": {...},
    "layout_constraints": {...},
    "rendering_grammar": {...}
  }
}
```

---

## 质量标准

### 知识图谱质量
- ✅ 实体抽取完整（不少于 80% 覆盖）
- ✅ 关系定义准确（避免错误关联）
- ✅ 层级结构清晰（符合业务逻辑）
- ✅ 术语翻译准确（中英文对照）

### 语义结构质量
- ✅ 矩阵映射合理（行列逻辑正确）
- ✅ 约束条件满足（符合业务规则）
- ✅ 多对多关系（正确表达复杂关联）

### 视觉语法质量
- ✅ 颜色编码语义化（不使用随机颜色）
- ✅ 层次分明（字体/间距/边框有区分）
- ✅ 可读性保证（信息密度合理）
- ✅ 扁平化设计（无视觉噪音）

### 渲染输出质量
- ✅ 布局准确（严格遵循矩阵模型）
- ✅ 样式一致（符合视觉语法）
- ✅ 交互友好（悬停/点击反馈）
- ✅ 导出功能（PDF/PNG/SVG）

---

## 扩展能力

### 支持的架构类型

1. **分层架构**（Layered Architecture）
2. **微服务架构**（Microservices）
3. **事件驱动架构**（Event-Driven）
4. **六边形架构**（Hexagonal）
5. **DDD 架构**（Domain-Driven Design）
6. **管道架构**（Pipes and Filters）
7. **插件架构**（Plug-in）
8. **云原生架构**（Cloud-Native）

### 支持的视图

1. **业务视图**（Business View）
   - 业务流程
   - 业务能力
   - 业务实体

2. **技术视图**（Technical View）
   - 系统组件
   - 技术栈
   - 接口定义

3. **数据视图**（Data View）
   - 数据模型
   - 数据流
   - 存储结构

4. **部署视图**（Deployment View）
   - 服务器/容器
   - 网络拓扑
   - 基础设施

---

## 最佳实践

### DO ✅

1. **先理解，再建模**
   - 充分探索代码/文档
   - 与用户确认关键概念
   - 建立共识后再生成

2. **迭代优化**
   - 先生成初版
   - 收集反馈
   - 逐步完善

3. **保持简单**
   - 从核心实体开始
   - 逐步添加细节
   - 避免过度复杂

4. **数据驱动**
   - 使用 JSON 作为中间格式
   - 便于版本控制
   - 支持自动化

### DON'T ❌

1. **不要凭空想象**
   - 基于实际代码/文档
   - 不添加不存在的内容
   - 有疑问先询问

2. **不要过度设计**
   - 避免不必要的抽象
   - 保持层级清晰
   - 控制信息密度

3. **不要忽略约束**
   - 业务规则必须遵守
   - 技术限制要考虑
   - 部署环境要适配

---

## 示例用法

### 用户输入示例

**简单调用**：
```
请帮我生成一个电商系统的架构图
系统代码在 /path/to/ecommerce
```

**详细调用**：
```
请生成我的订单管理系统的架构图
- 代码库：/Users/projects/order-system
- 重点：展示微服务拆分和数据流
- 输出格式：HTML + PDF
- 用途：团队技术分享
```

**基于文档**：
```
帮我根据 README.md 生成架构图
项目路径：/path/to/project
重点关注系统分层和模块依赖
```

### 执行响应示例

```
🔍 正在分析系统...
   ✓ 发现项目类型：Spring Boot 微服务
   ✓ 识别模块：8个核心服务
   ✓ 数据库：MySQL + Redis
   ✓ 消息队列：RabbitMQ

📊 正在构建领域模型...
   ✓ 实体抽取：45个
   ✓ 关系定义：89个
   ✓ 层级结构：7层

🎨 正在生成架构图...
   ✓ HTML 交互式版本
   ✓ PDF 导出版本
   ✓ JSON 数据资产

✅ 完成！文件已生成到 /path/to/output/
```

---

## 技术实现

### HTML 渲染器技术栈
- CSS Grid Layout（矩阵布局）
- CSS Variables（主题系统）
- Vanilla JavaScript（交互功能）
- Print CSS（PDF 导出）

### 未来扩展方向
- D3.js 交互式可视化
- React/Vue 组件化版本
- Figma 插件集成
- VS Code 插件集成
- CLI 工具（命令行生成）

---

## 维护说明

### 版本控制
- 每次生成包含版本号
- JSON 文件支持 Git 追踪
- 便于架构演进历史查看

### 更新策略
- 代码变更时重新生成
- 保持 JSON 向后兼容
- 增量更新优于全量重建

---

**Skill Version**: 1.0
**Created**: 2025-01-14
**Methodology**: PIPELINE (Domain Model → Semantic Structure → Visual Grammar → Rendering Engine)
