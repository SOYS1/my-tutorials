# gcli2api 云端部署自用教程

本教程将帮助您使用 Zeabur 平台一键免费部署 gcli2api 服务。服务需要几分钟，您可以带上已获取的 Gemini API 凭证文件（.json）供应自己使用。

> **注意**：获取凭证文件请参考[本地凭证获取教程](https://github.com/google/generative-ai-python/blob/main/docs/client_library_quickstart.ipynb)或[云端凭证获取教程](https://github.com/google/generative-ai-python/blob/main/docs/client_library_quickstart_colab.ipynb)。

## 通过Zeabur平台一键免费部署gcli2api服务

Zeabur 每日有5美刀免费额度，部署 gcli2api 完全够用，可以放心使用。

[**点击此处一键部署**](https://zeabur.com/button?template=https://github.com/SOYS1/gcli2api)

### 1. 切换为中文界面

如果您不熟悉英文，可以先将 Zeabur 的网站语言切换为中文，方便后续操作。

![切换中文](https://raw.githubusercontent.com/SOYS1/my-tutorials/main/images/gcli2api-部署教程-1.png)

### 2. 进行注册

点击一键部署后，如果您没有 Zeabur 账号，会自动跳转到注册页面。推荐使用 Google 账号进行注册，方便快捷。

![注册Zeabur](https://raw.githubusercontent.com/SOYS1/my-tutorials/main/images/gcli2api-部署教程-2.png)

### 3. 手机验证

首次注册需要进行手机号验证以激活账号。

![手机验证](https://raw.githubusercontent.com/SOYS1/my-tutorials/main/images/gcli2api-部署教程-3.png)

### 4. 确认并部署

登录后，系统会自动为您配置好项目，您只需点击“部署”按钮即可。

![确认部署](https://raw.githubusercontent.com/SOYS1/my-tutorials/main/images/gcli2api-部署教程-4.png)

### 5. 设置服务参数

在弹出的窗口中，您可以设置服务的名称、访问密码以及服务器区域。设置完成后，点击“部署”。

*   **PASSWORD**: 这是您在访问 gcli2api 页面时需要填写的密码，请务必记住。
*   **SERVICE DOMAIN**: 这是您的服务域名，可以自定义。
*   **Region**: 服务区域，选择离您近的或者符合政策的区域即可。

> **警告**: 请勿选择香港服务器，因为香港地区无法正常使用 Google Gemini 服务。

![设置参数](https://raw.githubusercontent.com/SOYS1/my-tutorials/main/images/gcli2api-部署教程-5.png)

### 6. 等待部署完成

点击部署后，系统将开始自动化构建和部署。您可以点击“Go to Project”查看项目主页，等待服务状态变为绿色的“Running”。

![部署中](https://raw.githubusercontent.com/SOYS1/my-tutorials/main/images/gcli2api-部署教程-6.png)

部署成功后，即可访问您的专属域名，使用之前设置的密码登录，并上传您的 .json 凭证文件开始使用。
