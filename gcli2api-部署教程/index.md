# gcli2api 云端部署及凭证获取教程

本教程将指导您如何通过 Zeabur 平台一键免费部署 gcli2api 服务，并详细说明如何获取所需的 Gemini API 凭证文件。

---

## 一、凭证获取 (本地或云端)

在部署服务之前，您需要先获取一个 `credentials_*.json` 凭证文件。

### 方式一：通过本地 Gemini CLI 获取 (推荐)

#### 1. 安装指南

**Windows 环境**
初始安装，选择一个您喜欢的文件夹，右键选择“在终端中打开”，然后执行：
```powershell
iex (iwr "https://raw.githubusercontent.com/su-kaka/gcli2api/refs/heads/master/install.ps1" -UseBasicParsing).Content
```
下一次需要启动时，双击执行 `start.bat` 文件。

**Linux / Termux 环境**
```bash
curl -o install.sh "https://raw.githubusercontent.com/su-kaka/gcli2api/refs/heads/master/install.sh" && chmod +x install.sh && ./install.sh
```
下一次需要启动时，进入 `gcli2api` 目录，执行 `bash start.sh`。

#### 2. 详细使用教程

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

4.  **获取凭证文件**
    认证成功后，系统会自动生成 JSON 凭证文件，位于 `./geminicli/creds/` 目录下，文件名为 `credentials_*.json`。**请妥善保管此文件，后续部署时需要上传。**

### 方式二：通过云端服务获取

1.  **访问认证页面**: 打开浏览器访问 `http://gcli-auth.sukaka.top:7861/`
2.  **登录认证**: 输入密码 `pwd`，按照网页指引完成 Google 账号登录。
3.  **获取 JSON 文件**: 登录成功后，选择“获取JSON”按钮，复制内容或直接下载 JSON 文件。

> **注意**：如果页面显示报错，请手动将地址栏的 `localhost` 改为 `gcli-auth.sukaka.top` 后重新访问。

---

## 二、通过Zeabur平台一键免费部署gcli2api服务

获取到 `.json` 凭证文件后，我们开始部署服务。

[**点击此处一键部署**](https://zeabur.com/button?template=https://github.com/SOYS1/gcli2api)

### 1. 注册与登录
如果您没有 Zeabur 账号，会自动跳转到注册页面。推荐使用 Google 账号进行注册。首次登录可能需要手机验证。

### 2. 确认并部署
登录后，系统会自动为您配置好项目，您只需点击“部署”按钮即可。

### 3. 设置服务参数
在弹出的窗口中，设置您的服务名称、访问密码和服务器区域。
*   **PASSWORD**: 访问 gcli2api 页面的密码，请务必记住。
*   **SERVICE DOMAIN**: 您的服务域名，可以自定义。
*   **Region**: 服务器区域 (**请勿选择香港**)。

### 4. 等待部署完成
点击部署后，等待服务状态变为绿色的“Running”。

### 5. 上传凭证并使用
部署成功后，访问您的专属域名，使用之前设置的密码登录，并上传您在第一步中获取的 `.json` 凭证文件，即可开始使用。

3.  **保存更改**：粘贴完成后，滚动到页面底部，点击绿色的 **Commit changes** 按钮。

4.  **上传图片**：最后，请将您刚才发给我的“凭证获取教程”的截图，裁剪并命名后，上传到仓库根目录的 `images` 文件夹中。

这样，所有的内容就都整合在一个文件里了，完全符合您的要求！
