# 安装指南

## Termux 环境

每次开启 Termux 运行这个脚本即可，进程会自动后台运行：

```bash
curl -o termux-install.sh "https://raw.githubusercontent.com/su-kaka/gcli2api/refs/heads/master/termux-install.sh" && chmod +x termux-install.sh && ./termux-install.sh
```

## Windows 环境

初始安装，选择一个您喜欢的文件夹，右键选择“在终端中打开”，然后执行：

```powershell
iex (iwr "https://raw.githubusercontent.com/su-kaka/gcli2api/refs/heads/master/install.ps1" -UseBasicParsing).Content
```

下一次需要启动时，双击执行 `start.bat` 文件。

## Linux 环境

初始安装：

```bash
curl -o install.sh "https://raw.githubusercontent.com/su-kaka/gcli2api/refs/heads/master/install.sh" && chmod +x install.sh && ./install.sh
```

下一次需要启动：

```bash
cd gcli2api
bash start.sh
```

# 配置说明

1.  **访问认证页面**
    在浏览器中打开：`http://127.0.0.1:7861/auth`

2.  **完成 OAuth 认证**
    使用默认密码 `pwd`，按照页面指引完成 Google OAuth 认证流程。

# 详细使用教程

1.  **安装 Gemini CLI**
    使用 npm 全局安装官方 Gemini CLI 工具：
    ```bash
    npx https://github.com/google-gemini/gemini-cli
    ```

2.  **选择认证选项**
    运行命令后选择选项 `1` (用户认证)：
    ```
    ? 选择认证方式 › - 使用箭头键选择
    ❯   用户认证 (User Authentication)
        服务账号认证 (Service Account Authentication)
    ```

3.  **完成浏览器认证**
    按回车确认后，系统会自动打开浏览器完成 Google 账户认证。
    *   在浏览器中选择要使用的 Google 账户
    *   授予必要的 API 访问权限
    *   认证完成后会自动返回命令行

4.  **获取凭证文件**
    认证成功后，系统会自动生成 JSON 凭证文件：
    *   **文件位置**: `./geminicli/creds/` 目录
    *   **文件格式**: `credentials_*.json`
    *   包含完整的 API 访问凭证信息

# 故障排除 - 400 错误解决方案

**问题描述**: 在使用过程中可能会遇到 400 Bad Request 错误，这通常是由于认证配置问题导致的。

**解决方案**:

1.  **重新运行认证流程**: 确保按照上述详细教程的步骤重新进行认证。
2.  **检查网络连接**: 确保网络连接稳定，能够正常访问 Google 服务。
3.  **清除缓存文件**: 删除旧的凭证文件后重新认证：
    ```bash
    rm -rf ./geminicli/creds/*.json
    ```
4.  **检查浏览器设置**: 确保浏览器允许弹出窗口，没有拦截认证页面的打开。

# 注意事项

*   当前 OAuth 验证流程仅支持**本地主机 (localhost)** 访问，即必须通过 `http://127.0.0.1:7861/auth` 完成认证。
*   如需在云服务器或其他远程环境部署，请先在本地运行服务并完成 OAuth 验证，获得生成的 `json` 凭证文件后，再在 `auth` 面板将该文件上传。
*   **GitHub 项目地址**: [https://github.com/su-kaka/gcli2api](https://github.com/su-kaka/gcli2api)，可查看最新更新和问题反馈。

# 云端凭证获取教程

1.  **访问认证页面**: 打开浏览器访问 `http://gcli-auth.sukaka.top:7861/`
2.  **登录认证**: 输入密码 `pwd`，按照网页指引完成 Google 账号登录。
3.  **获取 JSON 文件**: 登录成功后，选择“获取JSON”按钮，系统会自动获取 project id 并开启服务，复制内容或直接下载 JSON 文件即可。

> **注意**：如果页面显示报错，请手动将地址栏的 `localhost` 改为 `gcli-auth.sukaka.top` 后重新访问。
```

4.  **保存文件**：粘贴完成后，滚动到页面底部，点击绿色的 **Commit new file** 按钮。

**第二步：更新主目录**

1.  **点击下面的链接**，进入主目录 `README.md` 的编辑页面：
    [https://github.com/SOYS1/my-tutorials/edit/main/README.md](https://github.com/SOYS1/my-tutorials/edit/main/README.md)

2.  **清空并粘贴**：同样，删掉所有旧内容，然后把下面代码块里的新目录 **完整地** 复制粘贴进去。

```markdown
# 我的个人教学仓库

这里存放着我整理的各种技术和工具的教学文档。

## 教学目录

*   [Gemini 上游配置教学 (Cloudflare AI Gateway)](./gemini-cloudflare-tutorial/index.md)
*   [gcli2api 部署教程](./gcli2api-部署教程/index.md)
*   [Gemini CLI 凭证获取教程](./Gemini-CLI-凭证获取教程/index.md)
```

3.  **保存更改**：粘贴完成后，滚动到底部，点击绿色的 **Commit changes** 按钮。

**最后一步：上传图片**

请将您刚才发给我的“凭证获取教程”的截图，裁剪并命名后，上传到根目录的 `images` 文件夹中。

做完这些，您的整个教程仓库就都整理好了！
