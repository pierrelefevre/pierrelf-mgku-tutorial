Modify app.py to use OpenTelemetry instrumentation:

```
nano app.py
```{{exec}}

```
from flask import Flask
from opentelemetry.instrumentation.flask import FlaskInstrumentor
from trace import get_tracer

app = Flask(__name__)
FlaskInstrumentor().instrument_app(app)
tracer = get_tracer()

@app.route("/")
def hello():
    with tracer.start_as_current_span("hello-span"):
        return "Hello, OpenTelemetry!"

if __name__ == "__main__":
    app.run(port=5000)

```
