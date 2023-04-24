In this example, we'll use Python and Flask to create a simple web application and instrument it with OpenTelemetry for tracing and metrics. You can adapt this example for other programming languages and frameworks.

Create a new directory for your project and set up a virtual environment:

```
apt install python3.8-venv
mkdir opentelemetry-example
cd opentelemetry-example
python -m venv venv
source venv/bin/activate
```{{exec}}


Install Flask and OpenTelemetry packages:

```
pip install Flask opentelemetry-api opentelemetry-sdk opentelemetry-instrumentation opentelemetry-instrumentation-flask opentelemetry-exporter-jaeger

```{{exec}}


