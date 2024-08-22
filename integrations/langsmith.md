# Langsmith

{% hint style="info" %}
<mark style="color:blue;">If you are using Langchain or other Langchain based framework to develop. You can use Langsmith SDK to submit LLM traces to Darkraven.</mark>
{% endhint %}

## Install Langsmith

{% tabs %}
{% tab title="Python" %}
<pre><code><strong>pip install langsmith
</strong></code></pre>
{% endtab %}
{% endtabs %}

## Create an API Key

In settings, go to **API Key** tab and create an API Key。

## Configuration

Add below config to Langchain:

{% tabs %}
{% tab title="Through environment variables" %}
<pre><code><strong>export LANGCHAIN_TRACING_V2=true
</strong>export LANGCHAIN_API_KEY=&#x3C;your-api-key>
export LANGCHAIN_PROJECT=&#x3C;your-project-name>
export LANGCHAIN_ENDPOINT=https://api.darkraven.ai/api/v1/insert
</code></pre>
{% endtab %}
{% endtabs %}

## Other

To use other functionality of Langsmith, refer to: [Langsmith Doc - Tracing](https://docs.smith.langchain.com/how\_to\_guides/tracing)
