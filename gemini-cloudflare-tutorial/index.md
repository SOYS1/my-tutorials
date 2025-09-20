# Gemini 上游配置教学 (Cloudflare AI Gateway)

本教学将指导您如何通过 Cloudflare AI Gateway 配置 Gemini 上游，以便在您的应用程序中使用。

## 步骤一：访问并创建 AI Gateway

1.  登录到您的 Cloudflare 账户。
2.  在左侧导航栏中，找到并点击 **AI**。
3.  在 AI 菜单下，选择 **AI Gateway**。

    ![步骤一：导航到 AI Gateway](images/image1.png)

4.  点击 **创建网关**。
5.  在 **Gateway 名称** 字段中，输入一个您自定义的名称（例如：`gpt-load`）。
6.  根据您的需求配置其他设置，例如“收集日志”。对于初次设置，可以暂时保持默认值。
7.  点击 **创建** 按钮。

    ![步骤二：创建新网关](images/image2.png)

## 步骤二：获取 API 终结点

1.  创建网关后，系统会弹出一个窗口，其中包含您的 API 终结点 URL。
2.  这个 URL 是您连接到 AI Gateway 的入口。请复制此 URL，稍后会用到。
3.  平台选择 `Google AI Studio` 可以看到相应的 `curl` 测试示例。

    ![步骤三：获取 API 终结点](images/image3.png)

## 步骤三：在您的应用中配置上游

1.  进入您需要配置上游的应用或平台的管理后台。
2.  创建一个新的分组或渠道，用于对接 Gemini。
3.  填写以下信息：
    *   **分组名称**: `gemini`
    *   **显示名称**: `Google Gemini`
    *   **渠道类型**: `gemini`
    *   **测试模型**: `gemini-2.0-flash-lite` (或其他您需要的模型)
    *   **上游地址**: 粘贴您在 **步骤二** 中复制的 Cloudflare AI Gateway API 终结点 URL。
4.  保存配置。

    ![步骤四：配置上游地址](images/image4.png)

完成以上步骤后，您的应用程序发往此分组的请求将通过 Cloudflare AI Gateway 路由到 Google Gemini。您可以在 Cloudflare 的 AI Gateway 仪表盘中查看日志、分析和缓存等信息。

## 操作注意事项

*   **API 密钥安全**：在配置过程中，您可能会接触到 `GOOGLE_AI_STUDIO_TOKEN` 或其他平台的 API 密钥。请务必妥善保管您的密钥，不要将其泄露或硬编码到客户端代码中。
*   **Cloudflare 定价**：请注意 Cloudflare AI Gateway 的定价策略。虽然它提供了免费额度，但超出部分会产生费用。请定期检查您的用量。
*   **日志和隐私**：AI Gateway 默认会收集请求和响应的日志。如果您处理的是敏感数据，请根据您的隐私政策调整日志记录设置。
*   **上游地址准确性**：请确保您从 Cloudflare 复制并粘贴到应用中的上游地址是完全正确的，包括协议头（`https://`）和所有路径。
*   **模型支持**：不同的上游渠道可能支持不同的模型。请确保您在应用中请求的模型与您在 Cloudflare 和后端服务中配置的相匹配。