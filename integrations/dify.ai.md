---
description: >-
  (Dify)[https://github.com/langgenius/dify] is an open-source LLM app
  development platform. If you are using Dify to develop and deploy your LLM
  application. You can send your trace data to darkraven.
---

# Dify.ai

1. Create an API key in Darkraven in settings
2. In Dify: go to `Monitoring`  - `Tracing app performance`
3. Config `Langfuse` as a provider. Add your Darkraven API key to both `Secret Key` and `Public Key`
4. Add `https://api.darkraven.ai/api/dify` to `Host`
5. Click `Save & Enable`
6. Now you can see your LLM traces in Darkraven.

