# openrig 项目规则

## 本文件范围

本文件是当前仓库的项目规则主入口，维护项目阶段、技术栈、目录职责与执行边界。适用的全局规则和 Vault 工作流共存，项目规则优先；明确读取的 `CLAUDE.md` 作为入口补充，不复制维护第二套规则。

## 项目简介

参考 OpenRig 的能力，以 Vue3、FastAPI、SQLAlchemy、MySQL 和 Python daemon 自建中文研发平台。重点是轻量 Codex 执行、中央资源管理与多项目上下文隔离。

## 项目阶段

`initialization`

原始需求已形成，尚未形成经评审的阶段规格，新平台尚未实现。原 OpenRig 的代码和历史验证不等于新平台能力。

## 代码与分支

- 在当前仓库 `/Users/kanewu/Documents/TechSet/openrig` 的 `feature/chinese-multihost-baseline` 分支建设；不另建仓库，不自行切换分支或创建工作树。
- 原 OpenRig 源码、旧 CI、脚本和依赖已从当前工作区退出，通过 Git 基准 `29c2a56104e6247d289267685264b96fac46ec2a` 追溯；保留 LICENSE、Git 历史及 remotes，不操作日用 OpenRig 进程。
- 当前工作区只建设新平台。依赖清单、锁文件、构建和部署入口按实施阶段建立，不继承旧 npm workspace 或历史测试通过结论。
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
| `docs/01-需求文档/` | 原始需求与标准需求入口，单点维护 |
| `docs/02-业务架构/` | 业务流程、角色及功能到实现的映射 |
| `docs/03-技术架构/` | 新平台技术边界与原始 OpenRig 参考分析 |
| `docs/04-部署文档/` | 经验证的部署方法；当前仅初始化 |
| `docs/05-使用手册/` | 已交付产品的操作说明；当前仅初始化 |
| `docs/06-交付审计/` | 实际交付审计报告，不伪造通过结论 |
| `docs/superpowers/specs/` | 后续按 SDD 形成的阶段规格 |
| `docs/superpowers/plans/` | 规格评审后的详细实施计划 |
| `frontend/`、`backend/`、`runner/` | 新平台代码目录，当前仅保留 `.gitkeep`，不代表已实现 |

## Vault 登记

当前按 `dev-project-init` 登记到 `~/Documents/Obsidian/dev-vault/projects/openrig/`。Vault 保存开发状态和笔记，项目需求与规格以本仓库为权威，不全文复制双写。未来平台资料迁移按原始需求推进，当前登记不构成永久 Vault 依赖。

工作流与笔记约定见 `~/Documents/Obsidian/dev-vault/CLAUDE.md`；本项目上述 override 优先。
