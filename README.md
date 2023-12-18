# GeminiTranslate: Free Python Translation API using Google Gemini

[中文版本文档](README_CN.md)

This is a translation API written in Python that integrates with "immersive translation" plugin in browser, using the Google Gemini API, which is powered by Google's generative AI technology. It provides compatibility with the DeepLx interface.

## Usage

To use the GeminiTranslate, follow the steps below:

1. [Obtain a free API key from Google.](https://makersuite.google.com/app/apikey) You can configure the API key by replacing `"YOUR_API_KEY"` with your actual API key in `main.py`:

   ```python
   genai.configure(api_key="YOUR_API_KEY")
   ```

2. Install the required dependencies:

   ```bash
    pip install -r requirements.txt
   ```

3. Run the Flask application on the local server, default API address is `http://127.0.0.1:5000/translate`:

   ```bash
   python ./main.py
   ```

4. Configure immersive translation plugin.
   - In developer settings, turn on `Beta features`.
   - Basic settings -> Translate service -> DeepLX(Beta)
   - Set `API URL` to your API address, default is `http://127.0.0.1:5000/translate`.

5. Enjoy!

## Notes

- You can adjust the `safety_settings` and `generation_config` parameters according to your requirements, default is none.
- Make sure you can access the Google API, otherwise you may need to use a proxy.
- The API is limited to 60 times per minute, you can [apply for a higher limit here](https://ai.google.dev/docs/increase_quota), or set the maximum number of requests per second to 1 in the immersive translation custom options.
- Prompt injection may exist in the translation result.
