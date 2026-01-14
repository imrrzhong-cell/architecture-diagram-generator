# 贡献指南

感谢您考虑为 Architecture Diagram Generator 项目做出贡献！我们欢迎各种形式的贡献。

---

## 🤝 如何贡献

### 报告问题

如果您发现了 bug 或有功能建议：

1. 检查 [Issues](../../issues) 是否已存在相同问题
2. 如果没有，创建新的 Issue
3. 提供清晰的问题描述和重现步骤
4. 如果可能，附上截图或错误日志

### 提交代码

#### 1. Fork 仓库

点击页面右上角的 "Fork" 按钮

#### 2. 克隆您的 Fork

```bash
git clone https://github.com/YOUR_USERNAME/architecture-diagram-generator.git
cd architecture-diagram-generator
```

#### 3. 创建分支

```bash
git checkout -b feature/your-feature-name
# 或
git checkout -b fix/your-bug-fix
```

#### 4. 进行修改

- 遵循现有代码风格
- 添加必要的注释
- 更新相关文档

#### 5. 提交更改

```bash
git add .
git commit -m "feat: add some amazing feature"
# 或
git commit -m "fix: resolve some issue"
```

**提交信息格式**：

- `feat:` - 新功能
- `fix:` - Bug 修复
- `docs:` - 文档更新
- `style:` - 代码格式调整
- `refactor:` - 代码重构
- `test:` - 测试相关
- `chore:` - 构建/工具相关

#### 6. 推送到您的 Fork

```bash
git push origin feature/your-feature-name
```

#### 7. 创建 Pull Request

1. 访问您的 Fork 页面
2. 点击 "Compare & pull request"
3. 填写 PR 描述
4. 等待 review 和合并

---

## 📋 开发指南

### 项目结构

```
architecture-diagram-generator/
├── architecture-diagram.md      # Claude Code Skill 定义
├── examples/                    # 示例
│   ├── *.json                  # 领域模型示例
│   └── *.html                  # 渲染器示例
└── docs/                        # 文档
```

### 添加新示例

如果您有新的架构图示例：

1. 在 `examples/` 目录下添加文件
2. 遵循命名规范：`{system}-architecture-{type}.ext`
3. 在 README.md 中添加说明
4. 提交 PR

### 扩展 Skill 功能

如果要扩展 Skill 功能：

1. 编辑 `architecture-diagram.md`
2. 添加新的执行步骤或能力
3. 更新文档说明
4. 提供使用示例
5. 提交 PR

### 文档改进

文档改进包括：

- 修正错误
- 添加使用说明
- 翻译文档
- 添加图示
- 改进示例代码

---

## ✨ 代码规范

### Markdown 文件

- 使用一致的标题层级
- 代码块使用语言标识
- 链接使用相对路径
- 添加必要的注释

### JSON 文件

- 使用 2 空格缩进
- 键名使用双引号
- 确保语法正确
- 添加必要的注释（如 supported）

### HTML 文件

- 使用语义化标签
- 添加适当的注释
- 确保可访问性
- 优化性能

---

## 🎨 贡献领域

### 高优先级

- 🔥 更多架构图示例（ERP、MES、BI、OA 等）
- 🔥 国际化支持（英文、日文等）
- 🔥 D3.js 交互式可视化
- 🔥 Figma 插件集成

### 中优先级

- ⭐ VS Code 扩展
- ⭐ CLI 工具
- ⭐ 更多渲染引擎支持
- ⭐ 单元测试

### 低优先级

- 💡 在线编辑器
- 💡 协作功能
- 💡 版本对比
- 💡 导出更多格式

---

## 🐛 Bug 报告模板

```markdown
### 问题描述
简要描述遇到的问题

### 复现步骤
1. 步骤一
2. 步骤二
3. 步骤三

### 期望行为
描述期望的正确行为

### 实际行为
描述实际发生的情况

### 环境信息
- 操作系统：
- Claude Code 版本：
- 浏览器（如适用）：

### 截图/日志
如有，请附上截图或错误日志
```

### 功能请求模板

```markdown
### 功能描述
清晰描述您希望添加的功能

### 使用场景
描述这个功能的使用场景和价值

### 可能的实现
如果您有想法，请描述可能的实现方式

### 示例
如有，请提供示例或参考
```

---

## 📜 行为准则

### 我们的承诺

为了营造开放和友好的环境，我们承诺：

- 尊重不同观点和经验
- 优雅地接受建设性批评
- 关注对社区最有利的事情
- 对其他社区成员表示同理心

### 不可接受的行为

- 使用性别化语言或图像
- 人身攻击或侮辱性评论
- 公开或私下骚扰
- 未经许可发布他人信息
- 其他不专业或不恰当的行为

---

## 📖 资源

- [Claude Code 文档](https://docs.anthropic.com/claude-code)
- [GitHub Flow](https://guides.github.com/introduction/flow/)
- [如何撰写优秀的 Git 提交信息](https://chris.beams.io/posts/git-commit/)

---

## ❓ 常见问题

### Q: 我需要签署什么协议吗？

A: 不需要。提交 PR 即表示您同意使用 MIT 许可证发布您的贡献。

### Q: 我可以用于商业项目吗？

A: 可以。本项目采用 MIT 许可证，允许商业使用。

### Q: 如何获取帮助？

A: 您可以：
- 提交 Issue
- 发起 Discussion
- 查阅现有文档

---

## 🙏 致谢

感谢所有贡献者！您的贡献让这个项目变得更好。

---

**再次感谢您的贡献！** 🎉
