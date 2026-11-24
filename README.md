# dsh-video-mode

给 DeepSeek Harness 加一个**视频生成模式**（Agent 预设）。

- 插件包类型：纯配置 bundle（只插入一条 `@deepseek-ai/dsh-agent-preset` 声明）。
- 新增模式 id：`video`，显示名：**视频生成模式**，归在「自定义」分组。
- 依赖：无代码、无额外依赖；OpenMotion 的 `openmotion_*` 工具与技能由 `dsh-plugin-openmotion-local` 在 Host 层提供。

## 安装

在 Harness 里把本目录作为本地插件安装（Plugins → 添加插件 → 选择本目录），
或用 `plugin_manager` 的 `install_bundle`，`target` 填本目录绝对路径：

```
<本仓库克隆目录>/dsh-video-mode
```

安装后**新建任务**，在模式菜单选「视频生成模式」。已存在的会话仍保留原先的模式。

## 改法

- 改人格/流程：编辑 `cordis.patch.yml` 里 `persona.config.prefix`，重新安装或等 profile 补丁热重载。
- 改工具集：增删 `config.plugins` 里的行（工具包名见 DSH 的 `references/packages.md`）。
