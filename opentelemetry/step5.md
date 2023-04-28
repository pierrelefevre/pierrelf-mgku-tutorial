Run Jaeger in a Docker container:

```
docker run -d --name jaeger -p 6831:6831/udp -p 16686:16686 jaegertracing/all-in-one:latest

```{{exec}}


```
export OTEL_PYTHON_FLASK_EXCLUDED_URLS="metrics"
export OTEL_PYTHON_METRICS_EXPORTER=console
export OTEL_PYTHON_TRACES_EXPORTE01R=jaeger
export OTEL_TRACES_EXPORTER=jaeger

opentelemetry-instrument python app.py
```{{exec}}

