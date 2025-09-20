# gcli2api 云端部署尝鲜自用教程

> 本教程由 [SOYS1](https://github.com/SOYS1) 编写，项目地址：[su-k-a/gcli2api](https://github.com/su-k-a/gcli2api)

## 1. 通过 Zeabur 平台一键免费部署 gcli2api

### ① 注册账号
访问 [zeabur.com](https://zeabur.com) 并使用 GitHub 账号注册。

![Zeabur 登录页面](../images/gcli2api/deploy-1.png)

### ② 授权
登录后，授权 Zeabur 访问您的 GitHub 仓库。

![Zeabur 授权页面](../images/gcli2api/deploy-2.png)

### ③ 部署服务
点击下方按钮一键部署：
[![Deploy on Zeabur](https://zeabur.com/button.svg)](https://zeabur.com/templates/gcli2api)

### ④ 填写服务名和域名
- **服务名**: 随意填写，例如 `gcli2api`
- **SERVICE_DOMAIN**: 填写您想要的域名，例如 `gcli2api.zeabur.app`

![Zeabur 服务配置](../images/gcli2api/deploy-3.png)

### ⑤ 等待部署
部署过程可能需要几分钟，请耐心等待。

![Zeabur 部署中](../images/gcli2api/deploy-4.png)

### ⑥ 获取凭证文件
> **重要**: 获取凭证文件请参考 [本地凭证获取教程](./本地凭证获取教程.md) 或 [云端凭证获取教程](./云端凭证获取教程.md)。

### ⑦ 负载均衡（防止休眠）
Zeabur 的免费服务有休眠策略，您可以使用其他服务（如 aapanel/Cloudflare Worker）进行定时访问以保持服务活跃。

### ⑧ 添加环境变量
- 在 Zeabur 的服务设置中，找到“变量”选项卡。
- 添加一个新的变量，键为 `CREDENTIALS`。
- 将第 ⑥ 步获取到的凭证文件（JSON 格式）的**全部内容**粘贴到值中。

![Zeabur 添加环境变量](../images/gcli2api/deploy-5.png)

### ⑨ 完成部署
保存变量后，服务会自动重新部署。部署完成后，您就可以通过您设置的域名访问 gcli2api 服务了。

### ⑩ 服务位置
您可以根据需要选择不同的服务区域，以获得更好的访问速度。

![Zeabur 服务位置](../images/gcli2api/deploy-6.png)
