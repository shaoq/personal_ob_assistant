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

### 4. Obsidian Skills

Obsidian 官方 Agent Skills，提供 Obsidian 相关的 Claude Code 技能。

**重点说明：**
- `obsidian-markdown` - 创建和编辑 Obsidian Flavored Markdown
- `obsidian-bases` - 创建和编辑 Obsidian Bases（.base 文件）
- `json-canvas` - 创建和编辑 JSON Canvas 文件
- `defuddle` - 从网页提取干净的 Markdown 内容

**官方指引：** https://github.com/kepano/obsidian-skills

---

## 项目说明

### 运行脚本

| 脚本 | 文件 | 功能 |
|------|------|------|
| 创建 Base 库 | `分析脚本/1-创建base库.md` | 创建 Obsidian Base 汇总视图 |
| 创建分析报告 | `分析脚本/2-创建或更新分析报告.md` | 生成股票投资分析报告 |

### 配置文件

| 文件 | 功能 |
|------|------|
| `分析脚本/投资评级定义.md` | 投资评级标准和评分规则 |
| `分析脚本/行业分类配置.md` | 行业分类和映射配置 |
| `股票列表.md` | 待分析股票清单 |

### 可用技能

本项目使用以下 Claude Code 技能：

| 技能 | 用途 |
|------|------|
| `equity-research:thesis` | 创建或更新投资论点 |
| `obsidian-markdown` | 编辑 Obsidian Markdown 文件 |
| `obsidian-bases` | 管理 Obsidian Base 数据汇总 |
| `defuddle` | 从网页提取投资研究内容 |

### 文件结构

```
├── 分析脚本/                      # 运行脚本和配置
│   ├── 1-创建base库.md            # Base 汇总脚本
│   ├── 2-创建或更新分析报告.md     # 股票分析脚本
│   ├── 投资评级定义.md            # 评级标准定义
│   └── 行业分类配置.md            # 行业分类配置
├── 投资手册/
│   ├── 投资报告/                  # 股票分析报告
│   │   └── {股票名}({代码})-投资分析报告.md
│   └── 投资分析报告汇总.base       # 数据汇总视图
├── 股票列表.md                    # 待分析股票清单
└── README.md
```

### 使用流程

1. **准备股票列表**
   - 编辑 `股票列表.md`，添加待分析的股票代码和名称

2. **创建汇总视图**
   - 首次使用时执行 `分析脚本/1-创建base库.md`
   - 创建 Base 汇总视图

3. **创建分析报告**
   - 执行 `分析脚本/2-创建或更新分析报告.md`
   - 输入股票代码，报告自动生成到 `投资手册/投资报告/` 目录
   - 报告自动汇总到 Base 视图中
