# cc switch 接入 Claude Code 完整配置教程

[English](README_EN.md) | 中文

---

<p align="center">
  <img src="screenshots/logo.png" alt="cc switch Logo" width="200"/>
</p>

<p align="center">
  <strong>跨平台 AI 编程工具配置管理器</strong>
</p>

<p align="center">
  <a href="https://ccswitch.io">官网</a> •
  <a href="https://github.com/ccswitch/ccswitch">GitHub</a> •
  <a href="https://docs.anthropic.com/claude-code">Claude Code 文档</a>
</p>

---

## 目录

- [简介](#简介)
- [功能特性](#功能特性)
- [安装指南](#安装指南)
  - [macOS](#macos)
  - [Windows](#windows)
  - [Linux](#linux)
- [快速开始](#快速开始)
- [详细配置教程](#详细配置教程)
  - [步骤1：启动 cc switch](#步骤1启动-cc-switch)
  - [步骤2：选择 Claude 工具](#步骤2选择-claude-工具)
  - [步骤3：添加 Provider](#步骤3添加-provider)
  - [步骤4：填写配置信息](#步骤4填写配置信息)
  - [步骤5：保存配置](#步骤5保存配置)
  - [步骤6：激活并验证](#步骤6激活并验证)
- [截图指引](#截图指引)
- [常见问题](#常见问题)
- [许可证](#许可证)

---

## 简介

**cc switch** 是一个由 Tauri + Rust 构建的跨平台桌面应用程序，用于统一管理多种 AI 编程工具的 API 配置。

### 支持的工具

| 工具 | 说明 |
|------|------|
| Claude Code | Anthropic 官方 AI 编程助手 |
| OpenAI Codex | OpenAI 编程助手 |
| Gemini CLI | Google Gemini 命令行工具 |
| OpenCode | 开源代码助手 |
| OpenClaw | another AI 编程工具 |

---

## 功能特性

- 🎨 **可视化界面** - 无需手动编辑 JSON 或环境变量
- 🔄 **一键切换** - 在不同提供商之间快速切换
- 📦 **统一管理** - 同时管理 MCP 服务器和 Skills
- 🔐 **安全存储** - API 密钥安全存储
- 🌐 **跨平台** - 支持 macOS / Windows / Linux

---

## 安装指南

### macOS

#### 方式一：Homebrew（推荐）

```bash
brew install --cask cc-switch
```

#### 方式二：直接下载

1. 访问 [ccswitch.io](https://ccswitch.io) 官网
2. 下载 macOS 版本的 `.dmg` 安装包
3. 双击打开并将应用拖入 Applications 文件夹

![macOS 安装](screenshots/01-install-macos.png)

### Windows

1. 访问 [ccswitch.io](https://ccswitch.io) 官网
2. 下载 Windows 版本的 `.exe` 安装程序
3. 运行安装程序，按提示完成安装

![Windows 安装](screenshots/02-install-windows.png)

### Linux

**Debian / Ubuntu:**

```bash
sudo dpkg -i CC-Switch-*.deb
```

**AppImage:**

```bash
chmod +x CC-Switch-*.AppImage
./CC-Switch-*.AppImage
```

![Linux 安装](screenshots/03-install-linux.png)

---

## 快速开始

```
1. 安装 cc switch
2. 启动应用
3. 选择 Claude 工具
4. 添加 Provider 并配置
5. 激活并使用
```

---

## 详细配置教程

### 步骤1：启动 cc switch

在应用程序列表中找到 **CC Switch** 并打开。

![启动 cc switch](screenshots/04-launch-ccswitch.png)

### 步骤2：选择 Claude 工具

在左侧导航栏中，点击 **Claude** 图标切换到 Claude 配置面板。

![选择 Claude 工具](screenshots/05-select-claude.png)

### 步骤3：添加 Provider

点击右上角的 **+** 按钮，选择 **Custom** 自定义提供商。

![添加 Provider](screenshots/06-add-provider.png)

### 步骤4：填写配置信息

根据您的 API 提供商填写以下字段：

| 字段 | 示例值 | 说明 |
|------|--------|------|
| Provider Name | `my-claude-config` | 供您识别的自定义名称 |
| Website URL | `https://api.example.com` | API 提供商网站 |
| API Key | `sk-xxxxxxxxxxxxx` | 您的 API 密钥 |
| Request URL | `https://api.example.com/v1` | API 请求地址 |
| API Format | `Anthropic Messages (Native)` | 保持默认 |
| Auth Field | `ANTHROPIC_AUTH_TOKEN` | 保持默认 |

> ⚠️ **注意**：Request URL 末尾不要加斜杠 `/`，cc switch 对尾斜杠敏感。

![填写配置信息](screenshots/07-config-fields.png)

### 步骤5：保存配置

点击 **Add** 或 **Save** 按钮保存配置。

![保存配置](screenshots/08-save-config.png)

### 步骤6：激活并验证

返回提供商列表，选中刚才创建的配置，点击 **Use** 或 **Activate** 按钮激活。

![激活 Provider](screenshots/09-activate-provider.png)

打开终端验证连接：

```bash
claude
```

![验证连接](screenshots/10-verify-connection.png)

---

## 截图指引

本教程所需截图应放置在 `screenshots/` 目录下：

```
screenshots/
├── logo.png                 # cc switch Logo
├── 01-install-macos.png     # macOS 安装界面
├── 02-install-windows.png   # Windows 安装界面
├── 03-install-linux.png     # Linux 安装界面
├── 04-launch-ccswitch.png   # 启动 cc switch
├── 05-select-claude.png     # 选择 Claude 工具
├── 06-add-provider.png      # 添加 Provider
├── 07-config-fields.png     # 配置信息填写
├── 08-save-config.png       # 保存配置
├── 09-activate-provider.png # 激活 Provider
├── 10-verify-connection.png # 验证连接
├── 11-mcp-management.png     # MCP 管理界面
└── 12-multi-tool.png        # 多工具切换
```

### 推荐截图尺寸

| 截图类型 | 推荐尺寸 |
|---------|---------|
| 安装界面 | 1280 x 800 |
| 配置界面 | 1400 x 900 |
| 验证截图 | 800 x 400 |

---

## 常见问题

### Q1: 激活后提示 "Switched successfully" 但 Claude Code 连不上？

**解决方案**：
1. 确认 API Key 正确且有效
2. 检查 Request URL 是否有尾斜杠，去掉它
3. 确认 API Key 有对应的访问权限

### Q2: 能否同时配置多个提供商？

**可以**！您可以添加多个 Provider，需要时在它们之间切换即可。

### Q3: cc switch 会修改我的原始配置文件吗？

**不会**。cc switch 会自动写入 `~/.claude/settings.json`，不会影响您的其他配置。

### Q4: 如何重置配置？

在 cc switch 中，选中要删除的 Provider，点击 **Delete** 即可清除。

### Q5: 支持哪些 API 提供商？

常见支持提供商包括：
- Anthropic (官方)
- OfoxAI
- QCode.cc
- APIBox
- 以及任何兼容 Anthropic API 格式的提供商

---

## 高级配置

### 模型配置示例

| 模型层级 | 推荐模型 | 用途 |
|---------|---------|------|
| Default Sonnet | `claude-sonnet-4-20250514` | 日常编码 |
| Default Opus | `claude-opus-4-20250514` | 复杂任务 |
| Default Haiku | `claude-haiku-4-20250514` | 快速响应 |

### MCP 服务器管理

1. 切换到 **MCP** 标签页
2. 点击 **Add Server**
3. 填写服务器配置并保存

![MCP 管理](screenshots/11-mcp-management.png)

---

## 资源链接

- [cc switch 官网](https://ccswitch.io)
- [cc switch GitHub](https://github.com/ccswitch/ccswitch)
- [Claude Code 官方文档](https://docs.anthropic.com/claude-code)
- [Anthropic API 文档](https://docs.anthropic.com/claude-code/api)

---

## 许可证

本教程基于 MIT 许可证开源。

---

<p align="center">
  Made with ❤️ for AI Coding Enthusiasts
</p>
