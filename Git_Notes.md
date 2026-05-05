🚀 GitHub 代码同步全指南 (2026 版)
一、 核心同步方式对比
方式	协议	认证方式	国内使用建议
HTTPS (昨天)	https://	浏览器授权登录	最推荐。配合 SOCKS5 代理极速且稳定。
SSH	git@github.com	SSH Key 秘钥对	较安全，但在 Windows + 代理环境下配置复杂，易报错。
二、 基础配置 (一次性操作)
在开始同步前，必须确保身份和通道已打通：
身份签名：
```bash
git config --global user.name "你的用户名"
git config --global user.email "你的邮箱"

开启加速通道 (针对中国大陆网络)：
```bash
# 让 Git 走路由器的 SOCKS5 代理
git config --global http.proxy socks5://1.2.3.4:1080 #router_ip:port
git config --global https.proxy socks5://1.2.3.4:1080 #router_ip:port

三、 日常同步流程 (最常用)
1. 命令行流 (Git Bash) — “三部曲”
这是所有程序员的必修课，也是最稳的操作：
Step 1: 标记 — git add . (把所有改动放进暂存区)
Step 2: 打包 — git commit -m "feat: [中英双语信息]" (记录改动原因)
Step 3: 发射 — git push (同步到云端)
2. VS Code 图形流 — “效率流”
在 VS Code 中，无需记忆命令，操作更直观：
保存：Ctrl + S (Git 只能提交已保存的文件)。
暂存：点击左侧“小树枝”图标，点文件名旁的 +。
提交：在消息框输入备注，按 Ctrl + Enter。
同步：点击蓝色的 “同步更改” 按钮或左下角的 🔄。
四、 常见报错与排查 (Troubleshooting)
Error 10061 / Connection Reset: 代理 IP 或端口写错了，或者路由器加速插件没开，加速器开启全局模式就ok了。
无法点击“提交”按钮: 检查文件是否没保存 (文件名旁有白点)，或者消息框是否为空。
冲突 (Conflict): 云端和本地改了同一行。此时先 Pull，在 VS Code 提示中选择保留哪份代码，再重新 Push。
