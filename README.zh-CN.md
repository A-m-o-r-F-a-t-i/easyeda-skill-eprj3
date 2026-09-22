# EasyEDA Pro eprj3 工程 Skill

[English](README.md) | 简体中文

该 Skill 教 AI 编程代理创建、修改、校验并打开嘉立创 EDA 专业版的目录式 `.eprj3` 工程。它包含项目初始化、符号与封装生成、原理图和 PCB 记录写入、工程清理、结构校验以及打开本地客户端所需的 Node.js 脚本。

## 适用范围

- 从零创建目录式 `.eprj3` 工程。
- 生成或导入符号、封装和库数据。
- 写入原理图导线、网络标签、文本及 PCB 图元。
- 对工程目录和记录结构执行机器校验。
- 在嘉立创 EDA 专业版离线客户端中打开结果。

该仓库负责**离线工程格式与生成流程**。PCB 的器件布局、层叠、电流、回流路径、布线、铺铜、丝印和工程验收，应同时使用 `easyeda-pcb-layout-routing`。正在打开的真实 PCB 文档操作由 `easyeda-pcb-mcp` 执行。

## 快速开始

需要 Node.js。安装依赖并运行冒烟测试：

```powershell
npm ci
npm test
```

初始化工程并校验：

```powershell
node scripts/init.js <工程目录>
node scripts/validate.js <工程目录>
```

所有可用命令以 `package.json` 和 `SKILL.md` 为准。AI 代理应先读取 `SKILL.md`，再按任务选择 `scripts/` 中的工具，不应绕过校验直接拼接未知记录。

## 仓库结构

```text
SKILL.md       AI 代理入口与工作流
scripts/       工程创建、编辑、校验和打开工具
docs/          格式与使用说明
templates/     工程模板
test/          冒烟测试
install/       不同代理的接入说明
```

## 来源与许可证

本仓库基于 EasyEDA 的 MIT 许可项目进行 AgentDock 集成，固定来源提交为 `bffb417434c299d61e0ae4ed560991dc986a9850`。原许可证保存在 [LICENSE](LICENSE) 中；上游归属和第三方权利不因本仓库为私有仓库而改变。

