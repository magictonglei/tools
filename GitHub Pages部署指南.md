# GitHub Pages 部署详细指南

## 📝 前置准备

1. **注册 GitHub 账号**
   - 访问：https://github.com/
   - 点击右上角 "Sign up"
   - 填写邮箱、密码、用户名
   - 完成邮箱验证

2. **安装 Git（如已安装可跳过）**
   - Windows: https://git-scm.com/download/win
   - 下载安装包，一路"下一步"完成安装

---

## 🚀 部署步骤

### 第1步：创建新仓库

1. 登录 GitHub 后，点击右上角 `+` → `New repository`
2. 填写仓库信息：
   - **Repository name**: 随便填，例如 `log-analysis-tool`
   - **Description**（可选）: 日志重复度分析工具
   - **Public/Private**: 建议选 `Public`（免费）
   - **Add a README file**: 可以勾选
3. 点击 `Create repository`

### 第2步：上传文件到仓库

**方式A：通过网页上传（简单，适合单个文件）**

1. 在仓库页面，点击 `uploading an existing file`
2. 拖拽或点击选择你的 `log_analyzer.html` 文件
3. 在底部 "Commit changes" 输入：
   - "Add log analyzer tool"
4. 点击 `Commit changes`

**方式B：通过 Git 命令（适合团队协作）**

1. 复制仓库地址，例如：
   ```
   https://github.com/你的用户名/log-analysis-tool.git
   ```

2. 在文件所在目录打开 PowerShell 或命令提示符，执行：

   ```bash
   # 初始化 Git 仓库
   git init

   # 添加文件
   git add log_analyzer.html

   # 提交更改
   git commit -m "添加日志分析工具"

   # 关联远程仓库
   git remote add origin https://github.com/你的用户名/log-analysis-tool.git

   # 推送到 GitHub
   git push -u origin main
   ```

   如果提示输入用户名和密码：
   - 用户名：你的 GitHub 用户名
   - 密码：需要使用 Personal Access Token（见下方）

### 第3步：生成 Personal Access Token（方式B需要）

1. 点击 GitHub 右上角头像 → `Settings`
2. 左侧菜单找到最下方的 `Developer settings`
3. 点击 `Personal access tokens` → `Tokens (classic)`
4. 点击 `Generate new token` → `Generate new token (classic)`
5. 设置：
   - **Note**: log-analyzer
   - **Expiration**: 选个过期时间（如 90 days）
   - **Select scopes**: 勾选 `repo`
6. 点击 `Generate token`
7. **复制生成的 token**（只显示一次，请妥善保存）

推送时，密码处粘贴这个 token。

### 第4步：启用 GitHub Pages

1. 打开你的仓库页面
2. 点击顶部标签 `Settings`（仓库设置）
3. 左侧菜单找到 `Pages`（在 "Code and automation" 部分）
4. 在 "Build and deployment" 下：
   - **Source**: 选择 `Deploy from a branch`
   - **Branch**: 选择 `main`，目录选 `/(root)`
5. 点击 `Save`

### 第5步：等待部署完成

1. 页面会显示 "Your site is live at..."
2. 等待 1-2 分钟（GitHub 需要构建）
3. 刷新页面，状态会变为 "Deployed"

### 第6步：访问你的网站

GitHub Pages 地址格式：
```
https://你的用户名.github.io/log-analysis-tool/log_analyzer.html
```

例如：`https://zhangsan.github.io/log-analysis-tool/log_analyzer.html`

---

## 🔄 更新文件

### 通过网页更新：
1. 打开仓库页面
2. 点击 `log_analyzer.html` 文件
3. 点击右上角 `...` → `Edit this file`
4. 修改内容
5. 底部填写 commit message，点击 `Commit changes`

### 通过 Git 更新：
```bash
# 修改文件后
git add log_analyzer.html
git commit -m "更新日志分析工具"
git push
```

GitHub Pages 会自动重新部署（1-2分钟）。

---

## 💡 进阶：使用自定义域名（可选）

1. 在域名服务商处添加 CNAME 记录：
   - 主机记录：`@` 或 `www`
   - 记录值：`你的用户名.github.io`

2. 在 GitHub 仓库 `Settings` → `Pages`：
   - 在 "Custom domain" 输入你的域名
   - 点击 `Save`

3. 等待 DNS 生效（可能需要几小时）

---

## 🐛 常见问题

### Q1: 推送时提示 "Authentication failed"
**A:** GitHub 已弃用密码登录，需要使用 Personal Access Token：
- 按照上面的第3步生成 token
- 输入密码时粘贴 token

### Q2: GitHub Pages 访问 404
**A:** 检查：
- 文件名是否正确（`log_analyzer.html`）
- 等待 2-3 分钟让部署完成
- 刷新页面

### Q3: 想要 HTTPS 自动续期
**A:** GitHub Pages 自动提供 HTTPS 证书，无需额外配置。

### Q4: 如何删除仓库
**A:**
1. 仓库页面 → `Settings`
2. 滚动到最底部 "Danger Zone"
3. 点击 `Delete this repository`
4. 按提示输入仓库名确认删除

---

## 📦 完整示例

假设：
- GitHub 用户名：`zhangsan`
- 仓库名：`log-analysis-tool`

最终访问地址：
```
https://zhangsan.github.io/log-analysis-tool/log_analyzer.html
```

给团队分享这个链接即可！

---

## 🎯 快速检查清单

- [ ] 已注册 GitHub 账号
- [ ] 已创建仓库
- [ ] 已上传 `log_analyzer.html`
- [ ] 已启用 GitHub Pages
- [ ] 等待部署完成
- [ ] 测试访问网址
- [ ] 分享链接给团队

---

## 📞 获取帮助

- GitHub 官方文档：https://docs.github.com/pages
- Git 官方文档：https://git-scm.com/doc

祝部署顺利！🎉
