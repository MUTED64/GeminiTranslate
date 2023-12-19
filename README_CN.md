# GeminiTranslate： 基于 Google Gemini 的免费 Python 翻译 API

基于 Google Gemini 生成式人工智能技术的 Python 翻译 API，可与浏览器中的 “沉浸式翻译” 插件集成。~~狠狠地用 prompt PUA 了一下 Google Gemini~~

## 使用方法

要使用 GeminiTranslate，请按照以下步骤操作：

1. [从 Google 获取免费 API 密钥。](https://makersuite.google.com/app/apikey) 您可以在 `main.py` 中用实际 API 密钥替换 `os.getenv('GOOGLE_API_KEY')` 来配置 API 密钥：

   ```python
   genai.configure(api_key="YOUR_API_KEY")
   ```

2. 安装所需的依赖项：

   ```bash
    pip install -r requirements.txt
   ```

3. 在本地服务器上运行 Flask 应用程序，默认 API 地址为 `http://127.0.0.1/translate`：

   ```bash
   python ./main.py
   ```

4. 配置沉浸式翻译插件。

   - 在开发者设置中，打开 “Beta 测试特性”。
   - 基本设置 -> 翻译服务 -> 自定义API
   - 将 "API URL" 设置为你的 API 地址，默认为 `http://127.0.0.1/translate`。

5. 开始使用！

## 注意事项

- 你可以根据自己的需要调整 `generation_config` 中的 `safety_settings` 参数，默认为无安全限制。
- 确保可以访问 Google API，否则可能需要使用代理。
- API 的访问次数限制为每分钟 60 次，您可以 [在此申请更高的限制](https://ai.google.dev/docs/increase_quota)，或在沉浸式翻译自定义选项中将每秒最大请求数设为 1。
- 翻译结果中偶尔可能存在提示注入的问题。
- Gemini API 不允许谈论 OpenAI 相关的任何话题😑
- 推荐使用自定义选项中的每秒最大请求数：1，每次请求最大段落数：20，以避免超出限制。
