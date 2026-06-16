# 达晨财智投资助手 (dacheng-pe)

一级市场股权投资全流程 Skill，覆盖赛道研究、项目尽调、投资决策、风控回复、投后管理五大场景。支持 **Claude Code / Hermes / OpenCode** 三个平台。

## 📦 包含的五大功能

| 功能 | Claude Code | Hermes | OpenCode | 对应角色 |
|------|:--:|:--:|:--:|---------|
| 行业研究与赛道梳理 | `/hangyan` | `hangyan` skill | `hangyan` agent | 角色1 |
| 项目分析与尽调 | `/jinzhi` | `jinzhi` skill | `jinzhi` agent | 角色2 |
| 投资决策与上会材料 | `/toujue` | `toujue` skill | `toujue` agent | 角色3 |
| 风控报告回复 | `/fengkong` | `fengkong` skill | `fengkong` agent | 角色4 |
| 投后管理 | `/touhou` | `touhou` skill | `touhou` agent | 角色5 |

---

## 🖥️ 方式一：Claude Code 安装

在 Claude Code 的 `settings.json` 中添加（终端输入 `claude config` 打开）：

```json
{
  "extraKnownMarketplaces": {
    "dacheng-pe": {
      "source": {
        "source": "github",
        "repo": "yuanpingxu/dacheng-pe-skill"
      }
    }
  },
  "enabledPlugins": {
    "dacheng-pe@dacheng-pe": true
  }
}
```

重启 Claude Code 后，输入 `/hangyan 基因治疗` 即可使用。

更新：`claude plugin update dacheng-pe`

---

## 🔧 方式二：Hermes 安装

### 方法 A：从 GitHub 直接安装（推荐）

```bash
hermes plugins install yuanpingxu/dacheng-pe-skill
```

### 方法 B：添加 Tap 源

```bash
hermes skills tap add yuanpingxu/dacheng-pe-skill
hermes skills install hangyan
hermes skills install jinzhi
hermes skills install toujue
hermes skills install fengkong
hermes skills install touhou
```

安装后直接说"帮我分析基因治疗赛道"即可自动匹配对应 skill。

更新：`hermes plugins update dacheng-pe-skill`

---

## 🤖 方式三：OpenCode 安装

### 步骤 1：克隆仓库
```bash
git clone git@github.com:yuanpingxu/dacheng-pe-skill.git ~/.opencode/dacheng-pe
```

### 步骤 2：创建 Agent
```bash
opencode agent create --path ~/.opencode/dacheng-pe/opencode/agents/hangyan.md --description "行业研究与赛道梳理"
opencode agent create --path ~/.opencode/dacheng-pe/opencode/agents/jinzhi.md --description "项目分析与尽调"
opencode agent create --path ~/.opencode/dacheng-pe/opencode/agents/toujue.md --description "投资决策与上会材料"
opencode agent create --path ~/.opencode/dacheng-pe/opencode/agents/fengkong.md --description "风控报告回复"
opencode agent create --path ~/.opencode/dacheng-pe/opencode/agents/touhou.md --description "投后管理"
```

使用时在 OpenCode 中选择对应 agent 即可。

更新：`cd ~/.opencode/dacheng-pe && git pull`

---

## 📁 目录结构

```
dacheng-pe-skill/
├── commands/              ← Claude Code 斜杠命令入口
├── skills/                ← Claude Code 核心工作流
│   ├── industry-research/
│   ├── project-diligence/
│   ├── investment-decision/
│   ├── risk-control/
│   └── portfolio-mgmt/
├── hermes/skills/         ← Hermes 兼容 Skill
│   ├── hangyan/SKILL.md
│   ├── jinzhi/SKILL.md
│   ├── toujue/SKILL.md
│   ├── fengkong/SKILL.md
│   └── touhou/SKILL.md
├── opencode/agents/       ← OpenCode Agent 配置
│   ├── hangyan.md
│   ├── jinzhi.md
│   ├── toujue.md
│   ├── fengkong.md
│   └── touhou.md
├── references/
│   ├── templates/         ← 达晨模板详细内容
│   └── style-guide.md     ← 样板写作风格
└── .claude-plugin/
    └── plugin.json        ← 插件元信息
```

## 🔗 依赖

建议配合以下 Skills 使用（各平台均有对应版本）：

- `private-equity@claude-for-financial-services`
- `financial-analysis@claude-for-financial-services`
- `equity-research@claude-for-financial-services`
- `investment-banking@claude-for-financial-services`
- `minesweeper`（财报排雷）
