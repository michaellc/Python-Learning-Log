# 🚀 GitHub 代码同步全指南 (2026 版)

## 一、 核心同步方式对比


| 方式 | 协议 | 认证方式 | 国内使用建议 |
| :--- | :--- | :---: | :--- |
| **HTTPS** | `https://` | 浏览器授权 | **最推荐**。配合 SOCKS5 代理极速且稳定。 |
| **SSH** | `git@github.com` | SSH Key 秘钥对 | 较安全，但在 Windows 下配置复杂。 |

---

## 二、 基础配置 (一次性操作)

在开始同步前，必须确保身份和通道已打通：

### 1. 身份签名
```bash
git config --global user.name "你的用户名"
git config --global user.email "你的邮箱"
```

### 2. 开启加速通道 (针对中国大陆网络)
```bash
git config --global http.proxy socks5://1.2.3.4:1080 #router ip:port
git config --global https.proxy socks5://1.2.3.4:1080 # router ip:port
```

---

## 三、 日常同步流程 (最常用)

### 1. 命令行流 (Git Bash) — “三部曲”
1. **标记** — `git add .`
2. **打包** — `git commit -m "feat: 备注内容"`
3. **发射** — `git push`

### 2. VS Code 图形流 — “效率流”
* **保存**：`Ctrl + S`
* **暂存/提交**：点击“小树枝”图标，输入消息并点击“提交”。
* **推送**：点击“同步更改”。
