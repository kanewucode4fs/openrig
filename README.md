# openrig · 中文研发平台

参考 OpenRig 的能力，使用 Vue3、FastAPI、SQLAlchemy、MySQL 和 Python daemon 自建研发平台。通过中文网页管理项目、标准团队、SOP、执行节点、人工确认与交付审查。

**当前阶段：initialization。** 已形成原始需求和阶段规格草案，尚未实现产品功能；代码目录仅为占位，没有可运行的安装或启动命令。

## 文档入口

- [文档总索引](docs/00-总索引.md)
- [原始需求](docs/01-需求文档/原始需求文档.md)
- [SDD 阶段拆分](docs/02-业务架构/SDD阶段拆分.md)
- [阶段 0/A 执行基础规格（待评审）](docs/03-技术架构/阶段0A执行基础规格.md)
- [OpenRig 参考分析](docs/03-技术架构/OpenRig代码架构与设计分析.md)

## 目录

```text
openrig/
├── AGENTS.md
├── CLAUDE.md
├── LICENSE
├── README.md
├── docs/
│   ├── 00-总索引.md
│   ├── 01-需求文档/
│   ├── 02-业务架构/
│   ├── 03-技术架构/
│   ├── 04-部署文档/
│   ├── 05-使用手册/
│   ├── 06-交付审计/
│   └── superpowers/
│       ├── specs/
│       └── plans/
├── frontend/
├── backend/
└── runner/
```

`frontend/` 用于 Vue3 WebUI，`backend/` 用于 FastAPI 中央服务，`runner/` 用于 Python 执行节点。依赖和运行入口随实施阶段建立。

## 开发方式

使用 SDD + Superpowers：原始需求 → 经评审的规格 → 实施计划 → 实现 → 验证证据。当前在 `feature/chinese-multihost-baseline` 分支建设；具体约束见 [AGENTS.md](AGENTS.md)。

## 参考来源

原 [OpenRig](https://github.com/mvschwarz/openrig) 工程的源码和配套文件已从当前工作区退出，可通过固定提交 `29c2a56104e6247d289267685264b96fac46ec2a` 在 Git 历史中追溯。原 [LICENSE](LICENSE) 保留，历史版权和来源不因目录整理而移除。新平台不依赖原 Node.js daemon、CLI/TUI 或 tmux 执行层。
