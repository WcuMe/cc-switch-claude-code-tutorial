# cc switch 接入 Claude Code 完整配置教程

[English](README_EN.md) | 中文

---

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
- [详细配置教程](#详细配置教程)
- [截图展示](#截图展示)
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
| OpenClaw | 另一个 AI 编程工具 |

---

## 功能特性

- 可视化界面 - 无需手动编辑 JSON 或环境变量
- 一键切换 - 在不同提供商之间快速切换
- 统一管理 - 同时管理 MCP 服务器和 Skills
- 安全存储 - API 密钥安全存储
- 跨平台 - 支持 macOS / Windows / Linux

---

## 安装指南

### macOS

```bash
brew install --cask cc-switch
```

### Windows

1. 访问 [ccswitch.io](https://ccswitch.io) 官网
2. 下载 Windows 版本的 `.exe` 安装程序
3. 运行安装程序，按提示完成安装

### Linux

```bash
# Debian / Ubuntu
sudo dpkg -i CC-Switch-*.deb

# 或使用 AppImage
chmod +x CC-Switch-*.AppImage
./CC-Switch-*.AppImage
```

---

## 详细配置教程

### 步骤1：启动 cc switch

在应用程序列表中找到 **CC Switch** 并打开。

### 步骤2：选择 Claude 工具

在左侧导航栏中，点击 **Claude** 图标切换到 Claude 配置面板。

### 步骤3：切换到 Custom 标签

点击 **Custom** 标签，准备添加自定义提供商。

### 步骤4：添加 Provider

点击右上角的 **+** 按钮添加新的提供商。

### 步骤5：填写配置信息

根据您的 API 提供商填写以下字段：

| 字段 | 示例值 | 说明 |
|------|--------|------|
| Provider Name | `Tutorial Provider` | 供您识别的自定义名称 |
| Website URL | `https://api.example.com` | API 提供商网站 |
| API Key | `sk-xxxxxxxxxxxxx` | 您的 API 密钥 |
| Request URL | `https://api.example.com` | API 请求地址 |
| API Format | `Anthropic Messages (Native)` | 保持默认 |
| Auth Field | `ANTHROPIC_AUTH_TOKEN` | 保持默认 |

> 注意：Request URL 末尾不要加斜杠 `/`，cc switch 对尾斜杠敏感。

### 步骤6：保存配置

点击 **Save** 按钮保存配置。

### 步骤7：激活 Provider

返回提供商列表，选中刚才创建的配置，点击 **Use** 按钮激活。

---

## 截图展示

### 1. 主界面


cc switch 主界面，左侧显示支持的 AI 编程工具：Claude、Codex、Gemini、OpenCode、OpenClaw。

### 2. Custom 标签


切换到 Custom 标签，可以添加自定义 API 提供商。

### 3. 添加 Provider 对话框


点击 + 按钮后打开的添加 Provider 对话框。

### 4. 填写 Provider 名称


在 Provider Name 字段中输入名称。

### 5. 填写 Website URL


填写 API 提供商的网站地址。

### 6. 填写 API Key


输入您的 API 密钥。

### 7. 填写 Request URL


填写 API 请求地址。

### 8. 完整配置示例


完整的配置示例，包含 Provider Info 和 API Configuration。

### 9. 保存后界面


保存配置后，对话框关闭。

### 10. Provider 已添加到列表


tutorial-provider 已成功添加到 Custom Provider 列表中。

### 11. 激活 Provider


点击 Use 按钮激活 Provider，界面显示 "tutorial-provider is now active"。

### 12. Codex 工具界面


cc switch 同时支持配置 OpenAI Codex 等其他 AI 编程工具。

### 13. 设置界面


Settings 界面可以配置隐藏菜单栏图标、开机自启、自动更新等功能。

---

## 常见问题

### Q1: 激活后提示成功但 Claude Code 连不上？

解决方案：
1. 确认 API Key 正确且有效
2. 检查 Request URL 是否有尾斜杠，去掉它
3. 确认 API Key 有对应的访问权限

### Q2: 能否同时配置多个提供商？

可以！您可以添加多个 Provider，需要时在它们之间切换即可。

### Q3: cc switch 会修改我的原始配置文件吗？

不会。cc switch 会自动写入 `~/.claude/settings.json`，不会影响您的其他配置。

### Q4: 如何重置配置？

在 cc switch 中，选中要删除的 Provider，点击 Remove 即可清除。

---

## 资源链接

- [cc switch 官网](https://ccswitch.io)
- [cc switch GitHub](https://github.com/ccswitch/ccswitch)
- [Claude Code 官方文档](https://docs.anthropic.com/claude-code)

---

## 许可证

本教程基于 MIT 许可证开源。

---

<p align="center">
  Made for AI Coding Enthusiasts
</p>
