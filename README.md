# 股票投资分析助手

基于 Claude Code + Obsidian 的股票投资分析自动化工具。

---

## 依赖项目

### 1. Claude Code

Anthropic 官方 CLI 工具，用于在终端中使用 Claude 进行代码和任务处理。

**重点说明：**
- 支持扩展上下文、工具调用、多文件编辑
- 安装后需配置 API Key

**官方指引：** https://docs.anthropic.com/en/docs/claude-code

### 2. Financial Services Plugins

Anthropic 官方金融服务插件，提供投资分析相关的 Skills。

**重点说明：**
- 包含 `equity-research:thesis` 等投资分析技能
- 需安装到 Claude Code 的 skills 目录

**官方指引：** https://github.com/anthropics/financial-services-plugins

### 3. Obsidian

本地知识库管理工具，用于存储和管理投资分析报告。

**重点说明：**
- 支持 Markdown 和 YAML front matter
- 支持 Base 功能进行数据汇总展示

**官方指引：** https://obsidian.md

---

## 项目说明

### 运行脚本

| 脚本 | 文件 | 功能 |
|------|------|------|
| 创建分析报告 | `分析脚本/2-创建或更新分析报告.md` | 生成股票投资分析报告 |
| 更新 Base 库 | `分析脚本/3-创建或更新base库.md` | 汇总报告到 Obsidian Base |

### 文件结构

```
├── 分析脚本/           # 运行脚本
├── 投资手册/
│   ├── 投资报告/       # 股票分析报告
│   └── 投资分析报告汇总.base
└── README.md
```
