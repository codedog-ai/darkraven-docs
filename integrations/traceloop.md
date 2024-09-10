# Traceloop

{% hint style="danger" %}
<mark style="color:red;">**Traceloop Integration is temporarily unavailable.**</mark>
{% endhint %}

{% hint style="info" %}
If you are using python, javascript or other Traceloop compatible language, you can submit LLM traces  to Darkraven with Traceloop SDK.

\
Full compatibility reference: \
\- [Traceloop Doc - OpenLLMetry](https://www.traceloop.com/docs/openllmetry/introduction)

\- [Traceloop Doc - What's support ?](https://www.traceloop.com/docs/openllmetry/tracing/supported)
{% endhint %}

## Install Traceloop

{% tabs %}
{% tab title="Python" %}
```bash
pip install traceloop-sdk
```
{% endtab %}
{% endtabs %}

## Initialization

{% tabs %}
{% tab title="Python" %}
```python
from opentelemetry.exporter.otlp.proto.http.metric_exporter import OTLPMetricExporter
from opentelemetry.exporter.otlp.proto.http.trace_exporter import OTLPSpanExporter
from traceloop.sdk import Traceloop


app_name="LLM app name"
trace_endpoint="https://api.darkraven.com/api/v1/insert/trace-otlp"
metric_endpoint="https://api.darkraven.com/api/v1/insert/metric-otlp"
apikey="Darkraven API Key"

traces_exporter = OTLPSpanExporter(
    endpoint=trace_endpoint,
    headers={"apikey":apikey}
)
    
metrics_exporter = OTLPMetricExporter(
    endpoint_metric_endpoint,
    headers={"apikey":apikey}
)

Traceloop.init(
    app_name=app_name,
    exporter=traces_exporter,
    metrics_exporter=metrics_exporter
)
```
{% endtab %}
{% endtabs %}

## Other

To use other functionality of Langsmith, refer to: [Traceloop Doc - Workflow Annotations](https://www.traceloop.com/docs/openllmetry/tracing/annotations).
