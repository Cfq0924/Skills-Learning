# Claude Skills 学习中心

> 深入学习、拆解、复刻 Claude Code Skills 的知识库

## 目录结构

```
Skills-Learning/
├── 1-repositories/          # 克隆的原始skill仓库
│   ├── official-skills/      # Anthropic官方skills
│   └── third-party-skills/   # 社区高质量skills
│
├── 2-analysis/              # 源码分析（面向高级开发者）
│   └── <skill-name>/
│       ├── design-patterns.md       # 设计模式分析
│       ├── implementation-notes.md  # 实现要点
│       └── code-walkthrough.md      # 代码走查
│
├── 3-guides/                 # 使用指南
│   └── <skill-name>/
│       ├── README.md             # 入门指南
│       ├── advanced-usage.md     # 高级用法
│       └── best-practices.md     # 最佳实践
│
├── 4-knowledge-base/        # 知识沉淀（面向高级开发者）
│   ├── skill-anatomy.md          # Skill解剖学
│   ├── tool-definition-patterns.md
│   ├── prompt-engineering.md
│   ├── agent-orchestration.md
│   └── design-principles.md
│
├── 5-templates/              # 骨架模板
│   ├── skill-template/
│   └── agent-template/
│
├── 6-exercises/              # 实践练习
│
└── 7-resources/              # 外部资源
    └── awesome-claude-skills.md
```

## 快速开始

### 初学者路线
1. 查看 `7-resources/awesome-claude-skills.md` 了解有哪些高质量skills
2. 从 `1-repositories/` 克隆感兴趣的skill
3. 阅读 `3-guides/<skill-name>/README.md` 入门

### 进阶路线
1. 阅读 `4-knowledge-base/design-principles.md` 理解设计理念
2. 使用 `2-analysis/<skill-name>/` 深度拆解感兴趣的skill
3. 参考 `5-templates/` 创建自己的skill

## 贡献指南

- 每个skill创建对应的分析文档（`2-analysis/`）和使用指南（`3-guides/`）
- 知识沉淀及时更新到 `4-knowledge-base/`
- 练习题放到 `6-exercises/`
