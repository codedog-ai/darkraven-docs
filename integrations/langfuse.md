# Langfuse

{% hint style="info" %}
If you are using Python, Javascript or other Langfuse compatible language, you can submit LLM traces  to Darkraven with Langfuse SDK.

\
Full compatibility reference:&#x20;

\- [Langfuse SDKs - Overview](https://langfuse.com/docs/sdk/overview)

\- [Langfuse Integrations - Overview](https://langfuse.com/docs/integrations/overview)
{% endhint %}

## Installation

Installation guides are from [Langfuse SDKs](https://langfuse.com/docs/sdk/overview) document.

{% tabs %}
{% tab title="Python" %}
```bash
pip install langfuse
```
{% endtab %}

{% tab title="Javascript" %}
```bash
npm i langfuse
# or
yarn add langfuse
 
# Node.js < 18
npm i langfuse-node
 
# Deno
import { Langfuse } from "https://esm.sh/langfuse"// Some code
```
{% endtab %}
{% endtabs %}

## Setup

1. Create an API key in Darkraven in settings
2. Add environment variables

* LANGFUSE\_SECRET\_KEY: Your API key
* LANGFUSE\_PUBLIC\_KEY: Your API key
* LANGFUSE\_HOST: Use `https://api.darkraven.ai/api/dify`

## Usage Example

Examples are from [Langfuse SDKs](https://langfuse.com/docs/sdk/overview) document.

{% tabs %}
{% tab title="Python" %}
```python
from langfuse.decorators import observe
from langfuse.openai import openai # OpenAI integration
 
@observe()
def story():
    return openai.chat.completions.create(
        model="gpt-3.5-turbo",
        max_tokens=100,
        messages=[
          {"role": "system", "content": "You are a great storyteller."},
          {"role": "user", "content": "Once upon a time in a galaxy far, far away..."}
        ],
    ).choices[0].message.content
 
@observe()
def main():
    return story()
 
main()
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import { Langfuse } from "langfuse"; // or "langfuse-node"
 
// without additional options
const langfuse = new Langfuse();
 
// with additional options
const langfuse = new Langfuse({
  release: "v1.0.0",
  requestTimeout: 10000,
});
```
{% endtab %}
{% endtabs %}
