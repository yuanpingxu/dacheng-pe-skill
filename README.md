# 达晨财智投资助手 (dacheng-pe)

一级市场股权投资全流程 Skill，覆盖赛道研究、项目尽调、投资决策、风控回复、投后管理五大场景。

## 安装

在 Claude Code 的 `settings.json` 中添加：

```json
{
  "extraKnownMarketplaces": {
    "dacheng-pe": {
      "source": {
        "source": "github",
        "repo": "<your-repo>/dacheng-pe-skill"
      }
    }
  },
  "enabledPlugins": {
    "dacheng-pe@dacheng-pe": true
  }
}
```

## 包含的命令 (Commands)

| 命令 | 功能 | 对应角色 |
|------|------|---------|
| `/xingyan` | 行业研究与赛道梳理 | 角色1 |
| `/jinzhi` | 项目分析与尽调 | 角色2 |
| `/toujue` | 投资决策与上会材料 | 角色3 |
| `/fengkong` | 风控报告回复 | 角色4 |
| `/touhou` | 投后管理 | 角色5 |

## 包含的技能 (Skills)

| 技能 | 描述 |
|------|------|
| `industry-research` | 深度行业研究 + 快速赛道扫描 |
| `project-diligence` | BP评估 + 系统尽调四模块 |
| `investment-decision` | 估值分析 + IC Memo + PPT |
| `risk-control` | 风控回复五步法 + 常见问题速查 |
| `portfolio-mgmt` | 五维监控 + 三色预警 + 退出分析 |

## 目录结构

```
dacheng-pe-skill/
├── commands/              ← 斜杠命令入口
├── skills/                ← 核心工作流
│   ├── industry-research/
│   ├── project-diligence/
│   ├── investment-decision/
│   ├── risk-control/
│   └── portfolio-mgmt/
├── references/
│   ├── templates/         ← 达晨模板详细内容
│   └── style-guide.md     ← 样板写作风格
└── .claude-plugin/
    └── plugin.json        ← 插件元信息
```

## 依赖

建议配合以下 Skills 使用（已在 CLAUDE.md 中配置）：

- `private-equity@claude-for-financial-services`
- `financial-analysis@claude-for-financial-services`
- `equity-research@claude-for-financial-services`
- `investment-banking@claude-for-financial-services`
