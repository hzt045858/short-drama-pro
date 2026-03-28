---
name: short-drama-pro
description: "短剧项目创作技能。适合做短剧项目初始化、创作方案生成、角色档案、剧集目录、自检和导出。用于需要一个本地可运行的短剧工作流时。当前仓库为社区版修复安装，已验证 start/plan/characters/catalog/check/export，episode 仍需继续补强。"
---

# short-drama-pro

本技能用于在本地创建和推进短剧项目。

## 当前实际状态

已实测可用：
- `./short-drama-pro start`
- `./short-drama-pro plan`
- `./short-drama-pro characters`
- `./short-drama-pro catalog`
- `./short-drama-pro check`
- `./short-drama-pro export`

已补测通过：
- `./short-drama-pro episode 1`

说明：
- 该仓库原始内容不完整，且主入口与部分脚本有语法/参数问题。
- 当前版本已经过本地修复，适合继续迭代使用。
- 不要再假设仓库里存在 `references/`、`templates/`、`_meta.json` 等原文档提到但实际缺失的目录。

## 用法

在技能目录执行：

```bash
./short-drama-pro start
./short-drama-pro plan
./short-drama-pro characters
./short-drama-pro catalog
./short-drama-pro check all
./short-drama-pro export --format folder
```

如果存在多个项目目录，主入口会自动选择最新的：

```bash
short-drama-project-YYYYmmddHHMMSS/
```

也可以手动指定：

```bash
./short-drama-pro plan --project-dir /path/to/project
./short-drama-pro characters --project-dir /path/to/project
./short-drama-pro catalog --project-dir /path/to/project
./short-drama-pro check all --project-dir /path/to/project
./short-drama-pro export --project-dir /path/to/project --format folder
```

## 当前目录结构

```text
short-drama-pro/
├── SKILL.md
├── short-drama-pro
├── short-drama-pro-continue.sh
└── scripts/
    ├── start.py
    ├── start_noninteractive.py
    ├── plan.py
    ├── characters.py
    ├── catalog.py
    ├── episode.py
    ├── check.py
    └── export.py
```

## 建议工作流

1. `start`：创建项目与 `config.json`
2. `plan`：生成创作方案
3. `characters`：生成角色档案
4. `catalog`：生成剧集目录
5. `check`：做一次总体自检
6. `export`：导出整包

## 已知问题

- `episode.py` 仍需继续补测和修整；当前调用没有稳定产出。
- 文档里部分“商业分析 / analyze / 多模板 / 出海参考文档”等描述，当前仓库并没有完整实现，不要按宣传文案当作已完成能力。

## 维护建议

后续如果继续修：
- 优先修 `episode.py`
- 再补缺失的参考资料或模板
- 最后再扩展 `analyze` 一类未落地命令
