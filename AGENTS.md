# openrig 项目规则

## 本文件范围

本文件是当前仓库的项目规则主入口，维护项目阶段、技术栈、目录职责与执行边界。适用的全局规则和 Vault 工作流共存，项目规则优先；明确读取的 `CLAUDE.md` 作为入口补充，不复制维护第二套规则。

## 项目简介

参考 OpenRig 的能力，以 Vue3、FastAPI、SQLAlchemy、MySQL 和 Python daemon 自建中文研发平台。重点是轻量 Codex 执行、中央资源管理与多项目上下文隔离。

## 项目阶段

`initialization`

原始需求已形成，阶段 0/A 规格仍是待评审草案，新平台尚未实现。原 OpenRig 的代码和历史验证不等于新平台能力。

## 代码与分支

- 在当前仓库 `/Users/kanewu/Documents/TechSet/openrig` 的 `feature/chinese-multihost-baseline` 分支建设；不另建仓库，不自行切换分支或创建工作树。
- 保留原 `packages/`、源码历史、LICENSE、remotes 和日用 OpenRig 进程；新平台不依赖 OpenRig 的运行时、数据库或终端控制层。
- 新平台的依赖清单、锁文件、构建和部署入口独立。根 `package.json` 及原 npm workspace 当前属于 OpenRig，不将其构建成功当成新平台通过。
- 不自动 push、打 tag 或发布；不隐式 stash/reset，不提交无关改动。

## 技术栈

- 前端：Vue3、TypeScript、Pinia、Vue Router、Vite、tdesign-vue-next、Tailwind CSS。
- 后端：Python、FastAPI、SQLAlchemy、MySQL。
- 节点：Python、asyncio，Codex app-server；本地 sqlite3 和 HTTP 轮询属于待验证方案。
- Python 使用 uv 管理的兼容解释器、独立 `.venv` 和锁文件，不修改全局 Python。
- 当前不引入 LangGraph、Celery/Redis、通用执行器插件或 OpenRig tmux 控制层。

## 常用命令

新平台尚无经验证的安装、启动、测试和部署命令；随实现补充实际可运行命令，不填写示意命令冒充完成。

## 目录职责地图

| 目录 | 职责 |
|---|---|
| `docs/00-总索引.md` | 新平台标准文档导航 |
| `docs/01-需求文档/` | 需求权威入口，引用现有原始需求 |
| `docs/02-业务架构/` | 业务流程、角色和功能到实现的映射 |
| `docs/03-技术架构/` | 技术边界和已落实设计 |
| `docs/04-部署文档/` | 经验证的部署方法；当前仅初始化 |
| `docs/05-使用手册/` | 已交付产品的操作说明；当前仅初始化 |
| `docs/06-交付审计/` | 实际交付审计报告，不伪造通过结论 |
| `docs/project-reform/` | 原始需求、OpenRig 研究、阶段拆分及已有规格草案 |
| `docs/superpowers/specs/` | 后续阶段规格；既有草案通过索引引用，不重复复制 |
| `docs/superpowers/plans/` | 规格评审后的详细实施计划 |
| `frontend/`、`backend/`、`runner/` | 规划的新平台代码目录，实施到相应阶段才创建 |
| `packages/`、原 `scripts/`、`docs/as-built/`、`docs/reference/` | OpenRig 参考源码、工具和文档 |

## 工作流 override

用户明确指定 **SDD + Superpowers**，覆盖 Vault 中计划阶段默认使用 GStack 的路由。原始需求 → 经评审的阶段规格 → 实施计划 → 逐任务实现 → 验证证据；不把初始化授权解释为规格或实施计划获批。

使用 `superpowers:brainstorming` 处理必要澄清及规格；规格评审后用 `superpowers:writing-plans`；计划评审并选定执行方式后使用对应执行技能；按适用的 TDD、审查和完成验证技能交付。延续已有决定，不重复询问已确定的路径、分支和技术栈。

阶段与下一步以 [SDD 阶段拆分](docs/project-reform/SDD阶段拆分.md) 为入口。目前尚待阶段 0/A 规格评审，不开始产品编码。

## Vault 登记

当前按 `dev-project-init` 登记到 `~/Documents/Obsidian/dev-vault/projects/openrig/`。Vault 保存开发状态和笔记，项目需求与规格以本仓库为权威，不全文复制双写。未来平台资料迁移按原始需求推进，当前登记不构成永久 Vault 依赖。

工作流与笔记约定见 `~/Documents/Obsidian/dev-vault/CLAUDE.md`；本项目上述 override 优先。
