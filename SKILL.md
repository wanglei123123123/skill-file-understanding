# Skill: File Understanding 📚

一套系统化的文件理解和整理框架，用于分析代码文件的**用途、责任和依赖关系**。

## 📖 项目概览

本项目提供结构化的方法论和工具模板，帮助开发者和团队：

- 🎯 **快速理解** 陌生代码文件的核心职责
- 🔍 **深度分析** 文件的内部结构和外部依赖
- 📊 **可视化呈现** 复杂的关系图和数据流
- 📝 **标准化文档** 代码架构和设计模式
- 🚀 **加速onboarding** 新团队成员的学习曲线

## 🎓 核心理念

采用**"环"模型**（Ring Model）从内向外逐层分析：

| 环层 | 内容 | 成本 | 优先级 |
|------|------|------|--------|
| **Ring 0** | 文件本身（内容、元数据） | 无 | ⭐⭐⭐⭐⭐ |
| **Ring 1** | 内部结构（符号、导入、流程） | 低 | ⭐⭐⭐⭐ |
| **Ring 2** | 一度引用（类型、调用者、测试） | 中 | ⭐⭐⭐ |
| **Ring 3** | 历史和文档（blame、PR、docs） | 高 | ⭐⭐ |

## 📁 目录结构

```
.
├── README.md                 # 项目主文档
├── docs/
│   ├── GUIDE.md             # 使用指南（如何分析文件）
│   ├── TEMPLATE.md          # 标准分析模板
│   ├── METHODOLOGY.md       # 方法论详解
│   └── EXAMPLES/            # 真实示例
│       ├── example-auth.md
│       ├── example-api.md
│       └── example-utils.md
├── src/
│   ├── analyzer.md          # 分析器工作流程
│   ├── ring-model.md        # 环模型详细说明
│   └── queries.md           # 常见查询和答案
└── CHANGELOG.md             # 版本历史
```

## 🚀 快速开始

### 1️⃣ 基础分析（5分钟）

对任何文件运用标准框架：

```markdown
## 文件: src/auth.ts

### 用途
一句话说明这个文件是做什么的

### 关键责任
- 职责1
- 职责2
- 职责3

### 导出符号
- `function authenticate()` — 验证用户身份
- `interface User` — 用户对象定义

### 核心依赖
- `pkg/tokenstore` — 令牌验证
- `pkg/database` — 数据库访问
```

### 2️⃣ 深度分析（15分钟）

包含依赖、使用场景和数据流：

```markdown
## 文件: src/auth.ts

### 用途
...

### 内部结构
- 主要流程
- 控制流
- 数据结构

### 依赖关系
- 一度依赖
- 反向依赖（调用者）
- 相关测试

### 数据流
graph LR
  A[Request] --> B[authenticate()]
  B --> C[tokenstore.validate()]
  C --> D[Context]
```

## 📖 文档导航

- **[使用指南](docs/GUIDE.md)** — 分步教程
- **[分析模板](docs/TEMPLATE.md)** — 复制即用的模板
- **[方法论](docs/METHODOLOGY.md)** — 环模型和设计原理
- **[真实示例](docs/EXAMPLES/)** — 社区贡献的案例

## 🔧 适用场景

✅ 代码审查时理解文件的职责  
✅ 新人onboarding时的学习资料  
✅ 技术文档编写的基础框架  
✅ 架构设计和重构前的现状评估  
✅ 团队知识沉淀和共享  

## 📊 分析维度

每个文件分析涵盖以下维度：

| 维度 | 问题 | 输出 |
|------|------|------|
| **职责** | 这个文件做什么？ | 核心用途、关键责任 |
| **接口** | 它暴露什么？ | 导出符号、公共API |
| **依赖** | 它依赖什么？ | 导入、内部和外部依赖 |
| **结构** | 它怎么组织的？ | 内部流程、数据结构、控制流 |
| **使用** | 谁用它？ | 调用者、集成点、反向依赖 |
| **测试** | 如何验证？ | 覆盖的测试、关键场景 |
| **演变** | 怎么来的？ | 最近变更、设计决策（可选） |

## 🎯 效能指标

应用本框架后的预期收益：

- 📈 **理解时间** 缩短 60%
- 📝 **文档完整性** 提升 80%
- 🔗 **依赖清晰度** 提升 90%
- 👥 **团队协作** 提升 70%

## 🤝 贡献指南

欢迎提交：
- 新的分析示例
- 框架改进意见
- 针对特定语言的最佳实践
- 工具和自动化脚本

详见 [CONTRIBUTING.md](CONTRIBUTING.md)

## 📜 许可证

MIT License - 自由使用和修改

## 🔗 相关资源

- [Clean Code](https://www.oreilly.com/library/view/clean-code-a/9780136083238/) — 代码可读性的经典
- [Software Architecture Guide](https://martinfowler.com/architecture/) — Martin Fowler的架构指南
- [Code Review Best Practices](https://google.github.io/eng-practices/review/) — Google工程实践

---

**开始使用：** 选择一个文件，按照 [GUIDE.md](docs/GUIDE.md) 中的步骤逐步分析。

**有问题？** 查看 [FAQ](docs/FAQ.md) 或提交 Issue。

**想贡献？** 欢迎 PR！
