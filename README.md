# wechat-claw

基于 `@tencent-weixin/openclaw-weixin-cli` 实现的 [OpenClaw](https://github.com/nicepkg/openclaw) 微信集成项目。

## 环境要求

- **Node.js** >= 18
- **npm** >= 9（或兼容的包管理器）
- 已安装并配置好 **OpenClaw**

## 安装步骤

### 1. 安装 OpenClaw 微信插件

运行以下命令，通过官方 CLI 工具安装微信插件：

```bash
npx -y @tencent-weixin/openclaw-weixin-cli@latest install
```

该命令会自动完成以下操作：

1. **下载 CLI 工具** — 自动获取最新版本的 `@tencent-weixin/openclaw-weixin-cli`。
2. **安装微信插件** — 将 `@tencent-weixin/openclaw-weixin` 插件（v1.0.2+）安装到 `~/.openclaw/extensions/openclaw-weixin/` 目录。
3. **重启 OpenClaw Gateway** — 自动重启 Gateway 服务以加载新安装的插件。
4. **微信扫码登录** — 在终端中显示二维码，使用微信扫码完成授权连接。

### 2. 验证安装

安装完成后，可以通过以下命令验证插件是否安装成功：

```bash
openclaw extensions list
```

在已安装的扩展列表中应能看到 `openclaw-weixin`。

### 3. 微信账号登录

如需后续登录（或重新登录）微信账号，运行：

```bash
openclaw channels login --channel openclaw-weixin
```

按照终端中的二维码提示完成授权即可。

## 项目依赖

| 包名 | 版本 | 说明 |
|------|------|------|
| `@tencent-weixin/openclaw-weixin-cli` | ^1.0.2 | 用于安装和管理 OpenClaw 微信插件的 CLI 工具 |

## 文件结构

```
wechat-claw/
├── package.json          # 项目依赖配置
├── package-lock.json     # 依赖锁定文件
├── LICENSE               # 许可证文件
└── README.md             # 本文件
```

## 常见问题

- **二维码无法显示**：请确保终端支持 Unicode 渲染，建议使用现代终端模拟器。
- **Gateway 重启失败**：可手动执行 `openclaw gateway restart` 重启 Gateway 服务。
- **登录过期**：重新运行 `openclaw channels login --channel openclaw-weixin` 刷新微信会话。

## 许可证

详见 [LICENSE](./LICENSE)。
