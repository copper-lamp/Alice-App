# Alice App

> Alice Mod 智能体核心桌面客户端
>
> 版本: v1.0.0 · 通道: [standard](https://github.com/copper-lamp/Alice-App/releases)

---

## 介绍

Alice App 是 Alice Mod 系统的桌面客户端，让大语言模型（LLM）驱动 Minecraft 游戏内的假人，实现从感知、决策到执行的完整闭环。

只需在电脑上运行 Alice App，再配合游戏内的适配器模组/插件，即可让 AI 假人在 Minecraft 中自主完成各种任务。

## 功能

- **多模型支持** — 对接 OpenAI、Anthropic、Ollama 等多种 LLM 提供商
- **任务规划** — AI 智能体自主决策与任务编排，自动拆解复杂目标
- **记忆系统** — 基于 SQLite 的结构化记忆存储，让 AI 记住学习过的东西
- **QQ 机器人** — 通过 QQ 群聊远程操控游戏内假人
- **可视化界面** — 配置管理、状态监控、AI 思考过程实时展示
- **TCP 通信** — 与游戏内适配器实时通信，双向指令传递
- **自动更新** — 内置更新器，自动升级到最新版本

## 安装

### 下载

从 [Releases](https://github.com/copper-lamp/Alice-App/releases) 页面下载对应系统的最新版本：

| 系统 | 下载文件 |
|------|---------|
| Windows | `Alice-App-Setup-x.x.x.exe` |
| macOS (Intel) | `Alice-App-x.x.x.dmg` |
| macOS (Apple Silicon) | `Alice-App-x.x.x-arm64.dmg` |
| Linux | `Alice-App-x.x.x.AppImage` |

### 系统要求

- Windows 10+ / macOS 12+ / Ubuntu 20.04+
- 内存 ≥ 4GB（推荐 8GB+）
- 网络连接（用于 LLM API 调用）

### 安装步骤

1. 下载对应系统的安装包
2. Windows 用户双击 `.exe` 按引导安装；macOS 用户挂载 `.dmg` 拖入 Applications；Linux 用户给 `.AppImage` 添加执行权限后运行
3. 首次启动会进入配置向导

## 使用

### 快速开始

1. 启动 Alice App，进入配置向导
2. 配置 LLM API Key（支持 OpenAI / Anthropic / Ollama 等）
3. 确保 Minecraft 游戏中已安装对应的适配器（Alice-JE 或 Alice-BE）
4. 启动游戏，适配器会自动连接 Alice App
5. 在 Alice App 中发送指令，观察 AI 假人执行

### 版本通道

Alice App 提供多个更新通道，满足不同用户需求：

| 通道 | 版本 | 说明 |
|------|------|------|
| **standard** | 稳定版 | 经过充分测试的稳定版本，推荐所有用户使用 |
| **preview** | 预览版 | 领先 standard 一个 minor 版本，抢先体验新功能 |
| **advanced** | 高级版 | 含额外插件功能的专属版本（即将推出） |

### 配置说明

- **LLM Provider**：在设置页面填写 API Key 和模型名称
- **工作区**：管理多个 Minecraft 服务器的连接配置
- **插件**：管理已安装的工具模块和功能扩展

## 开发

### 环境要求

- Node.js ≥ 20.0 LTS
- pnpm ≥ 8.0

### 本地构建

```bash
git clone https://github.com/copper-lamp/Alice-App.git
cd Alice-App

pnpm install
pnpm dev    # 开发模式
pnpm build  # 构建
pnpm electron-builder  # 打包桌面应用
```

### 项目结构

```
src/
├── main/              # Electron 主进程
│   ├── llm/          # LLM 调度层
│   ├── tcp/          # TCP 通信
│   ├── memory/       # 记忆系统
│   ├── task/         # 任务规划
│   └── qq/           # QQ 机器人
└── renderer/          # React UI 界面
```

## 相关项目

- [Alice-JE](https://github.com/copper-lamp/Alice-JE) — Java 版 (Fabric) 游戏内适配器
- [Alice-BE](https://github.com/copper-lamp/Alice-BE) — 基岩版 (LeviLamina) 游戏内适配器

## 许可证

本项目为 Alice Mod 系统的一部分。