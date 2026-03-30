# gstack 新手傻瓜式使用指南

> 从零开始：一个想法到上线的完整流程。适合第一次使用 gstack 的开发者。

## 📖 目录

1. [从零开始：一个想法到上线的完整流程](#1-从零开始一个想法到上线的完整流程)
2. [每个技能的使用时机](#2-每个技能的使用时机)
3. [最佳实践工作流](#3-最佳实践工作流)
4. [常见问题排查](#4-常见问题排查)
5. [核心原则](#5-核心原则)
6. [快速参考卡片](#6-快速参考卡片)

---

## 1. 从零开始：一个想法到上线的完整流程

假设你有一个想法：**"我想给用户添加一个导出 PDF 报告的功能"**

### 第 1 步：先别急着写代码！用 `/plan-ceo-review`

```bash
/plan-ceo-review
```

**为什么第一步是这个？**

这个技能会帮你重新思考问题本身。比如：
- "导出 PDF"可能不是最佳方案
- 用户真正需要的是"分享报告"，PDF 只是其中一种方式
- 可能会提出 10 个更好的产品方向让你选择

**你会得到：**
- 产品方向的深度分析
- 多种实现方案的对比
- 优先级排序的建议

### 第 2 步：确定方向后，用 `/plan-design-review`

```bash
/plan-design-review
```

**这个技能做什么？**

对 UI/UX 进行 80 项设计审计：
- 检查 AI 生成的"塑料感"设计模式
- 推断你的设计系统
- 给出具体的改进建议

**你会得到：**
- 设计评分（A/B/C/D）
- AI 塑料感评分
- 具体的设计问题清单

### 第 3 步：技术实现前，用 `/plan-eng-review`

```bash
/plan-eng-review
```

**这个技能做什么？**

工程经理视角的技术审查：
- 画出数据流图
- 识别边界情况和失败模式
- 生成测试矩阵

**你会得到：**
- ASCII 架构图
- 14 种边界情况分析
- 安全风险评估

### 第 4 步：开始实现

现在 Claude 已经理解了完整的需求，会开始写代码。

### 第 5 步：代码写完后，用 `/review`

```bash
/review
```

**自动检查：**
- 生产环境可能爆发的 bug
- 遗漏的边界情况
- 自动修复简单问题

### 第 6 步：测试功能，用 `/qa`

```bash
/qa http://localhost:3000
```

**QA 会做什么：**
- 打开真实浏览器
- 像用户一样点击测试
- 找 bug 并自动修复
- 生成回归测试

### 第 7 步：一切 OK 后，用 `/ship`

```bash
/ship
```

**自动完成：**
- 同步主分支
- 运行测试
- 检查覆盖率
- 推送代码
- 创建 Pull Request

### 第 8 步：更新文档，用 `/document-release`

```bash
/document-release
```

**自动更新：**
- README.md
- ARCHITECTURE.md
- 所有相关文档

---

## 2. 每个技能的使用时机

| 场景 | 使用技能 | 触发时机 |
|------|----------|----------|
| **有一个产品想法** | `/plan-ceo-review` | 任何功能开发的第 1 步 |
| **需要设计 UI** | `/plan-design-review` | 确定产品方向后 |
| **需要设计系统** | `/design-consultation` | 从零开始构建新产品 |
| **要写代码了** | `/plan-eng-review` | 设计确定后，编码前 |
| **代码写完了** | `/review` | 提交 PR 前 |
| **需要测试** | `/qa` | 功能实现后 |
| **纯 QA 报告** | `/qa-only` | 只想找 bug 不修复 |
| **设计 + 修复** | `/design-review` | 设计审计 + 自动修复 |
| **准备上线** | `/ship` | 所有测试通过后 |
| **更新文档** | `/document-release` | 功能上线后 |
| **每周复盘** | `/retro` | 每周五或项目结束后 |
| **浏览器操作** | `/browse` | 需要真实浏览器测试 |
| **导入 Cookies** | `/setup-browser-cookies` | 测试需要登录的页面 |
| **升级 gstack** | `/gstack-upgrade` | 有新版本时 |

### 技能详细说明

| 技能 | 角色 | 做什么 |
|------|------|--------|
| `/plan-ceo-review` | CEO / 创始人 | 重新思考问题，找到 10 星产品方案 |
| `/plan-eng-review` | 工程经理 | 锁定架构、数据流、边界情况、测试 |
| `/plan-design-review` | 高级设计师 | 80 项设计审计，AI 塑料感检测 |
| `/design-consultation` | 设计顾问 | 从零构建完整设计系统 |
| `/review` | .staff 工程师 | 发现生产环境 bug，自动修复 |
| `/ship` | 发布工程师 | 一键推送 + 创建 PR |
| `/browse` | QA 工程师 | 真实浏览器，~100ms 延迟 |
| `/qa` | QA 主管 | 测试、找 bug、修复、生成回归测试 |
| `/qa-only` | QA 报告员 | 纯报告，不修改代码 |
| `/design-review` | 会编码的设计师 | 设计审计 + 自动修复 |
| `/setup-browser-cookies` | 会话管理 | 导入 Chrome/Arc/Brave 的 cookies |
| `/retro` | 工程经理 | 团队周报，代码贡献分析 |
| `/document-release` | 技术写作 | 自动更新所有文档 |

---

## 3. 最佳实践工作流

### 🎯 标准功能开发流程

```
/plan-ceo-review
    ↓
/plan-design-review (如果需要 UI)
    ↓
/plan-eng-review
    ↓
[ Claude 写代码 ]
    ↓
/review
    ↓
/qa http://your-staging-url
    ↓
/ship
    ↓
/document-release
```

### 🐛 修复 Bug 流程

```
/qa http://your-app.com  # 发现并修复 bug
    ↓
/review  # 审查修复
    ↓
/ship  # 推送修复
```

### 🎨 从零开始设计新产品

```
/design-consultation  # 构建设计系统
    ↓
/plan-ceo-review  # 确定产品方向
    ↓
/plan-eng-review  # 技术评审
    ↓
[ 实现 ]
    ↓
/design-review  # 设计审计 + 修复
    ↓
/ship
```

### 📊 每周复盘

```
/retro  # 每周五运行
```

会自动分析：
- 每人代码贡献
- 测试覆盖率趋势
- 需要改进的地方

### 🍪 测试需要登录的页面

```
/setup-browser-cookies  # 从 Chrome/Arc 导入 cookies
    ↓
/qa https://app.your.com  # 现在可以测试登录后的页面
```

---

## 4. 常见问题排查

### ❌ 技能不显示

```bash
cd ~/.claude/skills/gstack
./setup
```

### ❌ `/browse` 失败

```bash
cd ~/.claude/skills/gstack
bun install
bun run build
```

### ❌ 不确定该用哪个技能

**记住这个口诀：**
- **想产品** → `/plan-ceo-review`
- **看设计** → `/plan-design-review`
- **写代码** → `/plan-eng-review`
- **查代码** → `/review`
- **测功能** → `/qa`
- **要上线** → `/ship`

### ❌ 多窗口工作时

当打开 3 个以上 Claude 窗口时，所有问题会自动显示：
- 当前项目名称
- 当前分支
- 上下文信息

### ❌ E2E 测试失败

不要直接说"与我们的更改无关"。正确做法：

1. 在 main 分支运行同样的测试，证明它也失败
2. 如果 main 通过但你的分支失败 — 是你的更改导致的，追踪原因
3. 如果无法在 main 运行，标注"未验证 — 可能相关"

### ❌ 需要登录测试但无法认证

```bash
/setup-browser-cookies
```

会从你的 Chrome/Arc/Brave 浏览器导入 cookies，需要点击"允许"访问钥匙串。

---

## 5. 核心原则

1. **永远从 `/plan-ceo-review` 开始** - 重新思考问题本身，而不是直接实现表面需求
2. **测试优先** - `/qa` 会在真实浏览器中测试，不是模拟
3. **自动化一切** - `/ship` 自动处理测试、审查、发布全流程
4. **文档自动更新** - `/document-release` 保持文档与代码同步
5. **完整性优先** - 当完整实现可行时，不要推荐捷径

---

## 6. 快速参考卡片

```
┌─────────────────────────────────────────────────────┐
│  gstack 快速参考                                     │
├─────────────────────────────────────────────────────┤
│  想法 → /plan-ceo-review                            │
│  设计 → /plan-design-review                         │
│  技术 → /plan-eng-review                            │
│  审查 → /review                                     │
│  测试 → /qa                                         │
│  上线 → /ship                                       │
│  文档 → /document-release                           │
│  复盘 → /retro                                      │
│  Cookies → /setup-browser-cookies                   │
│  升级 → /gstack-upgrade                             │
└─────────────────────────────────────────────────────┘
```

---

## 7. 完整示例对话

### 场景：添加用户头像上传功能

```
你：我想添加用户头像上传功能

你：/plan-ceo-review

Claude: "上传头像"可能不是最佳方案。用户真正需要的是
        "建立个人品牌"。这里有 10 个更好的方向：
        1. 自动生成头像（AI 绘制）
        2. 从 LinkedIn 同步
        3. 上传 + AI 增强
        4. 视频头像
        5. NFT 头像集成
        ...
        你选哪个？

你：选择方案 3 和 5 的组合

你：/plan-design-review

Claude: 设计评分：B  |  AI 塑料感：C
        问题清单（80 项）：
        1. 上传区域太小，移动端难点击
        2. 缺少拖拽上传
        3. 加载状态不明确
        4. 裁剪工具缺失
        ...

你：/plan-eng-review

Claude: 架构设计：
        ┌─────────┐    ┌──────────┐    ┌─────────┐
        │ 上传    │───▶│ 压缩     │───▶│ 存储    │
        │ (同步)  │    │ (异步)   │    │ (S3)    │
        └─────────┘    └──────────┘    └─────────┘

        边界情况：14 种
        - 文件太大 (>10MB)
        - 非图片格式
        - 恶意文件上传
        - 并发上传冲突
        ...

        测试矩阵：23 个用例

你：好的，开始实现吧

[Claude 写代码 - 约 8 分钟，2400 行代码，11 个文件]

你：/review

Claude: [自动修复] 缺少图片类型验证
        [自动修复] S3 清理逻辑不完整
        [提问] 需要添加速率限制吗？

你：需要

你：/qa https://staging.myapp.com

Claude: [打开真实浏览器，实际测试上传流程]
        ✓ 上传流程正常
        ✓ 压缩工作正常
        ✗ 发现 bug：第二次上传不清理预览
        [自动修复，生成回归测试]

你：/ship

Claude: 测试：42 → 51 (+9 个新测试)
        覆盖率：14/14 代码路径 (100%)
        PR: github.com/you/app/pull/42

你：/document-release

Claude: 已更新：
        - README.md (新增头像上传说明)
        - API 文档
        - CHANGELOG.md
```

---

## 8. 下一步

完成第一次完整流程后，你可以：

1. **查看深度文档** - 阅读 [docs/skills.md](docs/skills.md) 了解每个技能的哲学
2. **查看架构** - 阅读 [ARCHITECTURE.md](ARCHITECTURE.md) 了解系统设计
3. **参与贡献** - 阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 学习如何开发 gstack
4. **查看更新日志** - 阅读 [CHANGELOG.md](CHANGELOG.md) 了解最新版本功能

---

**现在就开始吧！** 有任何问题随时问 Claude。

> MIT License • [github.com/garrytan/gstack](https://github.com/garrytan/gstack)
