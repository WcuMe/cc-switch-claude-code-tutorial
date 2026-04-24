# cc switch 接入 Claude Code 完整配置教程

## 目录

1. [cc switch 简介](#cc-switch-简介)
2. [安装 cc switch](#安装-cc-switch)
3. [配置 Claude Code 接入](#配置-claude-code-接入)
4. [常见问题](#常见问题)

---

## cc switch 简介

**cc switch** 是一个跨平台桌面应用程序（支持 Windows / macOS / Linux），由 Tauri + Rust 构建，用于统一管理多种 AI 编程工具的 API 提供商配置：

- Claude Code
- OpenAI Codex
- Gemini CLI
- OpenCode
- OpenClaw

使用 cc switch，您可以：
- 通过可视化界面管理 API 配置，无需手动编辑 JSON 或环境变量
- 在不同提供商之间一键切换
- 统一管理 MCP 服务器和 Skills

---

## 安装 cc switch

### macOS

#### 方式一：Homebrew（推荐）

```bash
brew install --cask cc-switch
```

#### 方式二：直接下载

1. 访问 [ccswitch.io](https://ccswitch.io) 官网
2. 下载 macOS 版本的 `.dmg` 安装包
3. 双击打开并将应用拖入 Applications 文件夹

![macOS安装界面示意](screenshots/01-install-macos.png)

### Windows

1. 访问 [ccswitch.io](https://ccswitch.io) 官网
2. 下载 Windows 版本的 `.exe` 安装程序
3. 运行安装程序，按提示完成安装

![Windows安装界面示意](screenshots/02-install-windows.png)

### Linux (Debian / Ubuntu)

```bash
sudo dpkg -i CC-Switch-*.deb
```

或使用 AppImage：

```bash
chmod +x CC-Switch-*.AppImage
./CC-Switch-*.AppImage
```

![Linux安装界面示意](screenshots/03-install-linux.png)

---

## 配置 Claude Code 接入

### 前置要求

- 已安装 Claude Code CLI（如果未安装，请参考 [Claude Code 官方文档](https://docs.anthropic.com/claude-code)）
- 一个 API 提供商的密钥（如 OpenAI、Anthropic、OfoxAI 等）

### 步骤一：启动 cc switch

安装完成后，在应用程序列表中找到 **CC Switch** 并打开。

![启动cc switch](screenshots/04-launch-ccswitch.png)

### 步骤二：选择 Claude 工具

在左侧导航栏中，点击 **Claude** 图标切换到 Claude 配置面板。

![选择Claude工具](screenshots/05-select-claude.png)

### 步骤三：添加新的 Provider

点击右上角的 **+** 按钮，选择 **Custom** 自定义提供商。

![添加Provider](screenshots/06-add-provider.png)

### 步骤四：填写配置信息

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

### 步骤五：保存配置

点击 **Add** 或 **Save** 按钮保存配置。

![保存配置](screenshots/08-save-config.png)

### 步骤六：激活 Provider

返回提供商列表，选中刚才创建的配置，点击 **Use** 或 **Activate** 按钮激活。

![激活Provider](screenshots/09-activate-provider.png)

### 步骤七：验证连接

打开终端，运行：

```bash
claude
```

如果配置成功，您应该能看到 Claude Code 正常启动并连接到您配置的 API 提供商。

![验证连接](screenshots/10-verify-connection.png)

---

## 高级配置

### 模型配置

在 cc switch 中，您可以为每个 Provider 设置默认模型：

| 模型层级 | 推荐模型 | 用途 |
|---------|---------|------|
| Default Sonnet | `claude-sonnet-4-20250514` | 日常编码 |
| Default Opus | `claude-opus-4-20250514` | 复杂任务 |
| Default Haiku | `claude-haiku-4-20250514` | 快速响应 |

### MCP 服务器管理

cc switch 还支持管理 MCP（Model Context Protocol）服务器：

1. 切换到 **MCP** 标签页
2. 点击 **Add Server**
3. 填写服务器配置并保存

![MCP管理](screenshots/11-mcp-management.png)

### 多工具切换

cc switch 可以在不同 AI 工具之间共享配置：

| 工具 | 配置文件位置 |
|------|-------------|
| Claude Code | `~/.claude/settings.json` |
| Codex | `~/.codex/settings.json` |

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

---

## 总结

通过 cc switch，您可以轻松管理 Claude Code 的 API 配置，实现：
- ✅ 可视化配置管理
- ✅ 一键切换提供商
- ✅ 多工具配置统一
- ✅ MCP 服务器管理

希望本教程对您有所帮助！如有问题，请参考 [ccswitch 官方文档](https://ccswitch.io/docs)。

---

*文档更新时间：2026-04-24*
